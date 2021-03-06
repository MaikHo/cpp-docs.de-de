---
title: 'Server: Implementieren eines Servers'
ms.date: 11/04/2016
helpviewer_keywords:
- servers, implementing
- OLE server applications [MFC], implementing OLE servers
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
ms.openlocfilehash: 953d157f4bbad0b460947740a2622074dfc90f4f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308016"
---
# <a name="servers-implementing-a-server"></a>Server: Implementieren eines Servers

Dieser Artikel erläutert den Code, den die MFC-Anwendungs-Assistent für eine visuelle Bearbeitung Serveranwendung erstellt. Wenn Sie nicht der Anwendungs-Assistent verwenden, führt in diesem Artikel die Bereiche, in dem Sie Code zum Implementieren einer Serveranwendung schreiben müssen.

Wenn Sie den Assistenten zum Erstellen eine neuen Serveranwendung verwenden, wird einen erheblichen Teil der Server-spezifischen Code für Sie bereitgestellt. Wenn Sie visual Bearbeitungsfunktionen von Server zu einer vorhandenen Anwendung hinzufügen, müssen Sie den Code duplizieren, den der Anwendungs-Assistent eingegeben haben, wird bevor Sie den Rest des Codes erforderlichen Server hinzufügen.

Der Servercode, den der Anwendungs-Assistent bietet fällt in verschiedene Kategorien:

- Definieren von Serverressourcen:

  - Die Menüressource verwendet, wenn der Server ein eingebettetes Element in einem eigenen Fenster bearbeitet wird.

  - Die Menü- und Symbolleistenobjekte Ressourcen verwendet, wenn der Server direkt aktiv ist.

  Weitere Informationen zu diesen Ressourcen finden Sie unter [Menüs und Ressourcen: Servererweiterungen](../mfc/menus-and-resources-server-additions.md).

- Definieren eine Elementklasse abgeleitet `COleServerItem`. Weitere Informationen zu Server-Elemente, finden Sie unter [Server: Berichtsserverelemente](../mfc/servers-server-items.md).

- Ändern die Basisklasse der Dokumentklasse `COleServerDoc`. Weitere Informationen finden Sie unter [Server: Implementieren von Serverdokumenten](../mfc/servers-implementing-server-documents.md).

- Definieren einer Rahmenfenster Klasse abgeleitet `COleIPFrameWnd`. Weitere Informationen finden Sie unter [Server: Implementieren von Windows für In-Place-Frame-](../mfc/servers-implementing-in-place-frame-windows.md).

- Erstellen in der Datenbank der Windows-Registrierung einen Eintrag für die Serveranwendung aus, und registrieren die neue Instanz des Servers mit dem OLE-System. Weitere Informationen zu diesem Thema finden Sie unter [Registrierung](../mfc/registration.md).

- Initialisieren und starten die Server-Anwendung. Weitere Informationen zu diesem Thema finden Sie unter [Registrierung](../mfc/registration.md).

Weitere Informationen finden Sie unter [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerDoc](../mfc/reference/coleserverdoc-class.md), und [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md) in die *Klassenbibliotheksreferenz*.

## <a name="see-also"></a>Siehe auch

[Server](../mfc/servers.md)<br/>
[Container](../mfc/containers.md)<br/>
[Menüs und Ressourcen (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Registrierung](../mfc/registration.md)
