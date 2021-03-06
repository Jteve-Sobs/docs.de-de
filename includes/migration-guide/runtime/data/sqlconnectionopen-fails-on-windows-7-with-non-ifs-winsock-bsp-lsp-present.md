---
ms.openlocfilehash: 65d9edc1e7377a86f8185ebf28bb5bee3a3f887d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803251"
---
### <a name="sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>SqlConnection.Open schlägt unter Windows 7 mit vorhandenem Nicht-IFS-Winsock-BSP oder -LSP fehl

|   |   |
|---|---|
|Details|Auf einem Windows 7-Computer mit einem Nicht-IFS-Winsock-BSP oder -LSP schlagen <xref:System.Data.SqlClient.SqlConnection.Open> und <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> in .NET Framework 4.5 fehl. Verwenden Sie den Befehl <code>netsh WinSock Show Catalog</code>, und untersuchen Sie alle <code>Winsock Catalog Provider Entry</code>-Elemente, die zurückgegeben werden, um zu erkennen, ob ein Nicht-IFS-Winsock-BSP oder -LSP installiert ist. Wenn für den Servicekennzeichenwert das <code>0x20000</code>-Bit gesetzt ist, verwendet der Anbieter IFS-Handle und funktioniert daher ordnungsgemäß. Wenn das <code>0x20000</code>-Bit leer (nicht festgelegt) ist, handelt es sich um ein Nicht-IFS-BSP oder -LSP.|
|Vorschlag|Dieses Problem wurde in .NET Framework 4.5.2 behoben, daher kann es durch ein Upgrade von .NET Framework vermieden werden. Alternativ kann es durch Entfernen aller installierten Nicht-IFS-Winsock-LSPs vermieden werden.|
|`Scope`|Nebenversion|
|Version|4.5|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)?displayProperty=nameWithType></li></ul>|
