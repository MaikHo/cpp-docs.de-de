---
title: utility (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/utility>
- cliext::pair
- cliext::pair::pair
- cliext::pair::first
- cliext::pair::first_type
- cliext::pair::second
- cliext::pair::second_type
- cliext::pair::swap
- cliext::make_pair
- cliext::pair::operator=
- cliext::pair::operator==
- cliext::pair::operator>=
- cliext::pair::operator>
- cliext::pair::operator!=
- cliext::pair::operator<=
- cliext::pair::operator<
helpviewer_keywords:
- <utility> header [STL/CLR]
- utility header [STL/CLR]
- <cliext/utility> header [STL/CLR]
- first member [STL/CLR]
- first_type member [STL/CLR]
- second member [STL/CLR]
- second_type member [STL/CLR]
- swap member [STL/CLR]
- make_pair function [STL/CLR]
- pair class [STL/CLR]
- pair member [STL/CLR]
- operator== member [STL/CLR]
- operator= member [STL/CLR]
- operator>= member [STL/CLR]
- operator> member [STL/CLR]
- operator!= member [STL/CLR]
- operator<= member [STL/CLR]
- operator< member [STL/CLR]
ms.assetid: fb48cb75-d5ef-47ce-b526-bf60dc86c552
ms.openlocfilehash: b21f9ec2ace54281f30f8f32134c7fb3466a1faa
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214853"
---
# <a name="utility-stlclr"></a>utility (STL/CLR)

Fügen Sie den STL/CLR-Header ein `<cliext/utility>` , um die Vorlagen Klasse `pair` und verschiedene unterstützende Vorlagen Funktionen zu definieren.

## <a name="syntax"></a>Syntax

```cpp
#include <utility>
```

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:**\<cliext/utility>

**Namespace:** cliext

## <a name="declarations"></a>Deklarationen

|Klasse|BESCHREIBUNG|
|-----------|-----------------|
|[pair (STL/CLR)](#pair)|Wrappen Sie ein Element Paar.|

|Operator|BESCHREIBUNG|
|--------------|-----------------|
|[Operator = = (Pair) (STL/CLR)](#op_eq)|Gleicher Vergleich.|
|[Operator! = (Pair) (STL/CLR)](#op_neq)|Paar ungleich Vergleich.|
|[Operator< (Pair) (STL/CLR)](#op_lt)|Paar kleiner als-Vergleich.|
|[Operator \< = (Pair) (STL/CLR)](#op_lteq)|Paar kleiner oder gleich-Vergleich.|
|[Operator> (Pair) (STL/CLR)](#op_gt)|Paar größer als-Vergleich.|
|[operator>= (pair) (STL/CLR)](#op_gteq)|Paar größer oder gleich-Vergleich.|

|Funktion|BESCHREIBUNG|
|--------------|-----------------|
|[make_pair (STL/CLR)](#make_pair)|Erstellen Sie ein paar aus einem Paar von Werten.|

## <a name="members"></a>Member

## <a name="pair-stlclr"></a><a name="pair"></a>Pair (STL/CLR)

Die Vorlagen Klasse beschreibt ein Objekt, das ein paar von Werten umschließt.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    ref class pair;
```

#### <a name="parameters"></a>Parameter

*Value1*<br/>
Der Typ des ersten umschließenden Werts.

*Value2*<br/>
Der Typ des zweiten umschließenden Werts.

## <a name="members"></a>Member

|Typendefinition|BESCHREIBUNG|
|---------------------|-----------------|
|[pair::first_type (STL/CLR)](#first_type)|Der Typ des ersten umschließenden Werts.|
|[pair::second_type (STL/CLR)](#second_type)|Der Typ des zweiten umschließenden Werts.|

|Member-Objekt|BESCHREIBUNG|
|-------------------|-----------------|
|[pair::first (STL/CLR)](#first)|Der erste gespeicherte Wert.|
|[pair::second (STL/CLR)](#second)|Der zweite gespeicherte Wert.|

|Memberfunktion|BESCHREIBUNG|
|---------------------|-----------------|
|[pair::pair (STL/CLR)](#pair_pair)|Erstellt ein Pair-Objekt.|
|[pair::swap (STL/CLR)](#swap)|Tauscht den Inhalt zweier Paare aus.|

|Operator|BESCHREIBUNG|
|--------------|-----------------|
|[pair::operator= (STL/CLR)](#op_as)|Ersetzt das gespeicherte paar von Werten.|

## <a name="remarks"></a>Bemerkungen

Das-Objekt speichert ein Wertepaar. Sie verwenden diese Vorlagen Klasse, um zwei Werte in einem einzelnen Objekt zu kombinieren. Außerdem speichert das-Objekt `cliext::pair` (hier beschrieben) nur verwaltete Typen. zum Speichern eines Paares nicht verwalteter Typen verwenden Sie `std::pair` , deklariert in `<utility>` .

## <a name="pairfirst-stlclr"></a><a name="first"></a>Pair:: First (STL/CLR)

Der erste umschließende Wert.

### <a name="syntax"></a>Syntax

```cpp
Value1 first;
```

### <a name="remarks"></a>Bemerkungen

Das-Objekt speichert den ersten umschließten Wert.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_first.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairfirst_type-stlclr"></a><a name="first_type"></a>Pair:: first_type (STL/CLR)

Der Typ des ersten umschließenden Werts.

### <a name="syntax"></a>Syntax

```cpp
typedef Value1 first_type;
```

### <a name="remarks"></a>Bemerkungen

Der Typ ist ein Synonym für den Vorlagen Parameter *value1*.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_first_type.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairoperator-stlclr"></a><a name="op_as"></a>Pair:: Operator = (STL/CLR)

Ersetzt das gespeicherte paar von Werten.

### <a name="syntax"></a>Syntax

```cpp
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*Richting*<br/>
Zu Kopiervorgang koppeln.

### <a name="remarks"></a>Bemerkungen

Der Member-Operator kopiert *direkt* in das-Objekt und gibt dann zurück **`*this`** . Sie verwenden es, um das gespeicherte Werte Paar durch eine Kopie des gespeicherten Werte Paars in der *rechten*Ecke zu ersetzen.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_operator_as.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

// assign to a new pair
    cliext::pair<wchar_t, int> c2;
    c2 = c1;
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);
    return (0);
    }
```

```Output
[x, 3]
[x, 3]
```

## <a name="pairpair-stlclr"></a><a name="pair_pair"></a>Pair::p Air (STL/CLR)

Erstellt ein Pair-Objekt.

### <a name="syntax"></a>Syntax

```cpp
pair();
pair(pair<Coll>% right);
pair(pair<Coll>^ right);
pair(Value1 val1, Value2 val2);
```

#### <a name="parameters"></a>Parameter

*Richting*<br/>
Zu Speicher Paar.

*val1*<br/>
Der erste Wert, der gespeichert wird.

*Wert2*<br/>
Der zweite zu Speicher Endwert.

### <a name="remarks"></a>Bemerkungen

Der Konstruktor:

`pair();`

Initialisiert das gespeicherte Paar mit standardmäßig erstellten Werten.

Der Konstruktor:

`pair(pair<Value1, Value2>% right);`

Initialisiert das gespeicherte Paar mit `right.` [Pair:: First (STL/CLR)](../dotnet/pair-first-stl-clr.md) und `right.` [Pair:: Second (STL/CLR)](../dotnet/pair-second-stl-clr.md).

`pair(pair<Value1, Value2>^ right);`

Initialisiert das gespeicherte Paar mit `right->` [Pair:: First (STL/CLR)](../dotnet/pair-first-stl-clr.md) und `right>` [Pair:: Second (STL/CLR)](../dotnet/pair-second-stl-clr.md).

Der Konstruktor:

`pair(Value1 val1, Value2 val2);`

Initialisiert das gespeicherte Paar mit *Wert1* und *Wert2*.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_construct.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
// construct an empty container
    cliext::pair<wchar_t, int> c1;
    System::Console::WriteLine("[{0}, {1}]",
        c1.first == L'\0' ? "\\0" : "??", c1.second);

// construct with a pair of values
    cliext::pair<wchar_t, int> c2(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

// construct by copying another pair
    cliext::pair<wchar_t, int> c3(c2);
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);

// construct by copying a pair handle
    cliext::pair<wchar_t, int> c4(%c3);
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);

    return (0);
    }
```

```Output
[\0, 0]
[x, 3]
[x, 3]
[x, 3]
```

## <a name="pairsecond-stlclr"></a><a name="second"></a>Pair:: Second (STL/CLR)

Der zweite umschließende Wert.

### <a name="syntax"></a>Syntax

```cpp
Value2 second;
```

### <a name="remarks"></a>Bemerkungen

Das-Objekt speichert den zweiten umschließten Wert.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_second.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairsecond_type-stlclr"></a><a name="second_type"></a>Pair:: second_type (STL/CLR)

Der Typ des zweiten umschließenden Werts.

### <a name="syntax"></a>Syntax

```cpp
typedef Value2 second_type;
```

### <a name="remarks"></a>Bemerkungen

Der Typ ist ein Synonym für den Vorlagen Parameter *value2*.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_second_type.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairswap-stlclr"></a><a name="swap"></a>Pair:: Swap (STL/CLR)

Tauscht den Inhalt zweier Paare aus.

### <a name="syntax"></a>Syntax

```cpp
void swap(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*Richting*<br/>
Paar zum Austauschen von Inhalten mit.

### <a name="remarks"></a>Bemerkungen

Die Member-Funktion tauscht das gespeicherte paar von Werten zwischen **`*this`** und *Rechts*aus.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_swap.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
    {
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    cliext::deque<wchar_t> d2(5, L'x');
    Mycoll c2(%d2);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// swap and redisplay
    c1.swap(c2);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
x x x x x
x x x x x
a b c
```

## <a name="make_pair-stlclr"></a><a name="make_pair"></a>make_pair (STL/CLR)

Einen `pair` aus einem Paar von Werten erstellen.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);
```

#### <a name="parameters"></a>Parameter

*Value1*<br/>
Der Typ des ersten umschließenden Werts.

*Value2*<br/>
Der Typ des zweiten umschließenden Werts.

*first*<br/>
Der erste zu Umbruch Ende Wert.

*second*<br/>
Der zweite umzuschließende Wert.

### <a name="remarks"></a>Bemerkungen

Diese Vorlagenfunktion gibt `pair<Value1, Value2>(first, second)` zurück. Sie verwenden es, um ein- `pair<Value1, Value2>` Objekt aus einem Wertepaar zu erstellen.

### <a name="example"></a>Beispiel

```cpp
// cliext_make_pair.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    c1 = cliext::make_pair(L'y', 4);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    return (0);
    }
```

```Output
[x, 3]
[y, 4]
```

## <a name="operator-pair-stlclr"></a><a name="op_neq"></a>Operator! = (Pair) (STL/CLR)

Paar ungleich Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    bool operator!=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*linken*<br/>
Linkes Paar zum vergleichen.

*Richting*<br/>
Das richtige Paar zum vergleichen.

### <a name="remarks"></a>Bemerkungen

Die Operator Funktion gibt zurück `!(left == right)` . Sie verwenden es, um zu testen, ob *left* nicht identisch ist *, wenn die* beiden Paare Element Weise verglichen werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_operator_ne.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] != [x 3] is {0}",
        c1 != c1);
    System::Console::WriteLine("[x 3] != [x 4] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] != [x 3] is False
[x 3] != [x 4] is True
```

## <a name="operatorlt-pair-stlclr"></a><a name="op_lt"></a>Operator &lt; (Pair) (STL/CLR)

Paar kleiner als-Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    bool operator<(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*linken*<br/>
Linkes Paar zum vergleichen.

*Richting*<br/>
Das richtige Paar zum vergleichen.

### <a name="remarks"></a>Bemerkungen

Die Operator Funktion gibt zurück `left.first <` `right.first || !(right.first <` `left.first &&` `left.second <` `right.second` . Sie verwenden es, um zu überprüfen, ob *left* nach *Rechts* geordnet ist, wenn die beiden Paare Element Weise verglichen werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_operator_lt.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] < [x 3] is {0}",
        c1 < c1);
    System::Console::WriteLine("[x 3] < [x 4] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] < [x 3] is False
[x 3] < [x 4] is True
```

## <a name="operatorlt-pair-stlclr"></a><a name="op_lteq"></a>Operator &lt; = (Pair) (STL/CLR)

Paar kleiner oder gleich-Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    bool operator<=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*linken*<br/>
Linkes Paar zum vergleichen.

*Richting*<br/>
Das richtige Paar zum vergleichen.

### <a name="remarks"></a>Bemerkungen

Die Operator Funktion gibt zurück `!(right < left)` . Sie verwenden es, um zu testen, ob *left* nach *Rechts* nicht geordnet ist, wenn die beiden Paare Element Weise verglichen werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_operator_le.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] <= [x 3] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[x 4] <= [x 3] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] <= [x 3] is True
[x 4] <= [x 3] is False
```

## <a name="operator-pair-stlclr"></a><a name="op_eq"></a>Operator = = (Pair) (STL/CLR)

Gleicher Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    bool operator==(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*linken*<br/>
Linkes Paar zum vergleichen.

*Richting*<br/>
Das richtige Paar zum vergleichen.

### <a name="remarks"></a>Bemerkungen

Die Operator Funktion gibt zurück `left.first ==` `right.first &&` `left.second ==` `right.second` . Sie verwenden es, um zu überprüfen, ob *Links* mit *right* dem Element by-Element verglichen werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_operator_eq.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] == [x 3] is {0}",
        c1 == c1);
    System::Console::WriteLine("[x 3] == [x 4] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] == [x 3] is True
[x 3] == [x 4] is False
```

## <a name="operatorgt-pair-stlclr"></a><a name="op_gt"></a>Operator &gt; (Pair) (STL/CLR)

Paar größer als-Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    bool operator>(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*linken*<br/>
Linkes Paar zum vergleichen.

*Richting*<br/>
Das richtige Paar zum vergleichen.

### <a name="remarks"></a>Bemerkungen

Die Operator Funktion gibt zurück `right` `<` `left` . Sie verwenden es, um zu überprüfen, ob *Links* nach *Rechts* angeordnet ist, wenn die beiden Paare Element Weise verglichen werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_operator_gt.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] > [x 3] is {0}",
        c1 > c1);
    System::Console::WriteLine("[x 4] > [x 3] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] > [x 3] is False
[x 4] > [x 3] is True
```

## <a name="operatorgt-pair-stlclr"></a><a name="op_gteq"></a>Operator &gt; = (Pair) (STL/CLR)

Paar größer oder gleich-Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    bool operator>=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*linken*<br/>
Linkes Paar zum vergleichen.

*Richting*<br/>
Das richtige Paar zum vergleichen.

### <a name="remarks"></a>Bemerkungen

Die Operator Funktion gibt zurück `!(left < right)` . Sie verwenden es, um zu testen, ob *left* nicht vor *Rechts* geordnet ist, wenn die beiden Paare Element Weise verglichen werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_operator_ge.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] >= [x 3] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[x 3] >= [x 4] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] >= [x 3] is True
[x 3] >= [x 4] is False
```
