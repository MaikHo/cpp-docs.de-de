---
title: Compilerfehler C2752
ms.date: 11/04/2016
f1_keywords:
- C2752
helpviewer_keywords:
- C2752
ms.assetid: ae42b3ec-84a9-4e9d-8d59-3d208132d0b2
ms.openlocfilehash: 3095999b6141ad89e0f94e29d726512af1d58b0c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759580"
---
# <a name="compiler-error-c2752"></a>Compilerfehler C2752

"Template": mehr als eine partielle Spezialisierung stimmt mit der Vorlagen Argumentliste überein

Eine Instanziierung war mehrdeutig.

Im folgenden Beispiel wird C2752 generiert:

```cpp
// C2752.cpp
template<class T, class U>
struct A {};

template<class T, class U>
struct A<T*, U> {};

template<class T, class U>
struct A<T,U*> {};

// try the following line instead
// template<class T, class U> struct A<T*,U*> {};

int main() {
   A<char*,int*> a;   // C2752 an instantiation

   // OK
   A<char*,int> a1;
   A<char,int*> a2;
   A<char,int> a3;
}
```
