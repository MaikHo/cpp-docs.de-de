---
title: codecvt_base-Klasse
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_base
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
ms.openlocfilehash: 6fca9b2130407b165a7a7bfb1fb2a9ec81774e20
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689889"
---
# <a name="codecvt_base-class"></a>codecvt_base-Klasse

Eine Basisklasse für die Codecvt-Klasse, die verwendet wird, um einen Enumerationstyp zu definieren, der als `result` bezeichnet wird, der als Rückgabetyp für die facetmember-Funktionen verwendet wird, um das Ergebnis einer Konvertierung anzugeben.

## <a name="syntax"></a>Syntax

```cpp
class codecvt_base : public locale::facet {
public:
    enum result {ok, partial, error, noconv};
    codecvt_base( size_t _Refs = 0);
    bool always_noconv() const;
    int max_length() const;
    int encoding() const;
    ~codecvt_base()

protected:
    virtual bool do_always_noconv() const;
    virtual int do_max_length() const;
    virtual int do_encoding() const;
};
```

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt eine Enumeration, die für alle Spezialisierungs Klassen Vorlagen [Codecvt](../standard-library/codecvt-class.md)gemeinsam ist. Das Enumerationsergebnis beschreibt die möglichen Rückgabewerte [do_in](../standard-library/codecvt-class.md#do_in) oder [do_out](../standard-library/codecvt-class.md#do_out):

- `ok`, wenn die Konvertierung zwischen internen und externen Zeichen Codierungen erfolgreich ist.

- `partial`, wenn das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ausgeführt werden kann.

- `error`, wenn die Quell Sequenz nicht ordnungsgemäß formatiert ist.

- `noconv`, wenn die Funktion keine Konvertierung ausführt.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
