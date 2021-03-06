---
title: Parametervalidierung
ms.date: 11/04/2016
helpviewer_keywords:
- parameters, validation
ms.assetid: 019dd5f0-dc61-4d2e-b4e9-b66409ddf1f2
ms.openlocfilehash: 2c7b2ae50fdcbf59cd23cc309a4ddc4c0803e24e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57748423"
---
# <a name="parameter-validation"></a>Parametervalidierung

Die meisten der CRT-Funktionen mit erweiterter Sicherheit und viele der vorhandenen Funktionen überprüfen ihre Parameter. Dazu gehört die Überprüfung von Zeigern auf **NULL**, die Überprüfung, ob ganze Zahlen im gültigen Bereich liegen, und die Überprüfung der Gültigkeit von Enumerationswerten. Wenn ein ungültiger Parameter gefunden wird, wird der ungültige Parameterhandler ausgeführt.

## <a name="invalid-parameter-handler-routine"></a>Routine für ungültige Parameterhandler

Wenn eine C-Laufzeitbibliotheksfunktion einen ungültigen Parameter erkennt, erfasst sie einige Informationen über den Fehler, ruft dann ein Makro auf, das eine Verteilerfunktion für ungültige Parameterhandler umschließt, eine [_invalid_parameter](../c-runtime-library/reference/invalid-parameter-functions.md), [_invalid_parameter_noinfo](../c-runtime-library/reference/invalid-parameter-functions.md) oder [_invalid_parameter_noinfo_noreturn](../c-runtime-library/reference/invalid-parameter-functions.md). Die aufgerufene Verteilerfunktion hängt davon ab, ob Ihr Code ein Debugbuild oder eine Verkaufsversion ist oder der Fehler als nicht wiederherstellbar gilt.

In Debugbuilds löst das ungültige Parametermakro in der Regel eine fehlgeschlagene Assertion und einen Debughaltepunkt aus, bevor die Verteilerfunktion aufgerufen wird. Wenn der Code ausgeführt wird, kann die Assertion für den Benutzer in einem Dialogfeld gemeldet werden, das über „Abbrechen“, „Wiederholen“, und „Fortsetzen“ oder ähnliche Möglichkeiten verfügt, je nach Betriebssystem und Laufzeitbibliotheksversion. Diese Optionen ermöglichen dem Benutzer das unmittelbare Beenden eines Programms, das Anfügen eines Debuggers, oder die fortlaufende Ausführung eines Codes, der die Verteilerfunktion aufruft.

Dagegen ruft die Verteilerfunktion des ungültigen Parameterhandlers den momentan zugewiesenen ungültigen Parameterhandler auf. Der ungültige Parameter ruft standardmäßig `_invoke_watson` auf, worauf die Anwendung „abstürzt“, das heißt, sie wird beendet und ein Minidump wird erstellt. Wenn durch das Betriebssystem aktiviert, fragt ein Dialogfeld den Benutzer, ob er das Absturzbild zur Analyse an Microsoft senden möchte.

Dieses Verhalten kann geändert werden, indem die Funktionen [_set_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) oder [_set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) verwendet werden, um den ungültigen Parameterhandler auf Ihre eigene Funktion festzulegen. Wenn die Funktion, die Sie angeben, die Anwendung nicht beendet, wird die Steuerung an die Funktion zurückgegeben, die ungültige Parameter empfangen hat. Normalerweise stellen diese Funktionen die Ausführung in CRT ein. Legen Sie `errno` auf einen Fehlercode fest, und geben Sie einen Fehlercode zurück. In vielen Fällen sind der `errno`-Wert und der Rückgabewert beide `EINVAL`, was einen ungültigen Parameter angibt. In einigen Fällen wird ein spezifischerer Fehlercode zurückgegeben, wie z.B. `EBADF` für einen ungültigen Dateizeiger, der als Parameter übergeben wird. Weitere Informationen zu `errno` finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="see-also"></a>Siehe auch

[Sicherheitsfunktionen in der CRT](../c-runtime-library/security-features-in-the-crt.md)<br/>
[CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)
