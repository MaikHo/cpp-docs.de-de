---
title: Speichern und Laden eines CObject per Archiv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CObject
dev_langs: C++
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 987f754ccdf03e5a252feae693a1f7718da1b353
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>Speichern und Laden eines CObject per Archiv
Speichern und Laden von `CObject`s per Archiv muss zusätzliche berücksichtigt werden. In bestimmten Fällen sollten Sie Aufrufen der `Serialize` Funktion des Objekts, in dem die `CArchive` Objekt ist ein Parameter der der `Serialize` Aufruf, im Gegensatz zur Verwendung der  **< \<**  oder  **>>**  Operator über die `CArchive`. Wichtig zu bedenken ist, die die `CArchive`  **>>**  Operator Konstrukte der `CObject` im Arbeitsspeicher, die basierend auf `CRuntimeClass` Informationen, die zuvor durch das Speichern von Archiv in die Datei geschrieben.  
  
 Deshalb gibt an, ob Sie verwenden die `CArchive`  **< \<**  und  **>>**  Operatoren, im Vergleich zur aufrufenden `Serialize`, davon abhängig, ob Sie *müssen* laden Archiv, dass das Objekt dynamisch zu rekonstruieren basierend auf zuvor gespeicherte `CRuntimeClass` Informationen. Verwenden der `Serialize` Funktion in den folgenden Fällen:  
  
-   Das Objekt deserialisiert wird, wird die genaue Klasse des Objekts im Voraus kennen.  
  
-   Wenn das Objekt deserialisiert wird, verfügen Sie bereits für dieses Volume zugewiesene Arbeitsspeicher.  
  
> [!CAUTION]
>  Wenn Sie das Objekt mit laden die `Serialize` -Funktion, Sie müssen auch speichern, das mit der `Serialize` Funktion. Mit Speichern nicht die `CArchive`  **<<**  -Operator, und klicken Sie dann mit der `Serialize` Funktion ein, oder speichern Sie die Verwendung der `Serialize` Funktion, und Laden Sie mit **CArchive >>**Operator.  
  
 Das folgende Beispiel veranschaulicht die Fälle:  
  
 [!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]  
  
 [!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]  
  
 Zusammengefasst, wenn die serialisierbare Klasse ein eingebetteter definiert **CObject**t als Mitglied ist, sollten Sie *nicht* verwenden die `CArchive`  **< \<**  und  **>>**  Operatoren für das Objekt, aber Sie sollten Aufrufen der `Serialize` stattdessen-Funktion. Auch wenn die serialisierbare Klasse definiert, einen Zeiger auf eine `CObject` (oder ein Objekt abgeleitet `CObject`) als ein Element, aber Konstrukte dieses Objekt in einem eigenen Konstruktor, Sie sollten auch aufrufen, `Serialize`.  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)
