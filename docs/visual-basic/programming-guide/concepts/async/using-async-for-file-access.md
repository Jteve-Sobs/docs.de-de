---
title: Verwenden von Async für Dateizugriff
ms.date: 07/20/2015
ms.assetid: c989305f-08e3-4687-95c3-948465cda202
ms.openlocfilehash: 803d182f5b0f3071feb7aae4945bc3c0a1fd82c3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349106"
---
# <a name="using-async-for-file-access-visual-basic"></a>Using Async for File Access (Visual Basic) (Verwenden von Async für Dateizugriff (Visual Basic))
Sie können die Async-Funktion verwenden, um auf Dateien zuzugreifen. Mithilfe der Async-Funktion können Sie asynchrone Methoden aufrufen, ohne Rückrufe zu verwenden oder den Code über mehrere Methoden oder Lambdaausdrücke teilen zu müssen. Um synchronen Code asynchron auszuführen, rufen Sie einfach eine asynchrone Methode anstelle einer synchronen Methode auf und fügen Sie dem Code einige Schlüsselwörter hinzu.  
  
 Sie sollten die folgenden Gründe für das Hinzufügen von Asynchronie zu Dateizugriffsaufrufen in Betracht ziehen:  
  
- Durch Asynchronie kann die Reaktionsfähigkeit von UI-Anwendungen verbessert werden, da der UI-Thread, der den Vorgang startet, andere Aufgaben durchführen kann. Wenn der UI-Thread Code ausführt, der viel Zeit benötigt (z.B. mehr als 50 Millisekunden), kann die UI einfrieren, bis der E/A-Vorgang abgeschlossen ist und der UI-Thread wieder Tastatur- und Mauseingaben und andere Ereignisse verarbeiten kann.  
  
- Asynchronie verbessert die Skalierbarkeit von ASP.NET und anderen serverbasierten Anwendungen, indem die Notwendigkeit von Threads reduziert wird. Wenn die Anwendung einen dedizierten Thread pro Antwort verwendet und tausend Anforderungen gleichzeitig behandelt werden, werden auch tausend Threads benötigt. Asynchrone Vorgänge benötigen während der Wartezeit oft keinen Thread. Sie verwenden den vorhandenen E/A-Abschlussthread kurz am Ende.  
  
- Die Latenz von Dateizugriffsvorgängen kann unter bestimmten Umständen sehr niedrig sein, aber sie kann in Zukunft stark ansteigen. Eine Datei kann z.B. auf einen Server auf der anderen Seite der Erde verschoben werden.  
  
- Der zusätzliche Mehraufwand durch Verwendung der Async-Funktion ist gering.  
  
- Asynchrone Aufgaben können problemlos parallel ausgeführt werden.  
  
## <a name="running-the-examples"></a>Ausführen der Beispiele  
 Sie können eine **WPF-Anwendung** oder **Windows Forms-Anwendung** erstellen und dann eine **Schaltfläche** hinzufügen, um die Beispiele in diesem Thema auszuführen. Fügen Sie im `Click`-Ereignis der Schaltfläche einen Aufruf der ersten Methode jedes Beispiels hinzu.  
  
 Nehmen Sie in den folgenden Beispielen die `Imports`-Anweisungen mit auf.  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Diagnostics  
Imports System.IO  
Imports System.Text  
Imports System.Threading.Tasks  
```  
  
## <a name="use-of-the-filestream-class"></a>Verwenden der FileStream-Klasse  
 In den Beispielen in diesem Thema wird die <xref:System.IO.FileStream>-Klasse verwendet, die über eine Option verfügt, die asynchrone E/A-Vorgänge auf Betriebssystemebene auslöst. Mit dieser Option können Sie das Blockieren eines ThreadPool-Threads in vielen Fällen vermeiden. Geben Sie zum Aktivieren dieser Option das Argument `useAsync=true` oder `options=FileOptions.Asynchronous` im Konstruktoraufruf an.  
  
 Sie können diese Option nicht mit <xref:System.IO.StreamReader> und <xref:System.IO.StreamWriter> verwenden, wenn Sie sie direkt öffnen, indem Sie einen Dateipfad angeben. Allerdings können Sie diese Option verwenden, wenn Sie ihnen ein <xref:System.IO.Stream> geben, das die <xref:System.IO.FileStream>-Klasse geöffnet hat. Beachten Sie, dass asynchrone Aufrufe in Anwendungsbenutzeroberflächen schneller sind, selbst wenn ein ThreadPool-Thread blockiert wird, da der UI-Thread während der Wartezeit nicht blockiert ist.  
  
## <a name="writing-text"></a>Schreiben von Text  
 Im folgenden Beispiel wird Text in eine Datei geschrieben. Bei jeder await-Anweisung wird die Methode sofort beendet. Wenn die Datei-E/A abgeschlossen ist, wird die Methode bei der Anweisung hinter der await-Anweisung fortgesetzt. Beachten Sie, dass sich der async-Modifizierer in der Definition der Methoden befindet, die die await-Anweisung verwenden.  
  
```vb  
Public Async Sub ProcessWrite()  
    Dim filePath = "temp2.txt"  
    Dim text = "Hello World" & ControlChars.CrLf  
  
    Await WriteTextAsync(filePath, text)  
End Sub  
  
Private Async Function WriteTextAsync(filePath As String, text As String) As Task  
    Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Append, FileAccess.Write, FileShare.None,  
        bufferSize:=4096, useAsync:=True)  
  
        Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
    End Using  
End Function  
```  
  
 Das ursprüngliche Beispiel verfügt über die Anweisung `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, bei der es sich um eine Kontraktion der folgenden zwei Anweisungen handelt:  
  
```vb  
Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
Await theTask  
```  
  
 Die erste Anweisung gibt eine Aufgabe zurück und löst die Dateiverarbeitung aus. Die zweite await-Anweisung führt dazu, dass die Methode sofort beendet wird und eine andere Aufgabe zurückgibt. Wenn die Dateiverarbeitung später abgeschlossen wird, wird die Ausführung bei der Anweisung fortgesetzt, die auf die „await“-Anweisung folgt. Weitere Informationen finden Sie unter [Ablauf Steuerung in asynchronen Programmen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).  
  
## <a name="reading-text"></a>Lesen von Text  
 Im folgenden Beispiel wird Text aus einer Datei gelesen. Der Text wird gepuffert und in diesem Fall in <xref:System.Text.StringBuilder> abgelegt. Anders als im vorherigen Beispiel generiert die Auswertung von „await“ einen Wert. Die Methode <xref:System.IO.Stream.ReadAsync%2A> gibt ein <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>> zurück, sodass die Auswertung von await einen `Int32`-Wert (`numRead`) erzeugt, nachdem der Vorgang abgeschlossen ist. Weitere Informationen finden Sie unter [Async-Rückgabe Typen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
```vb  
Public Async Sub ProcessRead()  
    Dim filePath = "temp2.txt"  
  
    If File.Exists(filePath) = False Then  
        Debug.WriteLine("file not found: " & filePath)  
    Else  
        Try  
            Dim text As String = Await ReadTextAsync(filePath)  
            Debug.WriteLine(text)  
        Catch ex As Exception  
            Debug.WriteLine(ex.Message)  
        End Try  
    End If  
End Sub  
  
Private Async Function ReadTextAsync(filePath As String) As Task(Of String)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Open, FileAccess.Read, FileShare.Read,  
        bufferSize:=4096, useAsync:=True)  
  
        Dim sb As New StringBuilder  
  
        Dim buffer As Byte() = New Byte(&H1000) {}  
        Dim numRead As Integer  
        numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        While numRead <> 0  
            Dim text As String = Encoding.Unicode.GetString(buffer, 0, numRead)  
            sb.Append(text)  
  
            numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        End While  
  
        Return sb.ToString  
    End Using  
End Function  
```  
  
## <a name="parallel-asynchronous-io"></a>Parallele Asynchrone E/A  
 Das folgende Beispiel zeigt die parallele Verarbeitung durch das Schreiben von zehn Textdateien. Die Methode <xref:System.IO.Stream.WriteAsync%2A> gibt für jede Datei eine Aufgabe zurück, die anschließend zu einer Liste von Aufgaben hinzugefügt wird. Die `Await Task.WhenAll(tasks)`-Anweisung beendet die Methode und wird innerhalb der Methode fortgesetzt, wenn die Dateiverarbeitung für alle Aufgaben abgeschlossen ist.  
  
 Im Beispiel werden alle <xref:System.IO.FileStream>-Instanzen in einem `Finally`-Block geschlossen, nachdem die Aufgaben abgeschlossen sind. Wenn jeder `FileStream` stattdessen in einer `Imports`-Anweisung erstellt wurde, kann `FileStream` verworfen werden, bevor die Aufgabe abgeschlossen ist.  
  
 Beachten Sie, dass sich eine Steigerung der Leistung fast ausschließlich aus der parallelen und nicht der asynchronen Verarbeitung ergibt. Die Vorteile der Asynchronie sind, dass sie nicht mehrere Threads und den Benutzeroberflächenthread bindet.  
  
```vb  
Public Async Sub ProcessWriteMult()  
    Dim folder = "tempfolder\"  
    Dim tasks As New List(Of Task)  
    Dim sourceStreams As New List(Of FileStream)  
  
    Try  
        For index = 1 To 10  
            Dim text = "In file " & index.ToString & ControlChars.CrLf  
  
            Dim fileName = "thefile" & index.ToString("00") & ".txt"  
            Dim filePath = folder & fileName  
  
            Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
            Dim sourceStream As New FileStream(filePath,  
                FileMode.Append, FileAccess.Write, FileShare.None,  
                bufferSize:=4096, useAsync:=True)  
  
            Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
            sourceStreams.Add(sourceStream)  
  
            tasks.Add(theTask)  
        Next  
  
        Await Task.WhenAll(tasks)  
    Finally  
        For Each sourceStream As FileStream In sourceStreams  
            sourceStream.Close()  
        Next  
    End Try  
End Sub  
```  
  
 Bei Verwendung der Methoden <xref:System.IO.Stream.WriteAsync%2A> und <xref:System.IO.Stream.ReadAsync%2A> können Sie einen <xref:System.Threading.CancellationToken> angeben, mit dem Sie den Vorgang in der Mitte des Streams beenden können. Weitere Informationen finden Sie unter [Feinabstimmung der Async-Anwendung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) und [Abbruch in verwalteten Threads](../../../../standard/threading/cancellation-in-managed-threads.md).  
  
## <a name="see-also"></a>Siehe auch

- [Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
- [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) (Asynchrone Rückgabetypen (Visual Basic))
- [Ablaufsteuerung in asynchronen Programmen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)
