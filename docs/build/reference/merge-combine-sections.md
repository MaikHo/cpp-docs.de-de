---
title: /MERGE (Abschnitte kombinieren)
ms.date: 11/04/2016
f1_keywords:
- /merge
- VC.Project.VCLinkerTool.MergeSections
helpviewer_keywords:
- sections, combining
- /MERGE linker option
- sections, naming
- sections
- -MERGE linker option
- MERGE linker option
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
ms.openlocfilehash: f0e770425f8068b15522f405ffdcf7cf52999fe0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321214"
---
# <a name="merge-combine-sections"></a>/MERGE (Abschnitte kombinieren)

```
/MERGE:from=to
```

## <a name="remarks"></a>Hinweise

Die Option "/ Merge" kombiniert den ersten Abschnitt (*aus*) mit dem zweiten Abschnitt (*zu*), den so entstehende Abschnitt Benennung *zu*. Beispielsweise `/merge:.rdata=.text`.

Wenn der zweite Abschnitt nicht vorhanden ist, benennt der LINK im Abschnitt *aus* als *zu*.

Die Option "/ Merge" eignet sich zum Erstellen von VxDs und überschreiben die vom Compiler generierter Abschnittsnamen.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **erweitert** Eigenschaftenseite.

1. Ändern der **Abschnitte zusammenfügen** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
