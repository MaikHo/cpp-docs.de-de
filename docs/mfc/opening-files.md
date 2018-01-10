---
title: "Öffnen von Dateien | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Open member functions [MFC]
- CFile class [MFC], variable
- opening files, in MFC
- Open calls [MFC]
- Open method, CFile class [MFC]
- examples [MFC], opening files
- opening files, handling exceptions
- exception handling [MFC], when opening files
- files [MFC], opening
- file objects [MFC]
- MFC, file operations
- opening files [MFC]
- exception handling [MFC], opening files
ms.assetid: a991b8ec-b04a-4766-b47e-7485b5dd0b01
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ebc650aa4a3f13a0cbc9d9b0026d948d64ae8b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="opening-files"></a>Öffnen von Dateien
In MFC ist die gängigste Methode zum Öffnen einer Datei ein zweistufiger Prozess.  
  
#### <a name="to-open-a-file"></a>Öffnen eine Datei  
  
1.  Erstellen Sie das Objekt "Datei" ohne einen Pfad oder Berechtigungsflags anzugeben.  
  
     Sie erstellen ein Objekt "Datei" in der Regel durch Deklarieren einer [CFile](../mfc/reference/cfile-class.md) Variablen im Stapelrahmen.  
  
2.  Rufen Sie die [öffnen](../mfc/reference/cfile-class.md#open) Memberfunktion für das Objekt "Datei", einen Pfad und Berechtigungsflags bereitstellt.  
  
     Der Rückgabewert für `Open` ist ungleich NULL, wenn die Datei erfolgreich geöffnet wurde oder gleich 0 sein, wenn die angegebene Datei konnte nicht geöffnet werden. Die `Open` Memberfunktion ist der Prototyp wie folgt:  
  
     `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`  
  
     Die open-Flags festlegen, welche Berechtigungen, z. B. schreibgeschützt, Sie möchten, für die Datei. Die möglichen Flagwerte sind definiert als aufgezählte Konstanten in der `CFile` Klasse, damit sie mit qualifiziert sind "`CFile::`" wie in `CFile::modeRead`. Verwenden der `CFile::modeCreate` auszugeben, wenn Sie die Datei erstellen möchten.  
  
 Im folgende Beispiel veranschaulicht das Erstellen einer neuen Datei mit Lese-/Schreibberechtigung (Ersetzen eine vorhandene Datei mit dem gleichen Pfad):  
  
 [!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]  
  
> [!NOTE]
>  In diesem Beispiel erstellt und öffnet eine Datei. Wenn Probleme auftreten, die `Open` Aufruf zurückgeben kann ein `CFileException` Objekt in der letzten Parameter, wie hier gezeigt. Die `TRACE` Makro druckt den Dateinamen und einen Code, der angibt, der Ursache für Fehler. Sie erreichen die `AfxThrowFileException` funktioniert, wenn gewünscht, ausführlichere-Fehlerberichterstattung.  
  
## <a name="see-also"></a>Siehe auch  
 [CFile-Klasse](../mfc/reference/cfile-class.md)   
 [CFile::Open](../mfc/reference/cfile-class.md#open)   
 [Dateien](../mfc/files-in-mfc.md)
