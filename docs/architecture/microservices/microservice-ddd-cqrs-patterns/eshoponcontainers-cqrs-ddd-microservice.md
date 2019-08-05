---
title: Anwenden von CQRS- und CQS-Ansätzen in einem DDD-Microservice in eShopOnContainers
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über die Implementierung von CQRS im Microservice für Bestellungen in eShopOnContainers
ms.date: 10/08/2018
ms.openlocfilehash: 0380e759595e8a159e89f858a5ced4dacfa4e9b4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68674127"
---
# <a name="apply-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a><span data-ttu-id="d8195-103">Anwenden von CQRS- und CQS-Ansätzen in einem DDD-Microservice in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="d8195-103">Apply CQRS and CQS approaches in a DDD microservice in eShopOnContainers</span></span>

<span data-ttu-id="d8195-104">Die Struktur des Microservices für Bestellungen in der Referenzanwendung „eShopOnContainers“ basiert auf CQRS-Prinzipien.</span><span class="sxs-lookup"><span data-stu-id="d8195-104">The design of the ordering microservice at the eShopOnContainers reference application is based on CQRS principles.</span></span> <span data-ttu-id="d8195-105">Allerdings wird darin der einfachste Ansatz verwendet, bei dem Abfragen von Befehlen getrennt werden und dieselbe Datenbank für beide Aktionen dient.</span><span class="sxs-lookup"><span data-stu-id="d8195-105">However, it uses the simplest approach, which is just separating the queries from the commands and using the same database for both actions.</span></span>

<span data-ttu-id="d8195-106">Das Wesentliche dieser Muster und der wichtige Punkt bestehen hier darin, dass Abfragen idempotent sind: unabhängig davon, wie oft Sie Abfragen an ein System richten, ändert sich der Status des entsprechenden Systems nicht.</span><span class="sxs-lookup"><span data-stu-id="d8195-106">The essence of those patterns, and the important point here, is that queries are idempotent: no matter how many times you query a system, the state of that system won't change.</span></span> <span data-ttu-id="d8195-107">Das heißt, Abfragen haben keine Nebeneffekte.</span><span class="sxs-lookup"><span data-stu-id="d8195-107">In other words, queries are side-effect free.</span></span>

<span data-ttu-id="d8195-108">Darum könnten Sie auch ein anderes „reads“-Datenmodell als das transaktionslogische „writes“-Domänenmodell verwenden, obwohl die Microservices für Bestellungen dieselbe Datenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8195-108">Therefore, you could use a different “reads” data model than the transactional logic “writes” domain model, even though the ordering microservices are using the same database.</span></span> <span data-ttu-id="d8195-109">Daher ist es ein vereinfachter CQRS-Ansatz.</span><span class="sxs-lookup"><span data-stu-id="d8195-109">Hence, this is a simplified CQRS approach.</span></span>

<span data-ttu-id="d8195-110">Befehle, die Transaktionen und Datenupdates auslösen, ändern wiederum den Zustand im System.</span><span class="sxs-lookup"><span data-stu-id="d8195-110">On the other hand, commands, which trigger transactions and data updates, change state in the system.</span></span> <span data-ttu-id="d8195-111">Mit Befehlen müssen Sie im Zusammenhang mit Komplexität und sich kontinuierlich ändernden Geschäftsregeln sorgfältig umgehen.</span><span class="sxs-lookup"><span data-stu-id="d8195-111">With commands, you need to be careful when dealing with complexity and ever-changing business rules.</span></span> <span data-ttu-id="d8195-112">An dieser Stelle können Sie DDD-Techniken anwenden, um das System besser zu modellieren.</span><span class="sxs-lookup"><span data-stu-id="d8195-112">This is where you want to apply DDD techniques to have a better modeled system.</span></span>

<span data-ttu-id="d8195-113">Die in diesem Leitfaden vorgestellten DDD-Muster sollten nicht universell angewendet werden,</span><span class="sxs-lookup"><span data-stu-id="d8195-113">The DDD patterns presented in this guide should not be applied universally.</span></span> <span data-ttu-id="d8195-114">denn sie wirken sich negativ auf Ihren Entwurf aus.</span><span class="sxs-lookup"><span data-stu-id="d8195-114">They introduce constraints on your design.</span></span> <span data-ttu-id="d8195-115">Diese Einschränkungen haben zwar Vorteile wie höhere Qualität im Laufe der Zeit, vor allem bei Befehlen und anderen Codezeilen, die den Systemstatus ändern,</span><span class="sxs-lookup"><span data-stu-id="d8195-115">Those constraints provide benefits such as higher quality over time, especially in commands and other code that modifies system state.</span></span> <span data-ttu-id="d8195-116">erhöhen jedoch auch die Komplexität, was Nachteile für das Lesen und Abfragen von Daten hat.</span><span class="sxs-lookup"><span data-stu-id="d8195-116">However, those constraints add complexity with fewer benefits for reading and querying data.</span></span>

<span data-ttu-id="d8195-117">Ein solches Muster ist das Aggregatmuster, das wir in späteren Abschnitten kennenlernen.</span><span class="sxs-lookup"><span data-stu-id="d8195-117">One such pattern is the Aggregate pattern, which we examine more in later sections.</span></span> <span data-ttu-id="d8195-118">Beim Aggregatmuster werden viele Domänenobjekte aufgrund ihrer Beziehung zur Domäne als eine einzelne Einheit behandelt.</span><span class="sxs-lookup"><span data-stu-id="d8195-118">Briefly, in the Aggregate pattern, you treat many domain objects as a single unit as a result of their relationship in the domain.</span></span> <span data-ttu-id="d8195-119">In Abfragen ist dieses Muster nicht immer vorteilhaft, da es die Komplexität der Abfragelogik verkomplizieren kann.</span><span class="sxs-lookup"><span data-stu-id="d8195-119">You might not always gain advantages from this pattern in queries; it can increase the complexity of query logic.</span></span> <span data-ttu-id="d8195-120">Bei schreibgeschützten Abfragen werden viele Objekte nicht als einzelnes Aggregat behandelt.</span><span class="sxs-lookup"><span data-stu-id="d8195-120">For read-only queries, you do not get the advantages of treating multiple objects as a single Aggregate.</span></span> <span data-ttu-id="d8195-121">In diesem Fall erhöht sich nur die Komplexität.</span><span class="sxs-lookup"><span data-stu-id="d8195-121">You only get the complexity.</span></span>

<span data-ttu-id="d8195-122">Wie in Abbildung 7-2 dargestellt, empfiehlt dieser Leitfaden, DDD-Muster nur im Transaktions-/Updatebereich Ihres Microservices zu verwenden, d.h. durch Befehle ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d8195-122">As shown in Figure 7-2, this guide suggests using DDD patterns only in the transactional/updates area of your microservice (that is, as triggered by commands).</span></span> <span data-ttu-id="d8195-123">Abfragen können einem einfacheren Ansatz folgen und sollten im Sinne des CQRS-Ansatzes von Befehlen getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="d8195-123">Queries can follow a simpler approach and should be separated from commands, following a CQRS approach.</span></span>

<span data-ttu-id="d8195-124">Bei der Implementierung der Abfrageseite können Sie zwischen vielen Ansätzen wählen, z.B. ein vollständiger ORM wie EF Core, AutoMapper-Projektionen, gespeicherte Prozeduren, Ansichten, materialisierte Sichten oder ein Mikro-ORM.</span><span class="sxs-lookup"><span data-stu-id="d8195-124">For implementing the “queries side”, you can choose between many approaches, from your full-blown ORM like EF Core, AutoMapper projections, stored procedures, views, materialized views or a micro ORM.</span></span>

<span data-ttu-id="d8195-125">In diesem Leitfaden und in eShopOnContainers (insbesondere beim Microservice für Bestellungen) implementieren wir direkte Abfragen mit dem Mikro-ORM [Dapper](https://github.com/StackExchange/dapper-dot-net).</span><span class="sxs-lookup"><span data-stu-id="d8195-125">In this guide and in eShopOnContainers (specifically the ordering microservice) we chose to implement straight queries using a micro ORM like [Dapper](https://github.com/StackExchange/dapper-dot-net).</span></span> <span data-ttu-id="d8195-126">So können Sie jede Abfrage auf SQL-Anweisungen basierend implementieren, um aufgrund des schlanken Frameworks mit äußerst wenig Mehraufwand eine optimale Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="d8195-126">This lets you implement any query based on SQL statements to get the best performance, thanks to a light framework with very little overhead.</span></span>

<span data-ttu-id="d8195-127">Hinweis: Wenn Sie so vorgehen, erfordern alle Updates für das Modell, die in einer SQL-Datenbank aufbewahrt werden, auch separate Updates für SQL-Abfragen, die von Dapper oder anderen Abfrageansätzen (nicht EF) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d8195-127">Note that when you use this approach, any updates to your model that impact how entities are persisted to a SQL database also need separate updates to SQL queries used by Dapper or any other separate (non-EF) approaches to querying.</span></span>

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a><span data-ttu-id="d8195-128">CQRS und DDD-Muster sind keine Architekturen oberster Ebene</span><span class="sxs-lookup"><span data-stu-id="d8195-128">CQRS and DDD patterns are not top-level architectures</span></span>

<span data-ttu-id="d8195-129">CQRS und die meisten DDD-Muster (z.B. DDD-Ebenen oder ein Domänenmodell mit Aggregaten) sind keine Architekturstile, sondern lediglich Architekturmuster.</span><span class="sxs-lookup"><span data-stu-id="d8195-129">It's important to understand that CQRS and most DDD patterns (like DDD layers or a domain model with aggregates) are not architectural styles, but only architecture patterns.</span></span> <span data-ttu-id="d8195-130">Microservices, SOA und ereignisgesteuerte Architekturen (Event-Driven Architecture, EDA) sind Beispiele für Architekturstile,</span><span class="sxs-lookup"><span data-stu-id="d8195-130">Microservices, SOA, and event-driven architecture (EDA) are examples of architectural styles.</span></span> <span data-ttu-id="d8195-131">denn Sie beschreiben ein System mit vielen Komponenten, z.B. viele Microservices.</span><span class="sxs-lookup"><span data-stu-id="d8195-131">They describe a system of many components, such as many microservices.</span></span> <span data-ttu-id="d8195-132">CQRS und DDD-Muster beschreiben etwas innerhalb eines einzelnen Systems oder einer einzelnen Komponente, in diesem Fall etwas in einem Microservice.</span><span class="sxs-lookup"><span data-stu-id="d8195-132">CQRS and DDD patterns describe something inside a single system or component; in this case, something inside a microservice.</span></span>

<span data-ttu-id="d8195-133">Unterschiedliche Kontextgrenzen (Bounded Contexts, BCs) wenden außerdem verschiedene Muster an.</span><span class="sxs-lookup"><span data-stu-id="d8195-133">Different Bounded Contexts (BCs) will employ different patterns.</span></span> <span data-ttu-id="d8195-134">Sie haben unterschiedliche Aufgaben, und das führt häufig zu unterschiedlichen Lösungen.</span><span class="sxs-lookup"><span data-stu-id="d8195-134">They have different responsibilities, and that leads to different solutions.</span></span> <span data-ttu-id="d8195-135">Wenn überall dasselbe Muster erzwungen wird, führt das jedoch zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="d8195-135">It is worth emphasizing that forcing the same pattern everywhere leads to failure.</span></span> <span data-ttu-id="d8195-136">Daher sollten Sie dies auf keinen Fall tun.</span><span class="sxs-lookup"><span data-stu-id="d8195-136">Do not use CQRS and DDD patterns everywhere.</span></span> <span data-ttu-id="d8195-137">Viele Teilsysteme, BCs oder Microservices sind einfacher und können leichter mithilfe einfacher CRUD-Dienste oder einer anderen Lösung implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d8195-137">Many subsystems, BCs, or microservices are simpler and can be implemented more easily using simple CRUD services or using another approach.</span></span>

<span data-ttu-id="d8195-138">Es gibt nur eine Anwendungsarchitektur: die Architektur der System- oder der End-to-End-Anwendung, die Sie gerade entwerfen (z.B. die Microservicesarchitektur).</span><span class="sxs-lookup"><span data-stu-id="d8195-138">There is only one application architecture: the architecture of the system or end-to-end application you are designing (for example, the microservices architecture).</span></span> <span data-ttu-id="d8195-139">Der Entwurf der einzelnen Kontextgrenzen oder Microservices in dieser Anwendung spiegelt die eigenen Vor-und Nachteile und die interne Entwurfsentscheidungen auf Ebene der Musterarchitektur wider.</span><span class="sxs-lookup"><span data-stu-id="d8195-139">However, the design of each Bounded Context or microservice within that application reflects its own tradeoffs and internal design decisions at an architecture patterns level.</span></span> <span data-ttu-id="d8195-140">Wenden Sie auf keinen Fall überall dieselben Architekturmuster wie CQRS oder DDD an.</span><span class="sxs-lookup"><span data-stu-id="d8195-140">Do not try to apply the same architectural patterns like CQRS or DDD everywhere.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d8195-141">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d8195-141">Additional resources</span></span>

- <span data-ttu-id="d8195-142">**Martin Fowler. CQRS** </span><span class="sxs-lookup"><span data-stu-id="d8195-142">**Martin Fowler. CQRS** </span></span>\
  <https://martinfowler.com/bliki/CQRS.html>

- <span data-ttu-id="d8195-143">**Greg Young. CQRS Documents (CQRS-Dokumente)**  </span><span class="sxs-lookup"><span data-stu-id="d8195-143">**Greg Young. CQRS Documents** </span></span>\
  <https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf>

- <span data-ttu-id="d8195-144">**Udi Dahan. Clarified CQRS (Erläuterung zu CQRS)**  </span><span class="sxs-lookup"><span data-stu-id="d8195-144">**Udi Dahan. Clarified CQRS** </span></span>\
  <http://udidahan.com/2009/12/09/clarified-cqrs/>

>[!div class="step-by-step"]
><span data-ttu-id="d8195-145">[Zurück](apply-simplified-microservice-cqrs-ddd-patterns.md)
>[Weiter](cqrs-microservice-reads.md)</span><span class="sxs-lookup"><span data-stu-id="d8195-145">[Previous](apply-simplified-microservice-cqrs-ddd-patterns.md)
[Next](cqrs-microservice-reads.md)</span></span>