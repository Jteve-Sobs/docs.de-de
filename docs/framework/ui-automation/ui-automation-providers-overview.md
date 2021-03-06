---
title: Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, providers
- providers, UI Automation
ms.assetid: 859557b8-51e1-4d15-92e8-318d2dcdb2f7
ms.openlocfilehash: 1f780ffc37b0aff93a3358c1980d271fe10c1321
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179879"
---
# <a name="ui-automation-providers-overview"></a>Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Benutzeroberflächenautomatisierungs-Anbieter ermöglichen Steuerelementen die Kommunikation mit Clientanwendungen für die Automatisierung der Benutzeroberfläche. Im Allgemeinen wird jedes Steuerelement oder anderes eindeutiges Element auf einer [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] von einem Anbieter dargestellt. Der Anbieter macht Informationen zum Element verfügbar und implementiert optional Steuerelementmuster, die es der Clientanwendung ermöglichen, mit dem Steuerelement zu interagieren.  
  
 Clientanwendungen müssen normalerweise nicht direkt mit Anbietern arbeiten. Die meisten Standardsteuerelemente in Anwendungen, die Win32, Windows Forms [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] oder [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Frameworks verwenden, werden automatisch für das System verfügbar gemacht. Anwendungen, die benutzerdefinierte Steuerelemente implementieren, können auch [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anbieter für diese Steuerelemente implementieren, und die Clientanwendungen müssen keine besonderen Schritte ausführen, um Zugriff auf diese zu erlangen.  
  
 Dieses Thema bietet einen Überblick [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] darüber, wie Steuerelemententwickler Anbieter implementieren, insbesondere für Steuerelemente in Windows Forms und Win32-Fenstern.  
  
<a name="Types_of_Providers"></a>
## <a name="types-of-providers"></a>Anbietertypen  
 Benutzeroberflächenautomatisierungs-Anbieter werden in zwei Kategorien unterteilt: clientseitige und serverseitige Anbieter.  
  
### <a name="client-side-providers"></a>Clientseitige Anbieter  
 Clientseitige Anbieter werden von Benutzeroberflächenautomatisierungs-Clients für die Kommunikation mit einer Anwendung implementiert, die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht oder nicht vollständig unterstützt. Clientseitige Anbieter kommunizieren in der Regel über die Prozessgrenze hinweg mit dem Server, indem sie Windows-Nachrichten senden und empfangen.  
  
 Da Benutzeroberflächenautomatisierungsanbieter für Steuerelemente in Win32, Windows Forms oder [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Anwendungen als Teil des Betriebssystems bereitgestellt werden, müssen Clientanwendungen selten eigene Anbieter implementieren, und diese Übersicht deckt sie nicht weiter ab.  
  
### <a name="server-side-providers"></a>Serverseitiger Anbieter  
 Serverseitige Anbieter werden von benutzerdefinierten Steuerelementen oder von Anwendungen implementiert, die auf einem [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]anderen UI-Framework als Win32, Windows Forms oder basieren.  
  
 Serverseitige Anbieter kommunizieren mit Clientanwendungen über Prozessgrenzen hinweg, indem sie Schnittstellen für das [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Kernsystem verfügbar machen, das wiederum Anforderungen von Clients bereitstellt.  
  
<a name="AutomationProviderConcepts"></a>
## <a name="ui-automation-provider-concepts"></a>Konzepte für Benutzeroberflächenautomatisierungs-Anbieter  
 Dieser Abschnitt bietet kurze Erläuterungen zu einer Auswahl von Schlüsselkonzepten, die Sie kennen müssen, um Benutzeroberflächenautomatisierungs-Anbieter implementieren zu können.  
  
### <a name="elements"></a>Elemente  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Elemente sind Bestandteile der [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] , die für Benutzeroberflächenautomatisierungs-Clients angezeigt werden. Zu den entsprechenden Beispielen zählen Anwendungsfenster, Bereiche, Schaltflächen, QuickInfos, Listenfelder und Listenelemente.  
  
### <a name="navigation"></a>Navigation  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Elemente werden für Clients als [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur verfügbar gemacht. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] erstellt die Struktur durch Navigieren von einem Element zu einem anderen. Die Navigation wird von den Anbietern für jedes Element aktiviert, von denen jedes möglicherweise auf ein übergeordnetes, gleichgeordnetes oder untergeordnetes Element verweist.  
  
 Weitere Informationen zur Clientansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
### <a name="views"></a>Sichten  
 Ein Client kann die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur in drei hauptsächlichen Ansichten anzeigen, wie in der folgenden Tabelle dargestellt.  
  
|||  
|-|-|  
|Rohdatenansicht|Enthält alle Elemente.|  
|Steuerelementansicht|Enthält Elemente, die Steuerelemente sind.|  
|Inhaltsansicht|Enthält Elemente mit Inhalten.|  
  
 Weitere Informationen zu Clientansichten der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
 Für die Definition eines Elements als Inhaltselement oder Steuerelement ist die Anbieterimplementierung zuständig. Steuerelemente können auch Inhaltselemente sein, aber alle Inhaltselemente sind auch Steuerelemente.  
  
### <a name="frameworks"></a>Frameworks  
 Ein Framework ist eine Komponente, die untergeordneten Steuerelemente, Treffertests und das Rendering in einem Bereich des Bildschirms verwaltet. Beispielsweise kann ein Win32-Fenster, das häufig als HWND bezeichnet wird, als Framework dienen, das mehrere [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Elemente wie eine Menüleiste, eine Statusleiste und Schaltflächen enthält.  
  
 Win32-Containersteuerelemente wie Listenfelder und Baumansichten werden als Frameworks betrachtet, da sie ihren eigenen Code zum Rendern von untergeordneten Elementen und zum Durchführen von Treffertests für sie enthalten. Im Gegensatz dazu ist ein [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Listenfeld kein Framework, da Rendering und Treffertests vom enthaltenen [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Fenster übernommen werden.  
  
 Die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] in einer Anwendung kann aus verschiedenen Frameworks bestehen. Beispielsweise kann ein HWND-Anwendungsfenster Dynamic HTML (DHTML) enthalten, das wiederum eine Komponente wie ein Kombinationsfeld in einer HWND enthält.  
  
### <a name="fragments"></a>Fragments  
 Ein Fragment ist eine vollständige Unterstruktur von Elementen eines bestimmten Frameworks. Das Element im Stammknoten der Unterstruktur wird als Fragmentstamm bezeichnet. Ein Fragmentstamm hat kein übergeordnetes Element, sondern wird in einem anderen Framework gehostet, in der Regel in einem Win32-Fenster (HWND).  
  
### <a name="hosts"></a>Hosts  
 Der Stammknoten jedes Fragments muss in einem Element gehostet werden, in der Regel in einem Win32-Fenster (HWND). Die Ausnahme stellt der Desktop dar, der in keinem anderen Element gehostet wird. Der Host eines benutzerdefinierten Steuerelements ist das HWND des Steuerelements selbst, nicht das Anwendungsfenster oder ein anderes Fenster, das möglicherweise Gruppen von Steuerelementen der obersten Ebene enthält.  
  
 Der Host eines Fragments spielt bei der Bereitstellung von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Diensten eine wichtige Rolle. Er ermöglicht die Navigation zum Fragmentstamm und stellt einige Standardeigenschaften bereit, damit diese nicht vom benutzerdefinierten Anbieter implementiert werden müssen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters](server-side-ui-automation-provider-implementation.md)
