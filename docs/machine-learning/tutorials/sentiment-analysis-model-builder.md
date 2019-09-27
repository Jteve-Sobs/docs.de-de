---
title: 'Tutorial: Analysieren der Stimmung: binäre Klassifikation'
description: Dieses Tutorial zeigt Ihnen, wie Sie eine Razor Pages-Anwendung erstellen, die die Stimmung in Websitekommentaren klassifiziert und die entsprechenden Maßnahmen ergreift. Die binäre Standpunktklassifizierung verwendet den Modell-Generator in Visual Studio.
ms.date: 09/13/2019
author: luisquintanilla
ms.author: luquinta
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c6184e097daf4604173db9e2a34606e68eb0fdc8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054273"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-in-a-web-application-using-mlnet-model-builder"></a>Tutorial: Analysieren der Stimmung von Websitekommentaren in einer Webanwendung mit dem Modell-Generator von ML.NET

Erfahren Sie, wie Sie die Stimmung in Kommentaren in Echtzeit in einer Webanwendung analysiert wird.

Dieses Tutorial zeigt Ihnen, wie Sie eine ASP.NET Core Razor Pages-Anwendung erstellen, die die Stimmung in Websitekommentaren in Echtzeit klassifiziert.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
> * Erstellen einer ASP.NET Core Razor Pages-Anwendung
> * Vorbereiten und Verstehen der Daten
> * Auswählen eines Szenarios
> * Laden der Daten
> * Trainieren des Modells
> * Evaluieren des Modells
> * Verwenden des Modells für Vorhersagen

> [!NOTE]
> Der Modell-Generator befindet sich derzeit in der Vorschauphase.

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples).

## <a name="pre-requisites"></a>Voraussetzungen

Eine Liste der Voraussetzungen und Installationsanweisungen finden Sie in der [Installationsanleitung für den Modell-Generator](../how-to-guides/install-model-builder.md).

## <a name="create-a-razor-pages-application"></a>Erstellen einer Razor Pages Anwendung

1. Erstellen Sie eine **ASP.NET Core Razor Pages-Anwendung**.

    1. Öffnen Sie Visual Studio, und wählen Sie **Datei -> Neu -> Projekt** in der Menüleiste aus. 
    1. Wählen Sie im Dialogfeld „Neues Projekt“ den Knoten **Visual C#** und anschließend den Knoten **Web** aus. 
    1. Wählen Sie dann die Projektvorlage **ASP.NET Core-Webanwendung** aus. 
    1. Geben Sie in das Textfeld **Name** den Namen „SentimentRazor“ ein.
    1. Das Kontrollkästchen **Verzeichnis für Projektmappe erstellen** sollte standardmäßig aktiviert sein. Wenn dies nicht der Fall ist, aktivieren Sie es. 
    1. Klicken Sie auf die Schaltfläche **OK**.
    1. Wählen Sie im Fenster, das die verschiedenen Typen von ASP.NET Core-Projekten anzeigt, **Webanwendung** und dann die Schaltfläche **OK** aus.

## <a name="prepare-and-understand-the-data"></a>Vorbereiten und Verstehen der Daten

Laden Sie das [Wikipedia-detox-Dataset](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv) herunter. Wenn die Webseite geöffnet wird, klicken Sie mit der rechten Maustaste auf die Seite, wählen Sie **Speichern unter** aus, und speichern Sie die Datei auf Ihrem Computer. 

Jede Zeile im Dataset *wikipedia-detox-250-line-data.tsv* stellt einen anderen Kommentar dar, der von einem Benutzer auf Wikipedia verfasst wurde. Die erste Spalte stellt die Stimmung des Texts dar (0 ist nicht toxisch, 1 ist toxisch), und die zweite Spalte stellt den Kommentar dar, den der Benutzer hinterlassen hat. Die Spalten werden durch TAB getrennt. Die Daten sehen folgendermaßen aus:

| Standpunkt | SentimentText |
| :---: | :---: |
1 | ==RUDE== Dude, you are rude upload that carl picture back, or else.
1 | == OK! ==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!!
0 | Ich hoffe, dass dies hilfreich ist.

## <a name="choose-a-scenario"></a>Auswählen eines Szenarios

![](./media/sentiment-analysis-model-builder/model-builder-screen.png)

Um Ihr Modell zu trainieren, wählen Sie ein Szenario aus der Liste der vom Modell-Generator bereitgestellten verfügbaren Machine Learning-Szenarien aus. 

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt *SentimentRazor*, und wählen Sie **Hinzufügen** > **Machine Learning** aus.
1. Für dieses Beispiel ist das Szenario eine Stimmungsanalyse. Wählen Sie im Schritt *Szenario* des Modell-Generator-Tools das Szenario **Standpunktanalyse** aus.

## <a name="load-the-data"></a>Laden der Daten

Der Modell-Generator akzeptiert Daten aus zwei Quellen: aus einer SQL Server-Datenbank oder aus einer lokalen Datei im `csv`- oder `tsv`-Format.

1. Wählen Sie im Schritt „Daten“ des Modell-Generator-Tools die Option **Datei** aus der Dropdownliste „Datenquelle“ aus.
1. Wählen Sie die Schaltfläche neben dem Textfeld **Datei auswählen** aus, und verwenden Sie den Datei-Explorer, um die Datei *wikipedia-detox-250-line-data.tsv* zu suchen und auszuwählen.
1. Wählen Sie **Stimmung** aus der Dropdownliste **Vorherzusagende Bezeichnung oder Spalte** aus.
1. Wählen Sie den Link **Trainieren** aus, um zum nächsten Schritt im Modell-Generator-Tool zu gelangen.

## <a name="train-the-model"></a>Trainieren des Modells

Die in diesem Tutorial zum Trainieren des Preisvorhersagemodells verwendete Machine Learning-Aufgabe ist die binäre Klassifizierung. Während des Modelltrainings trainiert der Modell-Generator einzelne Modelle mit verschiedenen Algorithmen und Einstellungen für binäre Klassifizierung, um das leistungsfähigste Modell für Ihr Dataset zu finden.

Die Zeit, die für das Trainieren des Modells benötigt wird, ist proportional zur Datenmenge. Der Modell-Generator legt automatisch einen Standardwert für **Time to train (seconds)** (Trainingszeit (Sekunden)) basierend auf der Größe der Datenquelle fest. 

1. Obwohl der Modell-Generator den Wert von **Trainingszeit (Sekunden)** auf 10 Sekunden festlegt, erhöhen Sie den Wert auf 30 Sekunden. Ein längeres Training ermöglicht es dem Modell-Generator, eine größere Anzahl von Algorithmen und Kombinationen von Parametern auf der Suche nach dem besten Modell zu untersuchen.
1. Wählen Sie **Training starten** aus.

    Während des gesamten Trainingsprozesses werden die Fortschrittsdaten im Abschnitt `Progress` des Schritts „Trainieren“ angezeigt.

    - „Status“ zeigt den Abschlussstatus des Trainingsprozesses an.
    - „Beste Genauigkeit“ zeigt die Genauigkeit des leistungsfähigsten Modells, das bisher vom Modell-Generator gefunden wurde. Eine höhere Genauigkeit bedeutet, dass die Vorhersage des Modells anhand der Testdaten präziser ist.
    - „Bester Algorithmus“ zeigt den Namen des leistungsfähigsten Algorithmus an, der bisher vom Modell-Generator gefunden wurde.
    - „Letzter Algorithmus“ zeigt den Namen des Algorithmus an, der zuletzt vom Modell-Generator zum Trainieren des Modells verwendet wurde.

1. Wählen Sie nach Abschluss des Trainings den Link **Evaluieren** aus, um mit dem nächsten Schritt fortzufahren.

## <a name="evaluate-the-model"></a>Evaluieren des Modells

Das Ergebnis des Schritts „Trainieren“ ist ein Modell mit der besten Leistung. Der Schritt „Evaluieren“ des Modell-Generator-Tools, der Ausgabebereich, enthält den Algorithmus, der vom leistungsfähigsten Modell im Eintrag **Bestes Modell** verwendet wird, sowie Metriken in **Beste Modellqualität (RSquared)** . Außerdem finden Sie hier eine Übersichtstabelle mit den fünf besten Modellen und deren Metriken.

Wenn Sie mit Ihren Genauigkeitsmetriken nicht zufrieden sind, gibt es einige einfache Möglichkeiten, die Modellgenauigkeit zu verbessern. Dazu müssen Sie die Zeit für das Training des Modells erhöhen oder mehr Daten verwenden. Wählen Sie andernfalls den Link **Code** aus, um zum letzten Schritt im Modell-Generator-Tool zu gelangen.

## <a name="add-the-code-to-make-predictions"></a>Hinzufügen des Codes für Vorhersagen

Das Ergebnis des Trainings sind zwei Projekte.

### <a name="reference-the-trained-model"></a>Verweisen auf das trainierte Modell

1. Wählen Sie im Schritt *Code* des Modell-Generators die Option **Projekte hinzufügen** aus, um der Projektmappe die automatisch generierten Projekte hinzuzufügen.

    Die folgenden Projekte sollten im **Projektmappen-Explorer** angezeigt werden:

    - *SentimentRazorML.ConsoleApp*: Eine .NET Core-Konsolenanwendung, die den Modelltrainings- und Vorhersagecode enthält.
    - *SentimentRazorML.Model*: Eine .NET-Standardklassenbibliothek, die die Datenmodelle enthält, die das Schema der Eingabe- und Ausgabemodelldaten sowie die persistente Version des leistungsfähigsten Modells während des Trainings definieren.

    Für dieses Tutorial wird nur das Projekt *SentimentRazorML.Model* verwendet, da Vorhersagen in der Webanwendung *SentimentRazor* und nicht in der Konsole getroffen werden. Obwohl die *SentimentRazorML.ConsoleApp* nicht für die Bewertung verwendet wird, kann sie verwendet werden, um das Modell zu einem späteren Zeitpunkt mit neuen Daten erneut zu trainieren. Das erneute Trainieren wird in diesem Tutorial jedoch nicht behandelt.

1. Um das trainierte Modell in der Razor Pages-Anwendung zu verwenden, fügen Sie einen Verweis auf das Projekt *SentimentRazorML.Model* hinzu.

    1. Klicken Sie mit der rechten Maustaste auf das Projekt **SentimentRazor**. 
    1. Klicken Sie auf **Hinzufügen > Verweis**. 
    1. Wählen Sie den Knoten **Projekte > Projektmappe** aus, und aktivieren Sie in der Liste das Projekt **SentimentRazorML.Model**.
    1. Klicken Sie auf **OK**.

### <a name="configure-the-predictionengine-pool"></a>Konfigurieren des PredictionEngine-Pools

Sie können [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) verwenden, um eine einzelne Vorhersage zu treffen. Um [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in Ihrer Anwendung verwenden zu können, müssen Sie sie bei Bedarf erstellen. Für diesen Fall hat sich die Abhängigkeitsinjektion bewährt.

> [!WARNING]
> [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher. Verwenden Sie für verbesserte Leistung und Threadsicherheit den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) von `PredictionEngine`-Objekten für die Anwendungsverwendung erstellt. Lesen Sie den folgenden Blogbeitrag, um mehr über das Erstellen und [Verwenden von `PredictionEngine`-Objektpools in ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/) zu erfahren. 

1. Installieren Sie das NuGet-Paket *Microsoft.Extensions.ML*:

    1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. 
    1. Wählen Sie als Paketquelle „nuget.org“ aus. 
    1. Wählen Sie die Registerkarte **Durchsuchen** aus, und suchen Sie nach **Microsoft.Extensions.ML**. 
    1. Wählen Sie das Paket in der Liste aus, und **klicken Sie auf die Schaltfläche** Installieren. 
    1. Klicken Sie im Dialogfeld **Vorschau der Änderungen** auf die Schaltfläche **OK**.
    1. Wählen Sie die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz**, wenn Sie mit den Lizenzbedingungen für die aufgeführten Pakete einverstanden sind. 

1. Öffnen Sie die Datei *Startup.cs* im Projekt *SentimentRazor*.
1. Fügen Sie die folgenden using-Anweisungen hinzu, um auf das NuGet-Paket *Microsoft.Extensions.ML* und auf das Projekt *SentimentRazorML.Model* zu verweisen:

    [!code-csharp [StartupUsings](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L12-L14)]        

1. Erstellen Sie eine globale Variable zum Speichern des Speicherorts der trainierten Modelldatei.

    [!code-csharp [ModelPath](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L20)]

1. Die Modelldatei wird im Buildverzeichnis zusammen mit den Assemblydateien der Anwendung gespeichert. Um den Zugriff zu vereinfachen, erstellen Sie eine Hilfsmethode namens `GetAbsolutePath` nach der `Configure`-Methode.

    [!code-csharp [GetAbsolutePathMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L66-L73)]

1. Verwenden Sie die `GetAbsolutePath`-Methode im `Startup`-Klassenkonstruktor, um `_modelPath` festzulegen.

    [!code-csharp [InitModelPath](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L25)]

1. Konfigurieren Sie den `PredictionEnginePool` für Ihre Anwendung in der `ConfigureServices`-Methode:

    [!code-csharp [InitPredEnginePool](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L42)]

### <a name="create-sentiment-analysis-handler"></a>Erstellen eines Stimmungsanalysehandlers

Vorhersagen werden auf der Hauptseite der Anwendung getroffen. Daher muss eine Methode, die die Benutzereingaben annimmt und `PredictionEnginePool` zum Zurückgeben einer Vorhersage verwendet, hinzugefügt werden.

1. Öffnen Sie die Datei *index.cshtml.cs* im Verzeichnis *Pages*, und fügen Sie die folgenden using-Anweisungen hinzu:

    [!code-csharp [IndexUsings](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L7-L8)]

    Um den `PredictionEnginePool` zu verwenden, der in der `Startup`-Klasse konfiguriert wurde, müssen Sie ihn in den Konstruktor des Modells einschleusen, in dem Sie ihn verwenden möchten. 

1. Fügen Sie eine Variable hinzu, um auf den `PredictionEnginePool` in der `IndexModel`-Klasse zu verweisen.

    [!code-csharp [PredEnginePool](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L14)]

1. Erstellen Sie einen Konstruktor in der `IndexModel`-Klasse, und schleusen Sie den `PredictionEnginePool`-Dienst in diesen ein.

    [!code-csharp [IndexConstructor](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L16-L19)]

1. Erstellen Sie einen Methodenhandler, der den `PredictionEnginePool` verwendet, um Vorhersagen aus Benutzereingaben zu treffen, die von der Webseite empfangen werden.

    1. Erstellen Sie unter der `OnGet`-Methode eine Methode namens `OnGetAnalyzeSentiment`.

        ```csharp
        public IActionResult OnGetAnalyzeSentiment([FromQuery] string text)
        {

        }
        ```

    1. Geben Sie innerhalb der `OnGetAnalyzeSentiment`-Methode die Stimmung *Neutral* zurück, wenn die Eingabe des Benutzers leer oder NULL ist.

        [!code-csharp [InitInput](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L28)] 
    
    1. Erstellen Sie eine neue Instanz von `ModelInput`, wenn Sie über eine gültige Eingabe verfügen. 

        [!code-csharp [InitInput](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L29)] 

    1. Verwenden Sie `PredictionEnginePool` zum Vorhersagen der Stimmung.

        [!code-csharp [MakePrediction](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L30)] 

    1. Konvertieren Sie den vorhergesagten `bool`-Wert mit dem folgenden Code in „toxic“ oder „not toxic“.

        [!code-csharp [ConvertPrediction](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L31)]

    1. Geben Sie die Stimmung schließlich zurück an die Webseite.

        [!code-csharp [ReturnSentiment](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L32)]

### <a name="configure-the-web-page"></a>Konfigurieren der Webseite

Die von `OnGetAnalyzeSentiment` zurückgegebenen Ergebnisse werden dynamisch auf der `Index`-Webseite angezeigt.

1. Öffnen Sie die Datei *Index.cshtml* im Verzeichnis *Pages*, und ersetzen Sie deren Inhalt durch den folgenden Code: 

    [!code-cshtml [IndexPage](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml)]

1. Fügen Sie nun CSS-Formatierungscode am Ende der Seite *site.css* im Verzeichnis *wwwroot\css* hinzu:

    [!code-css [CssStyling](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/css/site.css#L61-L105)]

1. Fügen Sie anschließend Code hinzu, um Eingaben von der Webseite an den `OnGetAnalyzeSentiment`-Handler zu senden.

    1. Erstellen Sie in der Datei *site.js* im Verzeichnis *wwwroot\js* eine Funktion mit dem Namen `getSentiment`, um eine GET HTTP-Anforderung mit der Benutzereingabe an den `OnGetAnalyzeSentiment`-Handler auszugeben.

        [!code-javascript [GetSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L5-L10)]

    1. Fügen Sie darunter eine weitere Funktion mit dem Namen `updateMarker` hinzu, um die Position des Markers auf der Webseite dynamisch zu aktualisieren, wenn die Stimmung vorhergesagt wird.

        [!code-javascript [UpdateMarkerMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L12-L15)]

    1. Erstellen Sie eine Ereignishandlerfunktion namens `updateSentiment`, um die Eingabe vom Benutzer abzurufen, senden Sie diese mithilfe der `getSentiment`-Funktion an die `OnGetAnalyzeSentiment`-Funktion, und aktualisieren Sie den Marker mit der `updateMarker`-Funktion.

        [!code-javascript [UpdateSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L17-L34)]

    1. Registrieren Sie schließlich den Ereignishandler, und binden Sie ihn an das `textarea`-Element mit dem `id=Message`-Attribut.

        [!code-javascript [UpdateSentimentEvtHandler](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L36)]

## <a name="run-the-application"></a>Ausführen der Anwendung

Nachdem Sie Ihre Anwendung eingerichtet haben, führen Sie die Anwendung aus, die in Ihrem Browser gestartet werden sollte.

Wenn die Anwendung gestartet wird, geben Sie *Model Builder ist cool!* in den Textbereich ein. Die vorhergesagte Stimmung sollte *Not Toxic* sein.

![](./media/sentiment-analysis-model-builder/web-app.png)

Wenn Sie zu einem späteren Zeitpunkt innerhalb einer anderen Projektmappe auf die generierten Modell-Generator-Projekte verweisen müssen, finden Sie diese im Verzeichnis `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Erstellen einer ASP.NET Core Razor Pages-Anwendung
> * Vorbereiten und Verstehen der Daten
> * Auswählen eines Szenarios
> * Laden der Daten
> * Trainieren des Modells
> * Evaluieren des Modells
> * Verwenden des Modells für Vorhersagen

### <a name="additional-resources"></a>Zusätzliche Ressourcen

Weitere Informationen zu den in diesem Tutorial erwähnten Themen finden Sie in den folgenden Ressourcen:

- [Szenarien für den Modellgenerator](../automate-training-with-model-builder.md#scenarios)
- [Binäre Klassifizierung](../resources/glossary.md#binary-classification)
- [Metriken des Modells für binäre Klassifizierung](../resources/metrics.md#metrics-for-binary-classification)