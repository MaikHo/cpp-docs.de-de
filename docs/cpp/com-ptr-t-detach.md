---
title: _com_ptr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
ms.openlocfilehash: 8ba42f19e3474cc4a3199771f761b021221f430e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190013"
---
# <a name="_com_ptr_tdetach"></a>_com_ptr_t::Detach

**Microsoft-spezifisch**

Extrahiert den gekapselten Schnittstellenzeiger und gibt ihn zurück.

## <a name="syntax"></a>Syntax

```
Interface* Detach( ) throw( );
```

## <a name="remarks"></a>Bemerkungen

Extrahiert den gekapselten Schnittstellenzeiger und gibt ihn zurück und löscht dann den Speicher des gekapselten Zeigers auf NULL. Dadurch wird der Schnittstellenzeiger aus der Kapselung entfernt. Sie müssen `Release` für den zurückgegebenen Schnittstellen Zeiger aufzurufen.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Weitere Informationen

[_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)
