---
title: istrstream-Klasse
ms.date: 11/04/2016
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
ms.openlocfilehash: 37118772f7cefd6f380ceb01908da55500ee7ab5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228231"
---
# <a name="istrstream-class"></a>istrstream-Klasse

Beschreibt ein Objekt, das die Extraktion von Elementen und codierten Objekten aus einem Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.

## <a name="syntax"></a>Syntax

```cpp
class istrstream : public istream
```

## <a name="remarks"></a>Bemerkungen

Das Objekt speichert ein Objekt der Klasse `strstreambuf`.

> [!NOTE]
> Diese Klasse ist veraltet. Verwenden Sie stattdessen [istringstream](../standard-library/sstream-typedefs.md#istringstream) oder [wistringstream](../standard-library/sstream-typedefs.md#wistringstream).

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[istrstream](#istrstream)|Konstruiert ein Objekt vom Typ `istrstream`.|

### <a name="member-functions"></a>Memberfunktionen

|Memberfunktion|BESCHREIBUNG|
|-|-|
|[rdbuf](#rdbuf)|Gibt einen Zeiger auf das dem Stream zugeordnete `strstreambuf`-Objekt zurück.|
|[str](#str)|Ruft [freeze](../standard-library/strstreambuf-class.md#freeze) auf und gibt anschließend einen Zeiger auf den Anfang der kontrollierten Sequenz zurück.|

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:**\<strstream>

**Namespace:** std

## <a name="istrstreamistrstream"></a><a name="istrstream"></a>istrinstream:: istrinstream

Konstruiert ein Objekt vom Typ `istrstream`.

```cpp
explicit istrstream(
    const char* ptr);

explicit istrstream(
    char* ptr);

istrstream(
    const char* ptr,
    streamsize count);

istrstream(
    char* ptr,
    int count);
```

### <a name="parameters"></a>Parameter

*Countdown*\
Die Länge des Puffers (*ptr*).

*PTR*\
Der Inhalt, mit dem der Puffer initialisiert wird.

### <a name="remarks"></a>Bemerkungen

Alle Konstruktoren initialisieren die Basisklasse durch Aufrufen von [IStream](../standard-library/istream-typedefs.md#istream)(**SB**), wobei `sb` das gespeicherte Objekt der Klasse "" von " [strauf](../standard-library/strstreambuf-class.md)" ist. Die ersten beiden Konstruktoren initialisieren auch `sb` durch Aufrufen von `strstreambuf( ( const char *) ptr, 0 )` . Die verbleibenden zwei Konstruktoren werden stattdessen aufgerufen `strstreambuf( ( const char *) ptr, count )` .

## <a name="istrstreamrdbuf"></a><a name="rdbuf"></a>istrinstream:: Rdbuf

Gibt einen Zeiger auf das dem Stream zugeordneten strstreambuf-Objekt zurück.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das dem Stream zugeordnete strstreambuf-Objekt.

### <a name="remarks"></a>Bemerkungen

Die Memberfunktion gibt die Adresse des gespeicherten Streampuffers des Typs Zeiger auf [strstreambuf](../standard-library/strstreambuf-class.md) zurück.

### <a name="example"></a>Beispiel

Ein Beispiel, das `rdbuf` verwendet, finden Sie unter [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).

## <a name="istrstreamstr"></a><a name="str"></a>istrinstream:: Str

Ruft [freeze](../standard-library/strstreambuf-class.md#freeze) auf und gibt anschließend einen Zeiger auf den Anfang der kontrollierten Sequenz zurück.

```cpp
char *str();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf den Anfang der kontrollierten Sequenz.

### <a name="remarks"></a>Bemerkungen

Die Member-Funktion gibt [rdbuf](#rdbuf)  ->  [Str](../standard-library/strstreambuf-class.md#str)zurück.

### <a name="example"></a>Beispiel

Ein Beispiel, das verwendet, finden Sie unter [strinstream:: Str](../standard-library/strstreambuf-class.md#str) `str` .

## <a name="see-also"></a>Siehe auch

[IStream](../standard-library/istream-typedefs.md#istream)\
[Thread Sicherheit in der C++-Standard Bibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[Iostreams-Konventionen](../standard-library/iostreams-conventions.md)
