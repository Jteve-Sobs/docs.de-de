---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 6167a4ad56a9481a9f695b770605991a0a88d2d9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399411"
---
# <a name="transactedbatching"></a>\<transactedBatching>

Gibt an, ob Transaktionsbatching für Empfangsvorgänge unterstützt wird.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<transactedbatching->**  

## <a name="syntax"></a>Syntax

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|`maxBatchSize`|Eine ganze Zahl, die die maximale Anzahl an Empfangsvorgängen angibt, die in einer Transaktion zusammengefasst werden können. Die Standardeinstellung ist 0.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<behavior>](behavior-of-endpointbehaviors.md)|Gibt ein Endpunktverhalten an.|

## <a name="remarks"></a>Hinweise

Ein Transport, der für Transaktionsbatchingversuche konfiguriert ist, um verschiedene Empfangsvorgänge in einer Transaktion zusammenzufassen. Dadurch wird der relativ große Aufwand für das Erstellen und Übergeben einer Transaktion bei jedem Empfangsvorgang vermieden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie einem Dienst das transaktive Batchverarbeitungsverhalten in einer Konfigurationsdatei hinzugefügt wird.

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamples"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IQueueCalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <behaviors>
    <endpointBehaviors>
      <behavior name="endpointBehavior">
        <transactedBatching maxBatchSize="10" />
      </behavior>
    </endpointBehaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="true" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
