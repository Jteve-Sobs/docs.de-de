---
title: Die Datei ist zu groß, um in ein Bytearray geladen zu werden
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: a842205e9184355e4ea750ea2eb32e4bcf05a14d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665100"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>Die Datei ist zu groß, um in ein Bytearray geladen zu werden
Die Größe der Datei, die Sie versuchen, ein Bytearray eingelesen überschreitet Zustand 4 GB. Die `My.Computer.FileSystem.ReadAllBytes` Methode eine Datei, die diese Größe überschreitet kann nicht gelesen werden.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verwenden einer <xref:System.IO.StreamReader> zum Lesen der Datei. Weitere Informationen finden Sie unter [Grundlagen der .NET Framework-Datei-e/a und dem Dateisystem (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [Dateizugriff mit Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
- [Vorgehensweise: Lesen von Text aus Dateien mit einem StreamReader](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
