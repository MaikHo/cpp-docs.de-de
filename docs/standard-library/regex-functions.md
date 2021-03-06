---
title: '&lt;regex&gt;-Funktionen'
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_match
- regex/std::regex_replace
- regex/std::regex_search
- regex/std::swap
ms.assetid: 91a8314b-6f7c-4e33-b7d6-d8583dd75585
helpviewer_keywords:
- std::regex_match [C++]
- std::regex_replace [C++]
- std::regex_search [C++]
- std::swap [C++]
- std::swap [C++]
ms.openlocfilehash: fd7087025939a0aacf17153f201e37fc377653f9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842870"
---
# <a name="ltregexgt-functions"></a>&lt;regex&gt;-Funktionen

|Name|Beschreibung|
|-|-|
|[regex_match](#regex_match)|Testet, ob ein regulärer Ausdruck der gesamten Zielzeichenfolge entspricht.|
|[regex_replace](#regex_replace)|Ersetzt übereinstimmende reguläre Ausdrücke.|
|[regex_search](#regex_search)|Sucht nach einer Übereinstimmung mit einem regulären Ausdruck.|
|[swap](#swap)|Tauscht zwei- `basic_regex` oder- `match_results` Objekte aus.|

## <a name="regex_match"></a><a name="regex_match"></a> regex_match

Testet, ob ein regulärer Ausdruck der gesamten Zielzeichenfolge entspricht.

```cpp
// (1)
template <class BidIt, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    BidIt first,
    Bidit last,
    match_results<BidIt, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (2)
template <class BidIt, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    BidIt first,
    Bidit last,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (3)
template <class Elem, class Alloc, class RXtraits, class Alloc2>
bool regex_match(
    const Elem *ptr,
    match_results<const Elem*, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (4)
template <class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const Elem *ptr,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (5)
template <class IOtraits, class IOalloc, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    match_results<typename basic_string<Elem, IOtraits, IOalloc>::const_iterator, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (6)
template <class IOtraits, class IOalloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>Parameter

*Bidit*\
Der Itertatortyp für Teilübereinstimmungen. In allgemeinen Fällen ist dies eine `string::const_iterator` von `wstring::const_iterator` , `const char*` oder `const wchar_t*` .

*Zuordnungseinheits*\
Die Zuweisungsklasse des Übereinstimmungsergebnisses.

*Elem*\
Der zu entsprechende Elementtyp. In allgemeinen Fällen ist dies `string` , `wstring` `char*` oder `wchar_t*` .

*Rxcharakteristika*\
Merkmalklasse für Elemente.

*Alloc2*\
Die Zuweisungsklasse des regulären Ausdrucks.

*Iocharakteristika*\
Die Trait-Klasse der Zeichenfolge.

*Iozuweisung*\
Die Zuweisungsklasse der Zeichenfolge.

*fahren*\
Flags für Übereinstimmungen.

*erstes*\
Anfang der Sequenz, die übereinstimmen soll.

*letzten*\
Ende der Sequenz, die übereinstimmen soll.

*übereinstimmen*\
Die Übereinstimmungsergebnisse. Entspricht dem Elem-Typ: [smatch](../standard-library/regex-typedefs.md#smatch) für `string` , [wsmatch](../standard-library/regex-typedefs.md#wsmatch) für `wstring` , [cmatch](../standard-library/regex-typedefs.md#cmatch) for `char*` oder [wcmatch](../standard-library/regex-typedefs.md#wcmatch) for `wchar_t*` .

*PTR*\
Zeiger auf den Anfang der Sequenz, die übereinstimmen soll. Wenn *ptr* ist `char*` , verwenden Sie `cmatch` und `regex` . Wenn *ptr* `wchar_t*` dann und verwendet `wcmatch` wird `wregex` .

*Turm*\
Der reguläre Ausdruck, mit dem eine Übereinstimmung bestehen soll. Geben Sie `regex` für `string` und `char*` , oder `wregex` für und ein `wstring` `wchar_t*` .

*SRT*\
Zeichenfolge, die übereinstimmen soll. Entspricht dem Typ von *Elem*.

### <a name="remarks"></a>Bemerkungen

Jede Vorlagen Funktion gibt nur dann true zurück, wenn der gesamte operandensequenz- *Str* genau mit *dem Argument für*reguläre Ausdrücke übereinstimmt. Verwenden Sie [regex_search](../standard-library/regex-functions.md#regex_search) , um eine Teil Zeichenfolge innerhalb einer Zielsequenz abzugleichen und `regex_iterator` mehrere Übereinstimmungen zu finden. Die Funktionen, die ein `match_results`-Objekt übernehmen, legen dessen Member fest, um wiederzugeben, ob die Suche nach der Übereinstimmung erfolgreich war, und wenn ja, was die verschiedenen Erfassungsgruppen im regulären Ausdruck erfasst haben.

Die Funktionen, die ein `match_results`-Objekt übernehmen, legen dessen Member fest, um wiederzugeben, ob die Suche nach der Übereinstimmung erfolgreich war, und wenn ja, was die verschiedenen Erfassungsgruppen im regulären Ausdruck erfasst haben.

### <a name="example"></a>Beispiel

```cpp
// std__regex__regex_match.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

using namespace std;

int main()
{
    // (1) with char*
    // Note how const char* requires cmatch and regex
    const char *first = "abc";
    const char *last = first + strlen(first);
    cmatch narrowMatch;
    regex rx("a(b)c");

    bool found = regex_match(first, last, narrowMatch, rx);
    if (found)
        wcout << L"Regex found in abc" << endl;

    // (2) with std::wstring
    // Note how wstring requires wsmatch and wregex.
    // Note use of const iterators cbegin() and cend().
    wstring target(L"Hello");
    wsmatch wideMatch;
    wregex wrx(L"He(l+)o");

    if (regex_match(target.cbegin(), target.cend(), wideMatch, wrx))
        wcout << L"The matching text is:" << wideMatch.str() << endl;

    // (3) with std::string
    string target2("Drizzle");
    regex rx2(R"(D\w+e)"); // no double backslashes with raw string literal

    found = regex_match(target2.cbegin(), target2.cend(), rx2);
    if (found)
        wcout << L"Regex found in Drizzle" << endl;

    // (4) with wchar_t*
    const wchar_t* target3 = L"2014-04-02";
    wcmatch wideMatch2;

    // LR"(...)" is a  raw wide-string literal. Open and close parens
    // are delimiters, not string elements.
    wregex wrx2(LR"(\d{4}(-|/)\d{2}(-|/)\d{2})");
    if (regex_match(target3, wideMatch2, wrx2))
    {
        wcout << L"Matching text: " << wideMatch2.str() << endl;
    }

     return 0;
}
```

```Output
Regex found in abc
The matching text is: Hello
Regex found in Drizzle
The matching text is: 2014-04-02
```

## <a name="regex_replace"></a><a name="regex_replace"></a> regex_replace

Ersetzt übereinstimmende reguläre Ausdrücke.

```cpp
template <class OutIt, class BidIt, class RXtraits, class Alloc, class Elem>
OutIt regex_replace(
    OutIt out,
    BidIt first,
    BidIt last,
    const basic_regex<Elem, RXtraits, Alloc>& re,
    const basic_string<Elem>& fmt,
    match_flag_type flags = match_default);

template <class RXtraits, class Alloc, class Elem>
basic_string<Elem> regex_replace(
    const basic_string<Elem>& str,
    const basic_regex<Elem, RXtraits, Alloc>& re,
    const basic_string<Elem>& fmt,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>Parameter

*OutIt*\
Der Itertatortyp für Ersetzungen.

*Bidit*\
Der Itertatortyp für Teilübereinstimmungen.

*Rxcharakteristika*\
Merkmalklasse für Elemente.

*Zuordnungseinheits*\
Die Zuweisungsklasse des regulären Ausdrucks.

*Elem*\
Der zu entsprechende Elementtyp.

*fahren*\
Flags für Übereinstimmungen.

*erstes*\
Anfang der Sequenz, die übereinstimmen soll.

*fmt*\
Das Format für Ersetzungen.

*letzten*\
Ende der Sequenz, die übereinstimmen soll.

*vorgenommen*\
Der Ausgabeiterator.

*Turm*\
Der reguläre Ausdruck, mit dem eine Übereinstimmung bestehen soll.

*SRT*\
Zeichenfolge, die übereinstimmen soll.

### <a name="remarks"></a>Bemerkungen

Die erste Funktion erstellt ein [regex_iterator-Klassen](../standard-library/regex-iterator-class.md) Objekt `iter(first, last, re, flags)` und verwendet es, um den Eingabebereich `[first, last)` in eine Reihe von unter Sequenzen aufzuteilen `T0 M0 T1 M1...TN-1 MN-1 TN` , wobei `Mn` die vom Iterator erkannte ten-Entsprechung ist. Wenn keine Übereinstimmungen gefunden werden, ist `T0` der gesamte Bereich für die Eingabe und `N` ist null. Wenn `(flags & format_first_only) != 0` nur die erste Übereinstimmung verwendet, sind `T1` alle Eingabetexte, die der Übereinstimmung folgen und `N` ist 1. Für jede `i` im Bereich `[0, N)` , wenn `(flags & format_no_copy) == 0` der Text im Bereich in `Ti` den Iterator kopiert wird. *out* Anschließend wird aufgerufen `m.format(out, fmt, flags)` , wobei `m` das `match_results` vom Iteratorobjekt für die unter Sequenz zurückgegebene Objekt ist `iter` `Mi` . Schließlich wird `(flags & format_no_copy) == 0` der Text im Bereich in `TN` den Iterator *out*kopiert. Die *Funktion gibt zurück*.

Die zweite Funktion erstellt eine lokale Variable `result` des Typs `basic_string<charT>` und ruft `regex_replace(back_inserter(result), str.begin(), str.end(), re, fmt, flags)` auf. Er gibt `result` zurück.

### <a name="example"></a>Beispiel

```cpp
// std__regex__regex_replace.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    char buf[20];
    const char *first = "axayaz";
    const char *last = first + strlen(first);
    std::regex rx("a");
    std::string fmt("A");
    std::regex_constants::match_flag_type fonly =
        std::regex_constants::format_first_only;

    *std::regex_replace(&buf[0], first, last, rx, fmt) = '\0';
    std::cout << "replacement == " << &buf[0] << std::endl;

    *std::regex_replace(&buf[0], first, last, rx, fmt, fonly) = '\0';
    std::cout << "replacement == " << &buf[0] << std::endl;

    std::string str("adaeaf");
    std::cout << "replacement == "
        << std::regex_replace(str, rx, fmt) << std::endl;

    std::cout << "replacement == "
        << std::regex_replace(str, rx, fmt, fonly) << std::endl;

    return (0);
}
```

```Output
replacement == AxAyAz
replacement == Axayaz
replacement == AdAeAf
replacement == Adaeaf
```

## <a name="regex_search"></a><a name="regex_search"></a> regex_search

Sucht nach einer Übereinstimmung mit einem regulären Ausdruck.

```cpp
template <class BidIt, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    BidIt first,
    Bidit last,
    match_results<BidIt, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class BidIt, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    BidIt first,
    Bidit last,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class Elem, class Alloc, class RXtraits, class Alloc2>
bool regex_search(
    const Elem* ptr,
    match_results<const Elem*, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const Elem* ptr,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class IOtraits, class IOalloc, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    match_results<typename basic_string<Elem, IOtraits, IOalloc>::const_iterator, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class IOtraits, class IOalloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>Parameter

*Bidit*\
Der Itertatortyp für Teilübereinstimmungen.

*Zuordnungseinheits*\
Die Zuweisungsklasse des Übereinstimmungsergebnisses.

*Elem*\
Der zu entsprechende Elementtyp.

*Rxcharakteristika*\
Merkmalklasse für Elemente.

*Alloc2*\
Die Zuweisungsklasse des regulären Ausdrucks.

*Iocharakteristika*\
Die Trait-Klasse der Zeichenfolge.

*Iozuweisung*\
Die Zuweisungsklasse der Zeichenfolge.

*fahren*\
Flags für Übereinstimmungen.

*erstes*\
Anfang der Sequenz, die übereinstimmen soll.

*letzten*\
Ende der Sequenz, die übereinstimmen soll.

*übereinstimmen*\
Die Übereinstimmungsergebnisse.

*PTR*\
Zeiger auf den Anfang der Sequenz, die übereinstimmen soll.

*Turm*\
Der reguläre Ausdruck, mit dem eine Übereinstimmung bestehen soll.

*SRT*\
Zeichenfolge, die übereinstimmen soll.

### <a name="remarks"></a>Bemerkungen

Jede Vorlagen Funktion gibt nur dann true zurück, wenn eine Suche nach dem regulären *Ausdrucks Argument in* der operandensequenz erfolgreich ist. Die Funktionen, die ein `match_results`-Objekt übernehmen, legen dessen Member fest, um wiederzugeben, ob die Suche nach der Übereinstimmung erfolgreich war, und wenn ja, was die verschiedenen Erfassungsgruppen im regulären Ausdruck erfasst haben.

### <a name="example"></a>Beispiel

```cpp
// std__regex__regex_search.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    const char *first = "abcd";
    const char *last = first + strlen(first);
    std::cmatch mr;
    std::regex rx("abc");
    std::regex_constants::match_flag_type fl =
        std::regex_constants::match_default;

    std::cout << "search(f, f+1, \"abc\") == " << std::boolalpha
        << regex_search(first, first + 1, rx, fl) << std::endl;

    std::cout << "search(f, l, \"abc\") == " << std::boolalpha
        << regex_search(first, last, mr, rx) << std::endl;
    std::cout << "  matched: \"" << mr.str() << "\"" << std::endl;

    std::cout << "search(\"a\", \"abc\") == " << std::boolalpha
        << regex_search("a", rx) << std::endl;

    std::cout << "search(\"xabcd\", \"abc\") == " << std::boolalpha
        << regex_search("xabcd", mr, rx) << std::endl;
    std::cout << "  matched: \"" << mr.str() << "\"" << std::endl;

    std::cout << "search(string, \"abc\") == " << std::boolalpha
        << regex_search(std::string("a"), rx) << std::endl;

    std::string str("abcabc");
    std::match_results<std::string::const_iterator> mr2;
    std::cout << "search(string, \"abc\") == " << std::boolalpha
        << regex_search(str, mr2, rx) << std::endl;
    std::cout << "  matched: \"" << mr2.str() << "\"" << std::endl;

    return (0);
}
```

```Output
search(f, f+1, "abc") == false
search(f, l, "abc") == true
  matched: "abc"
search("a", "abc") == false
search("xabcd", "abc") == true
  matched: "abc"
search(string, "abc") == false
search(string, "abc") == true
  matched: "abc"
```

## <a name="swap"></a><a name="swap"></a> Wechsel

Tauscht zwei- `basic_regex` oder- `match_results` Objekte aus.

```cpp
template <class Elem, class RXtraits>
void swap(
    basic_regex<Elem, RXtraits, Alloc>& left,
    basic_regex<Elem, RXtraits>& right) noexcept;

template <class Elem, class IOtraits, class BidIt, class Alloc>
void swap(
    match_results<BidIt, Alloc>& left,
    match_results<BidIt, Alloc>& right) noexcept;
```

### <a name="parameters"></a>Parameter

*Elem*\
Der zu entsprechende Elementtyp.

*Rxcharakteristika*\
Merkmalklasse für Elemente.

### <a name="remarks"></a>Bemerkungen

Die Vorlagenfunktionen tauschen die Inhalte ihrer jeweiligen Argumente in konstanter Zeit und lösen keine Ausnahmen aus.

### <a name="example"></a>Beispiel

```cpp
// std__regex__swap.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    std::regex rx0("c(a*)|(b)");
    std::regex rx1;
    std::cmatch mr0;
    std::cmatch mr1;

    swap(rx0, rx1);
    std::regex_search("xcaaay", mr1, rx1);
    swap(mr0, mr1);

    std::csub_match sub = mr0[1];
    std::cout << "matched == " << std::boolalpha
        << sub.matched << std::endl;
    std::cout << "length == " << sub.length() << std::endl;
    std::cout << "string == " << sub << std::endl;

    return (0);
}
```

```Output
matched == true
length == 3
string == aaa
```

## <a name="see-also"></a>Weitere Informationen

[\<regex>](../standard-library/regex.md)\
[regex_constants-Klasse](../standard-library/regex-constants-class.md)\
[regex_error-Klasse](../standard-library/regex-error-class.md)\
[regex_iterator-Klasse](../standard-library/regex-iterator-class.md)\
[\<regex> Veranstalter](../standard-library/regex-operators.md)\
[regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md)\
[regex_traits-Klasse](../standard-library/regex-traits-class.md)\
[\<regex> Typedefs](../standard-library/regex-typedefs.md)
