---
title: 'Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 218dbb52abc0100724d38d10be91ef24252d5226
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349720"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt (Visual Basic)
Sie verwenden eine `Function` Prozedur, um einen Wert an den aufrufenden Code zurückzugeben.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>So erstellen Sie eine Prozedur, die einen Wert zurückgibt  
  
1. Verwenden Sie außerhalb einer anderen Prozedur eine `Function`-Anweisung, gefolgt von einer `End Function`-Anweisung.  
  
2. Befolgen Sie in der `Function`-Anweisung das `Function`-Schlüsselwort mit dem Namen der Prozedur und anschließend die Parameterliste in Klammern.  
  
3. Folgen Sie den Klammern mit einer `As`-Klausel, um den Datentyp des zurückgegebenen Werts anzugeben.  
  
4. Platzieren Sie die Code Anweisungen der Prozedur zwischen den Anweisungen `Function` und `End Function`.  
  
5. Verwenden Sie eine `Return`-Anweisung, um den Wert an den aufrufenden Code zurückzugeben.  
  
     Mit der folgenden `Function` Prozedur wird die längste Seite (Hypotenuse) eines Rechts Dreiecks berechnet, wobei die Werte für die beiden anderen Seiten angegeben werden.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     Das folgende Beispiel zeigt einen typischen `hypotenuse`-Aufruf.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Gewusst wie: Abrufen eines Werts aus einer Prozedur](./how-to-return-a-value-from-a-procedure.md)
- [Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)
