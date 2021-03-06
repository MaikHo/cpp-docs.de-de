---
title: /constexpr (constexpr-Auswertung steuern)
ms.date: 08/15/2017
f1_keywords:
- /constexpr
- -constexpr
helpviewer_keywords:
- /constexpr control constexpr evaluation [C++]
- -constexpr control constexpr evaluation [C++]
- constexpr control constexpr evaluation [C++]
ms.assetid: 76d56784-f5ad-401d-841d-09d1059e8b8c
ms.openlocfilehash: 7b3ae1cd732fe1ec234e2734ea4c6fa86db9d5af
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223862"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (constexpr-Auswertung steuern)

Verwenden Sie die **/constexpr** -Compileroptionen zum Steuern von Parametern zur **`constexpr`** Auswertung zur Kompilierzeit.

## <a name="syntax"></a>Syntax

> **/constexpr: Tiefe**<em>N</em>\
> **/constexpr: Rückverfolgung**<em>N</em>\
> **/constexpr: Schritte**<em>N</em>

## <a name="arguments"></a>Argumente

**Tiefe**<em>n</em> beschränken Sie die Tiefe rekursiver **`constexpr`** Funktionsaufrufe auf *N* Ebenen. Der Standardwert liegt bei 512.

**Rückverfolgung**<em>n</em> zeigt bis zu *N* **`constexpr`** Auswertungen in der Diagnose an. Der Standardwert ist 10.

**Schritte**<em>n</em> Beenden der **`constexpr`** Auswertung nach *N* Schritten. Der Standardwert ist 100.000.

## <a name="remarks"></a>Bemerkungen

Die **/constexpr** -Compileroptionen steuern die Kompilierzeit Auswertung von **`constexpr`** Ausdrücken. Bewertungsschritte, Rekursions Ebenen und Backtrace-Tiefe werden gesteuert, um zu verhindern, dass der Compiler zu viel Zeit für die **`constexpr`** Auswertung ausgibt. Weitere Informationen zum Language- **`constexpr`** Element finden Sie unter [constexpr (C++)](../../cpp/constexpr-cpp.md).

Die **/constexpr** -Optionen sind ab Visual Studio 2015 verfügbar.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaften Seiten** des Projekts.

2. Erweitern Sie unter **Konfigurations Eigenschaften**den Ordner **C/C++** , und wählen Sie die Eigenschaften Seite **Befehlszeile** aus.

3. Geben Sie im Feld **zusätzliche Optionen** beliebige **/constexpr** -Compileroptionen ein. Wählen Sie **OK** oder **anwenden** aus, um die Änderungen zu speichern.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[MSVC-compilerbefehlszeilensyntax](compiler-command-line-syntax.md)
