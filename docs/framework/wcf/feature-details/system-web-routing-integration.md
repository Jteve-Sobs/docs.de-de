---
title: System.Web.Routing-Integration
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: a80b5c3b336b4fd18b347a25ceaf509baf6461b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184392"
---
# <a name="systemwebrouting-integration"></a>System.Web.Routing-Integration
Wenn Sie einen Windows Communication Foundation (WCF)-Dienst im Internet Informationsdienst (Internet Information Service, IIS) hosten, platzieren Sie eine .svc-Datei im virtuellen Verzeichnis. Diese SVC-Datei gibt die zu verwendende Diensthostfactory sowie die Klasse an, die den Dienst implementiert. Wenn Sie Anforderungen an den Dienst stellen, geben Sie die `http://contoso.com/EmployeeServce.svc`.svc-Datei im URI an, z. B.: . Für Programmierer, die REST-Dienste schreiben, ist dieser Typ von URI nicht optimal. URIs für REST-Dienste geben eine bestimmte Ressource an und verfügen normalerweise nicht über Erweiterungen. Mit <xref:System.Web.Routing> der Integrationsfunktion können Sie einen WCF-REST-Dienst hosten, der auf URIs ohne Erweiterung reagiert. Weitere Informationen zum Routing finden [Sie unter ASP.NET Routing](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100)).  
  
## <a name="using-systemwebrouting-integration"></a>Verwenden der System.Web.Routing-Integration  
 Für die <xref:System.Web.Routing>-Integrationsfunktion verwenden Sie die <xref:System.ServiceModel.Activation.ServiceRoute>-Klasse, um eine oder mehrere Routen zu erstellen und diese dem <xref:System.Web.Routing.RouteTable>-Objekt in einer Global.asax-Datei hinzuzufügen. Diese Routen geben die relativen URIs an, auf die der Dienst reagiert. Das folgende Beispiel zeigt die erforderliche Vorgehensweise.  
  
```aspx-csharp  
<%@ Application Language="C#" %>  
<%@ Import Namespace="System.Web.Routing" %>  
<%@ Import Namespace="System.ServiceModel.Activation" %>  
<%@ Import Namespace="System.ServiceModel.Web " %>  
  
<script RunAt="server">  
    void Application_Start(object sender, EventArgs e)  
    {  
        RegisterRoutes(RouteTable.Routes);  
    }  
  
    private void RegisterRoutes(RouteCollection routes)  
    {  
        routes.Add(new ServiceRoute("Customers", new WebServiceHostFactory(), typeof(Service)));
   }  
</script>  
```  
  
 Hier werden alle Anforderungen mit einem relativen URI, die mit "Customers" beginnen, an den `Service`-Dienst weitergeleitet.  
  
 In der Datei "Web.config" müssen Sie das `System.Web.Routing.UrlRoutingModule`-Modul hinzufügen, das `runAllManagedModulesForAllRequests`-Attribut auf `true` setzen und dem `UrlRoutingHandler`-Element den `<system.webServer>`-Handler hinzufügen. Dies wird im folgenden Beispiel veranschaulicht.  
  
```xml  
<system.webServer>  
      <modules runAllManagedModulesForAllRequests="true">  
        <add name="UrlRoutingModule" type="System.Web.Routing.UrlRoutingModule, System.Web, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" />  
      </modules>  
      <handlers>  
        <add name="UrlRoutingHandler" preCondition="integratedMode" verb="*" path="UrlRouting.axd"/>  
      </handlers>  
    </system.webServer>  
```  
  
 Es werden ein Modul und ein Handler geladen, die für das Routing erforderlich sind. Weitere Informationen finden Sie unter [Routing](../../../../docs/framework/wcf/feature-details/routing.md). Außerdem müssen Sie das `aspNetCompatibilityEnabled`-Attribut wie im folgenden Beispiel gezeigt im `true`-Element auf `<serviceHostingEnvironment>` setzen.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 Die Klasse, die den Dienst implementiert, muss die ASP.NET-Kompatibilitätsanforderungen wie im folgenden Beispiel gezeigt aktivieren.  
  
```csharp
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [ASP.NET-Routing](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))
