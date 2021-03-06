---
title: Streamoperationen in RichEdit-Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- CRichEditCtrl class [MFC], stream operations
- CRichEditCtrl class [MFC], stream storage
- rich edit controls [MFC], stream operations
- storage, stream in CRichEditCtrl
- stream operations in CRichEditCtrl
- stream storage and CRichEditCtrl
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
ms.openlocfilehash: 73277f59dc0ad4dfe21d481d0b893903ed407ea9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512940"
---
# <a name="stream-operations-in-rich-edit-controls"></a>Streamoperationen in RichEdit-Steuerelementen

Sie können Datenströme zum Übertragen von Daten in ein oder aus einem Rich-Edit-Steuerelement ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) verwenden. Ein Stream wird durch eine [editstream](/windows/win32/api/richedit/ns-richedit-editstream) -Struktur definiert, die einen Puffer und eine Anwendungs definierte Rückruffunktion angibt.

Verwenden Sie zum Lesen von Daten in ein Rich-Edit-Steuerelement (d. h. zum Streamen der Daten in) die Funktion " [StreamIn](../mfc/reference/cricheditctrl-class.md#streamin) -Member". Das-Steuerelement ruft wiederholt die Anwendungs definierte Rückruffunktion auf, die jedes Mal einen Teil der Daten in den Puffer überträgt.

Um den Inhalt eines Rich-Edit-Steuer Elements (d. h. das Streamen der Daten) zu speichern, können Sie die Funktion " [StreamOut](../mfc/reference/cricheditctrl-class.md#streamout) -Member" verwenden. Das-Steuerelement schreibt wiederholt in den Puffer und ruft dann die Anwendungs definierte Rückruffunktion auf. Für jeden-Befehl speichert die Rückruffunktion den Inhalt des Puffers.

## <a name="see-also"></a>Siehe auch

[Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
