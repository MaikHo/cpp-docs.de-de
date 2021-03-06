---
title: Einfache Aufgaben
ms.date: 11/04/2016
helpviewer_keywords:
- lightweight tasks
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
ms.openlocfilehash: be417052ffab19c1bc2d2ba6f35094f98e315812
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141848"
---
# <a name="lightweight-tasks"></a>Einfache Aufgaben

Dieses Dokument beschreibt die Rolle von Lightweight-Aufgaben in der Concurrency Runtime. Eine *leichte Aufgabe* ist eine Aufgabe, die Sie direkt von einem `concurrency::Scheduler` oder `concurrency::ScheduleGroup` Objekt aus planen. Eine leichte Aufgabe ähnelt der-Funktion, die Sie der Windows-API-Funktion " [kreatethread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) " bereitstellen. Daher sind Lightweight-Aufgaben nützlich, wenn Sie vorhandenen Code anpassen, um die Planungs Funktionalität des Concurrency Runtime zu verwenden. Der Concurrency Runtime selbst verwendet Lightweight-Aufgaben, um asynchrone Agents zu planen und Nachrichten zwischen asynchronen Nachrichten Blöcken zu senden.

> [!TIP]
> Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner Sie bei der Feinabstimmung der Leistung Ihrer Anwendungen unterstützt, empfehlen wir Ihnen, mit der [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) zu beginnen, wenn Sie mit der Concurrency Runtime noch nicht vertraut sind.

Leichte Aufgaben führen zu weniger Aufwand als asynchrone Agents und Aufgaben Gruppen. Beispielsweise werden Sie von der Laufzeit nicht informiert, wenn eine leichte Aufgabe abgeschlossen ist. Außerdem werden Ausnahmen, die von einer leichten Aufgabe ausgelöst werden, von der Common Language Runtime nicht abgefangen oder behandelt. Weitere Informationen zur Ausnahmebehandlung und zu Lightweight-Aufgaben finden Sie unter [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

Für die meisten Aufgaben wird empfohlen, dass Sie robustere Funktionen wie z. b. Aufgaben Gruppen und parallele Algorithmen verwenden, da Sie komplexe Aufgaben leichter in grundlegende Aufgaben unterteilen können. Weitere Informationen zu Aufgaben Gruppen finden Sie unter [Aufgaben Parallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Weitere Informationen zu parallelen Algorithmen finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).

Um einen Lightweight-Task zu erstellen, rufen Sie die [Concurrency:: ScheduleGroup:: ScheduleTask](reference/schedulegroup-class.md#scheduletask)-, [Concurrency:: CurrentScheduler:: ScheduleTask](reference/currentscheduler-class.md#scheduletask)-Methode oder die [Concurrency:: Scheduler:: ScheduleTask](reference/scheduler-class.md#scheduletask) -Methode auf. Warten Sie, bis der übergeordnete Planer beendet ist, oder verwenden Sie einen Synchronisierungs Mechanismus, wie z. b. ein [parallelcurrency:: Event](../../parallel/concrt/reference/event-class.md) -Objekt, um zu warten, bis eine leichte Aufgabe abgeschlossen ist.

## <a name="example"></a>Beispiel

Ein Beispiel für das Anpassen von vorhandenem Code für die Verwendung einer Lightweight-Aufgabe finden Sie unter Exemplarische Vorgehensweise [: Anpassen von vorhandenem Code für die Verwendung von Lightweight-Aufgaben](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md).

## <a name="see-also"></a>Weitere Informationen

[Aufgabenplanung](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Exemplarische Vorgehensweise: Anpassen von vorhandenem Code für die Verwendung einfacher Aufgaben](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)
