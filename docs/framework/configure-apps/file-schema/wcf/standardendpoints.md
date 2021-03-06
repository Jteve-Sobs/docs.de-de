---
title: <standardEndpoints>
ms.date: 03/30/2017
ms.assetid: d62153d7-a6e6-462a-a784-cca61e9c2ba1
ms.openlocfilehash: 76a5303650c4e2b2887d29f511d3088c78b58fe2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399514"
---
# <a name="standardendpoints"></a>\<standardEndpoints>
Dieser Konfigurationsabschnitt ermöglicht die Definition einer Auflistung von Standardendpunkten, bei denen es sich um wiederverwendbare vorkonfigurierte Endpunkte handelt. Bei einem Standardendpunkt werden eines oder mehrere der Attribute für Adresse, Bindung und Vertrag vorab festgelegt. Zum Beispiel ist der Vertrag im Ermittlungsendpunkt ein fester Wert. Sie können Standardendpunkte auch verwenden, um Dienstendpunkte mit neuen Eigenschaften zu erweitern, ähnlich wie bei der Definition benutzerdefinierter Bindungen.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<standardendpoints->**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|Definiert einen Standardendpunkt mit einem festen Ankündigungsvertrag. Die Verfügbarkeit eines Diensts kann optional angekündigt werden, indem beim Öffnen bzw. Schließen des Diensts eine Online- bzw. Offline-Ankündigungsnachricht gesendet wird. Ein Windows Communication Foundation (WCF)-Dienst gibt die Ankündigungs Endpunkte im [ \<servicediscovery->](servicediscovery.md) Element an und verwendet den "-Dienst", um die Ankündigungen auszuführen. Ein Client, der auf die Ankündigung von einem anderen Dienst lauschen möchte, fungiert tatsächlich als WCF-Dienst. Daher müssen Sie die Ankündigungs Endpunkte für diesen Client im [ \<Abschnitt Dienste >](services.md) konfigurieren.|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|Definiert einen Standardendpunkt mit einem festen Ermittlungsvertrag. Wenn es der Dienstkonfiguration hinzugefügt wird, gibt es an, wo die Überwachung auf Ermittlungsnachrichten erfolgen soll. Wenn es der Clientkonfiguration hinzugefügt wird, gibt es an, wohin die Ermittlungsabfragen gesendet werden sollen.|  
|[\<dynamicEndpoint>](dynamicendpoint.md)|Dieses Konfigurationselement definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.|  
|[\<mexendpoint->](mexendpoint.md)|Definiert einen Standardendpunkt mit einem festen IMetadataExchange-Vertrag. Da alle Metadatenaustausch-Endpunkte IMetadataExchange als Vertrag angeben, können Sie diesen Standardpunkt verwenden, statt einen eigenen zu definieren.|  
|[\<udpAnnouncementEndpoint>](udpannouncementendpoint.md)|Definiert einen Standardendpunkt, der von Diensten verwendet wird, um Ankündigungsnachrichten über eine UDP-Bindung zu senden. Es weist einen festen Vertrag auf und unterstützt zwei Suchversionen. Außerdem weist er eine feste UDP-Bindung und einen Standardadresswert gemäß WS-Discovery-Spezifikationen (WS-Discovery Version April 2005 oder Version 1.1) auf. Sie können die Multicastadresse angeben, die zum Senden und Empfangen der Ankündigungsnachrichten verwendet werden soll.|  
|[\<udpDiscoveryEndpoint>](udpdiscoveryendpoint.md)|Definiert einen Standardendpunkt, der für Suchvorgänge über eine UDP-Multicastbindung vorkonfiguriert ist. Dieser Endpunkt hat einen festen Vertrag und unterstützt zwei WS-Discovery-Protokollversionen. Außerdem weist er eine feste UDP-Bindung und eine Standardadresse gemäß WS-Discovery-Spezifikationen (WS-Discovery Version April 2005 oder Version 1.1) auf.|  
|[\<webHttpEndpoint>](webhttpendpoint.md)|Definiert einen Standard Endpunkt mit einem fixierten [ \<WebHttpBinding->](webhttpbinding.md) Bindung, der das [ \<webHttp->](webhttp.md) Verhalten automatisch hinzufügt. Verwenden Sie diesen Endpunkt, wenn Sie einen REST-Dienst schreiben.|  
|[\<webScriptEndpoint>](webscriptendpoint.md)|Definiert einen Standard Endpunkt mit einem fixierten [ \<WebHttpBinding->](webhttpbinding.md) Bindung, der automatisch das > Verhalten der [ \<enableWebScript](enablewebscript.md) -Eigenschaft hinzufügt. Verwenden Sie diesen Endpunkt, wenn Sie einen Dienst schreiben, der von einer ASP.NET AJAX-Anwendung aufgerufen wird.|  
|[\<workflowControlEndpoint>](workflowcontrolendpoint.md)|Definiert einen Standardendpunkt zur Steuerung der Ausführung von Workflowinstanzen (create, run, suspend, terminate usw.).|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|\<system.ServiceModel>|Das Stammelement aller WCF-Konfigurationselemente.|  
  
## <a name="see-also"></a>Siehe auch

- [Standardendpunkte](../../../wcf/feature-details/standard-endpoints.md)
