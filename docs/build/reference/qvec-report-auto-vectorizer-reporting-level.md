---
title: /Qvec-report (Auto-Vectorizer-Berichtsebene)
ms.date: 11/04/2016
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
ms.openlocfilehash: 2007e80db0ee0aec362869315767505ec06ab109
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836867"
---
# <a name="qvec-report-auto-vectorizer-reporting-level"></a>/Qvec-report (Auto-Vectorizer-Berichtsebene)

Aktiviert die Berichterstattungs Funktion des [automatischen-Vektorisierungs](../../parallel/auto-parallelization-and-auto-vectorization.md) Moduls und gibt die Ebene der Informationsmeldungen für die Ausgabe während der Kompilierung an.

## <a name="syntax"></a>Syntax

```
/Qvec-report:{1}{2}
```

## <a name="remarks"></a>Bemerkungen

**/Qvec-Report: 1**<br/>
Gibt eine Informations Meldung für Schleifen aus, die vektorisiert sind.

**/Qvec-Report: 2**<br/>
Gibt eine Informations Meldung für Schleifen aus, die vektorisiert sind, sowie für Schleifen, die nicht vektorisiert sind, sowie einen Ursachen Code.

Weitere Informationen zu Ursachen Codes und Meldungen finden Sie unter [vektorizer-und parallelizer-Meldungen](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

### <a name="to-set-the-qvec-report-compiler-option-in-visual-studio"></a>So legen Sie die/Qvec-Report-Compileroption in Visual Studio fest

1. Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.

1. Wählen Sie im Dialogfeld **Eigenschaften Seiten** unter **C/C++** die Option **Befehlszeile**aus.

1. Geben Sie im Feld **zusätzliche Optionen** `/Qvec-report:1` oder ein `/Qvec-report:2` .

### <a name="to-set-the-qvec-report-compiler-option-programmatically"></a>So legen Sie die/Qvec-Report-Compileroption Programm gesteuert fest

- Verwenden Sie hierzu das Codebeispiel unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Weitere Informationen

[/Q-Optionen (Vorgänge auf niedriger Ebene)](q-options-low-level-operations.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[MSVC-compilerbefehlszeilensyntax](compiler-command-line-syntax.md)<br/>
[Vektorisierung in nativem Code in Visual Studio](/archive/blogs/nativeconcurrency/auto-vectorizer-in-visual-studio-2012-overview)
