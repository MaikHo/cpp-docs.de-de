---
title: Vordefinierte Regeln
ms.date: 11/04/2016
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
ms.openlocfilehash: 7a922a239306f10121791caa8f9f088cea88c019
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319446"
---
# <a name="predefined-rules"></a>Vordefinierte Regeln

Von vordefinierten Rückschlussregeln werden Befehls- und Optionenmakros von NMAKE verwendet.

|Regel|Befehl|Standard<br /><br /> action|Batch<br /><br /> Regel|Plattform, auf der nmake funktioniert|
|----------|-------------|------------------------|--------------------|----------------------------|
|.asm.exe|$(AS) $(AFLAGS) $<|ml-$<|Nein|x86|
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml /c $<|ja|x86|
|.asm.exe|$(AS) $(AFLAGS) $<|ml64 $<|Nein|x64|
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml64 /c $<|ja|x64|
|.c.exe|$(CC) $(CFLAGS) $<|CL-$<|Nein|all|
|.c.obj|$(CC) $(CFLAGS)/c <|cl /c $<|ja|all|
|.cc.exe|$(CC) $(CFLAGS) $<|CL-$<|Nein|all|
|.cc.obj|$(CC) $(CFLAGS)/c <|cl /c $<|ja|all|
|.cpp.exe|$(CPP) $(CPPFLAGS) $<|CL-$<|Nein|all|
|.cpp.obj|$(CPP) $(CPPFLAGS) /c $<|cl /c $<|ja|all|
|.cxx.exe|$(CXX) $(CXXFLAGS) $<|CL-$<|Nein|all|
|.cxx.obj|$(CXX) $(CXXFLAGS) /c $<|cl /c $<|ja|all|
|.rc.res|$(RC) $(RFLAGS)/r $<|RC/r $<|Nein|all|

## <a name="see-also"></a>Siehe auch

[Rückschlussregeln](inference-rules.md)
