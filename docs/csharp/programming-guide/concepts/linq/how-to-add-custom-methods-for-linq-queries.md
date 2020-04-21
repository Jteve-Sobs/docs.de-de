---
title: 'Vorgehensweise: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (C#)'
ms.date: 07/20/2015
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: e16175d3332b6ce36458eaa78af093e4f8772723
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141473"
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a>Vorgehensweise: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (C#)

Sie können die Methoden erweitern, die Sie für LINQ-Abfragen durch Hinzufügen von Erweiterungsmethoden zur <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle verwenden können. Zusätzlich zu den durchschnittlichen oder maximalen Standardvorgängen, können Sie eine benutzerdefinierte Aggregatmethode erstellen, um einen einzelnen Wert aus einer Sequenz von Werten zu berechnen. Sie können auch eine Methode erstellen, die als benutzerdefinierter Filter oder spezifische Datentransformation für eine Sequenz von Werten agiert und eine neue Sequenz zurückgibt. Beispiele für solche Methoden sind <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Reverse%2A>.

Beim Erweitern der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle können Sie die benutzerdefinierten Methoden auf jede aufzählbare Auflistung anwenden. Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../classes-and-structs/extension-methods.md).

## <a name="adding-an-aggregate-method"></a>Hinzufügen einer Aggregatmethode

Eine aggregierte Methode berechnet einen einzelnen Wert aus einer Gruppe von Werten. LINQ stellt mehrere Aggregatmethoden bereit, einschließlich <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> und <xref:System.Linq.Enumerable.Max%2A>. Sie können Ihre eigene Aggregatmethode erstellen, indem Sie der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle eine Erweiterungsmethode hinzufügen.

Im folgenden Codebeispiel wird veranschaulicht, wie eine Erweiterungsmethode namens `Median` erstellt wird, um einen Median für eine Zahlensequenz des Typs `double` zu berechnen.

```csharp
public static class LINQExtension
{
    public static double Median(this IEnumerable<double> source)
    {
        if (source.Count() == 0)
        {
            throw new InvalidOperationException("Cannot compute median for an empty set.");
        }

        var sortedList = from number in source
                         orderby number
                         select number;

        int itemIndex = (int)sortedList.Count() / 2;

        if (sortedList.Count() % 2 == 0)
        {
            // Even number of items.
            return (sortedList.ElementAt(itemIndex) + sortedList.ElementAt(itemIndex - 1)) / 2;
        }
        else
        {
            // Odd number of items.
            return sortedList.ElementAt(itemIndex);
        }
    }
}
```

Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung genau so aufrufen, wie Sie andere Aggregatmethoden aus der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle aufrufen.

Im folgenden Codebeispiel wird die Verwendung der `Median`-Methode für ein Array des Typs `double` veranschaulicht.

```csharp
double[] numbers1 = { 1.9, 2, 8, 4, 5.7, 6, 7.2, 0 };

var query1 = numbers1.Median();

Console.WriteLine("Double: Median = " + query1);
```

```csharp
/*
 This code produces the following output:

 Double: Median = 4.85
*/
```

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>Überladen einer Aggregatmethode zum Akzeptieren verschiedener Typen

Sie können die Aggregatmethode überladen, sodass diese Sequenzen verschiedener Typen akzeptiert. Die Standardmethode ist die Erstellung einer Überladung für jeden Typ. Ein anderer Ansatz ist das Erstellen einer Überladung, die einen generischen Typ annimmt und diesen mit einem Delegaten in einen bestimmten Typ konvertiert. Sie können auch beide Methoden kombinieren.

#### <a name="to-create-an-overload-for-each-type"></a>So erstellen Sie eine Überladung für jeden Typ

Sie können eine bestimmte Überladung für jeden Typ erstellen, den Sie unterstützen möchten. Im folgenden Codebeispiel wird eine Überladung der `Median`-Methode für den `integer`-Typ veranschaulicht.

```csharp
//int overload

public static double Median(this IEnumerable<int> source)
{
    return (from num in source select (double)num).Median();
}
```

Sie können nun die `Median`-Überladungen für die `integer`- und `double`-Typen aufrufen, so wie im folgenden Code gezeigt:

```csharp
double[] numbers1 = { 1.9, 2, 8, 4, 5.7, 6, 7.2, 0 };

var query1 = numbers1.Median();

Console.WriteLine("Double: Median = " + query1);
```

```csharp
int[] numbers2 = { 1, 2, 3, 4, 5 };

var query2 = numbers2.Median();

Console.WriteLine("Integer: Median = " + query2);
```

```csharp
/*
 This code produces the following output:

 Double: Median = 4.85
 Integer: Median = 3
*/
```

#### <a name="to-create-a-generic-overload"></a>So erstellen Sie eine generische Überladung

Sie können auch eine Überladung erstellen, die eine Sequenz generischer Objekte akzeptiert. Diese Überladung nimmt einen Delegaten als Parameter und verwendet ihn, um eine Sequenz von Objekten eines generischen Typs in einen bestimmten Typ zu konvertieren.

Der folgende Code zeigt eine Überladung der `Median`-Methode, die den <xref:System.Func%602>-Delegaten als Parameter akzeptiert. Dieser Delegat übernimmt ein Objekt des generischen Typs „T“ und gibt ein Objekt vom Typ `double` zurück.

```csharp
// Generic overload.

public static double Median<T>(this IEnumerable<T> numbers,
                       Func<T, double> selector)
{
    return (from num in numbers select selector(num)).Median();
}
```

Sie können nun die `Median`-Methode für eine Sequenz von Objekten beliebigen Typs aufrufen. Wenn der Typ nicht über eine eigene Methodenüberladung verfügt, müssen sie einen Delegatenparameter übergeben. In C# können Sie zu diesem Zweck einen Lambdaausdruck verwenden. Wenn Sie die `Aggregate`- oder `Group By`-Klausel anstatt des Methodenaufrufs verwenden, können Sie auch einen beliebigen Wert oder Ausdruck übergeben, der im Bereich dieser Klausel vorhanden ist. Diese Methode ist nur in Visual Basic verfügbar.

Der folgende Beispielcode veranschaulicht, wie eine `Median`-Methode für ein Array aus ganzen Zahlen und ein Array aus Zeichenfolgen aufgerufen wird. Für Zeichenfolgen wird der Median für die Längen der Zeichenfolgen im Array berechnet. Das Beispiel zeigt, wie der Delegatparameter <xref:System.Func%602> an die `Median`-Methode für jeden Fall übergeben wird.

```csharp
int[] numbers3 = { 1, 2, 3, 4, 5 };

/*
  You can use the num=>num lambda expression as a parameter for the Median method
  so that the compiler will implicitly convert its value to double.
  If there is no implicit conversion, the compiler will display an error message.
*/

var query3 = numbers3.Median(num => num);

Console.WriteLine("Integer: Median = " + query3);

string[] numbers4 = { "one", "two", "three", "four", "five" };

// With the generic overload, you can also use numeric properties of objects.

var query4 = numbers4.Median(str => str.Length);

Console.WriteLine("String: Median = " + query4);

/*
 This code produces the following output:

 Integer: Median = 3
 String: Median = 4
*/
```

## <a name="adding-a-method-that-returns-a-collection"></a>Hinzufügen einer Methode, die eine Auflistung zurückgibt

Sie können die Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> mit einer benutzerdefinierten Abfragemethode erweitern, die eine Sequenz von Werten zurückgibt. In diesem Fall muss die Methode eine Auflistung des Typs <xref:System.Collections.Generic.IEnumerable%601> zurückgeben. Solche Methoden können verwendet werden, um Filter oder Datentransformationen auf eine Sequenz von Werten anzuwenden.

Das folgende Beispiel zeigt, wie eine Erweiterungsmethode mit dem Namen `AlternateElements` erstellt wird, die jedes andere Element in einer Auflistung zurückgibt, beginnend mit dem ersten Element.

```csharp
// Extension method for the IEnumerable<T> interface.
// The method returns every other element of a sequence.

public static IEnumerable<T> AlternateElements<T>(this IEnumerable<T> source)
{
    List<T> list = new List<T>();

    int i = 0;

    foreach (var element in source)
    {
        if (i % 2 == 0)
        {
            list.Add(element);
        }

        i++;
    }

    return list;
}
```

Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung genau so aufrufen, wie Sie andere Methoden aus der Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> aufrufen, so wie im folgenden Code dargestellt:

```csharp
string[] strings = { "a", "b", "c", "d", "e" };

var query = strings.AlternateElements();

foreach (var element in query)
{
    Console.WriteLine(element);
}
/*
 This code produces the following output:

 a
 c
 e
*/
```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Collections.Generic.IEnumerable%601>
- [Erweiterungsmethoden](../../classes-and-structs/extension-methods.md)
