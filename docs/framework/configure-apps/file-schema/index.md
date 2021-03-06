---
title: Konfigurationsdateischema für .NET Framework
ms.date: 05/01/2017
helpviewer_keywords:
- .NET Framework application configuration, configuration schema
- machine configuration files
- application configuration files, schema
- app.config files, schema
- schema configuration settings
- schemas, configuration settings
- enterprisesec.config files
- well-formed XML
- enterprisesec configuration files
- security.config files
- security [.NET Framework], configuration files
- application development [.NET Framework], schema
- XML tags
- container tags
- machine.config files
- configuration schema [.NET Framework]
- configuration settings [.NET Framework], applications
- configuration file reference [.NET Framework]
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
ms.openlocfilehash: 35ed53fc480e218df595794f80af2458f3ecec38
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039158"
---
# <a name="configuration-file-schema-for-the-net-framework"></a>Konfigurationsdateischema für .NET Framework

Konfigurationsdateien sind Standard-XML-Dateien, die Sie verwenden können, um für Ihre Apps Einstellungen zu ändern und Richtlinien festzulegen. Das .NET Framework-Konfigurationsschema besteht aus Elementen, die Sie in Konfigurationsdateien verwenden können, um das Verhalten der Apps zu steuern. Das Inhaltsverzeichnis dieses Abschnitts gibt die Schemahierarchie für Startup, Laufzeit, Netzwerk und anderen Arten von Konfigurationseinstellungen wider.

Informationen zu den Typen, dem Format und dem Speicherort der Konfigurationsdateien finden Sie unter [Konfigurieren von apps](../index.md). Machen Sie sich mit XML vertraut, wenn Sie die Konfigurationsdateien direkt bearbeiten möchten.

> [!IMPORTANT]
> Bei XML-Tags und -Attributen in Konfigurationsdateien muss die Groß-/Kleinschreibung beachtet werden.

## <a name="in-this-section"></a>In diesem Abschnitt

[ **\<Configuration >** -Element](configuration-element.md)\
Das Element der obersten Ebene für alle Konfigurationsdateien.

[ **\<assemblyBinding >** Element](assemblybinding-element-for-configuration.md)\
Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.

[ **\<linkedconfiguration->** Element](linkedconfiguration-element.md)\
Gibt eine einzuschließende Konfigurationsdatei an.

[Schema\ für Start Einstellungen](./startup/index.md)
-Elemente, die angeben, welche Version des Common Language Runtime verwendet werden soll.

[Schema](./runtime/index.md)\ für Lauf Zeit Einstellungen
Elemente, die Assemblybindung und Laufzeitverhalten konfigurieren.

[Network Settings Schema (Netzwerkeinstellungsschema)](./network/index.md)\
-Elemente, die angeben, wie die .NET Framework eine Verbindung mit dem Internet herstellt.

[Schema\ für Kryptografieeinstellungen](./cryptography/index.md)
Elemente, die den Klassen, die Kryptografiealgorithmen implementieren, benutzerfreundliche Algorithmusnamen zuordnen.

[Schema\ für Konfigurations Abschnitte](configuration-sections-schema.md)
Elemente, mit denen Konfigurations Abschnitte für benutzerdefinierte Einstellungen erstellt und verwendet werden.

Schema\ für Ablauf [Verfolgungs-und Debugeinstellungen](./trace-debug/index.md)
-Elemente, die Ablauf Verfolgungs Schalter und-Listener angeben.

[Schema\ für Compiler-und Sprachanbieter Einstellungen](./compiler/index.md)
-Elemente, die die Compilerkonfiguration für verfügbare Sprachanbieter angeben.

[Schema\ für Anwendungseinstellungen](application-settings-schema.md)
Elemente, die eine Windows Forms-oder ASP.NET-Anwendung zum Speichern und Abrufen von anwendungsbezogenen und Benutzer bezogenen Einstellungen aktivieren.

[Schema](./appsettings/index.md)\ für App-Einstellungen
Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.

[Webeinstellungs Schema](./web/index.md)\
Elemente zum Konfigurieren, wie ASP.net mit einer Host Anwendung wie IIS funktioniert. Wird in *Aspnet.config*-Dateien verwendet.

[Windows Forms Konfigurations Schema](winforms/index.md)\
Alle Elemente im Konfigurations Abschnitt Windows Forms-Anwendung, der Anpassungen wie Multimonitor-und High-dpi-Unterstützung umfasst.

[WCF-Konfigurations Schema](./wcf/index.md)\
Alle Elemente, die es Ihnen ermöglichen, WCF-Dienst-und-Client Anwendungen zu konfigurieren.

[WCF-Direktivensyntax](./wcf-directive/index.md)\
Beschreibt die `@ServiceHost`-Direktive, die Seiten spezifische Attribute definiert, die vom SVC-Compiler verwendet werden.

[WIF Configuration Schema (Schema zur WIF-Konfiguration)](windows-identity-foundation/index.md)\
Alle Elemente des Windows Identity Foundation (WIF)-Konfigurations Schemas.

## <a name="related-sections"></a>Verwandte Abschnitte

[Schema\ für Remote Einstellungen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))
Beschreibt die Elemente, mit denen Client- und Serveranwendungen konfiguriert werden, die Remotefunktionen implementieren.

[ASP.NET Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))\
Beschreibt die Elemente, die das Verhalten von ASP.NET-Webanwendungen steuern.

Schema\ für die [Webdienst Einstellungen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))
Beschreibt die Elemente, die das Verhalten von ASP.NET-Webdiensten und ihren Clients steuern.

[Konfigurieren von .NET Framework-Apps](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))\
Beschreibt, wie Sicherheit, Assemblybindung und Remotefunktionen in .NET Framework konfiguriert werden.
