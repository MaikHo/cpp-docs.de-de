---
title: 'Gewusst wie: Marshallen von COM-Zeichenfolgen mit C++-Interop'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- COM [C++], marshaling strings
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
ms.openlocfilehash: 8dfdad892261d5ae2d3494734458e1447f8ebd7c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545228"
---
# <a name="how-to-marshal-com-strings-using-c-interop"></a>Gewusst wie: Marshallen von COM-Zeichenfolgen mit C++-Interop

In diesem Thema wird veranschaulicht, wie ein BSTR (das grundlegende Zeichen folgen Format, das bei der com-Programmierung bevorzugt wird) von einer verwalteten an eine nicht verwaltete Funktion und umgekehrt übermittelt werden kann. Informationen zum interagieren mit anderen Zeichen folgen Typen finden Sie in den folgenden Themen:

- [Vorgehensweise: Marshallen von Unicode-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Vorgehensweise: Marshallen von ANSI-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

In den folgenden Codebeispielen werden [verwaltete und nicht verwaltete #pragma-](../preprocessor/managed-unmanaged.md) Direktiven verwendet, um verwaltete und nicht verwaltete Funktionen in der gleichen Datei zu implementieren. diese Funktionen werden jedoch auf die gleiche Weise interagiert, wenn Sie in separaten Dateien definiert werden. Dateien, die nur nicht verwaltete Funktionen enthalten, müssen nicht mit/CLR kompiliert werden [(Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein BSTR (ein Zeichen folgen Format, das in der com-Programmierung verwendet wird) von einer verwalteten an eine nicht verwaltete Funktion übermittelt werden kann. Die Aufruf verwaltete Funktion verwendet <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A>, um die Adresse einer BSTR-Darstellung des Inhalts einer .NET System. String abzurufen. Dieser Zeiger wird mithilfe von [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) fixiert, um sicherzustellen, dass die physische Adresse während eines Garbage Collection Zyklen nicht geändert wird, während die nicht verwaltete Funktion ausgeführt wird. Der Garbage Collector ist nicht zulässig, um den Arbeitsspeicher zu verschieben, bis die [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) den Gültigkeitsbereich verlässt.

```cpp
// MarshalBSTR1.cpp
// compile with: /clr
#define WINVER 0x0502
#define _AFXDLL
#include <afxwin.h>

#include <iostream>
using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

void NativeTakesAString(BSTR bstr) {
   printf_s("%S", bstr);
}

#pragma managed

int main() {
   String^ s = "test string";

   IntPtr ip = Marshal::StringToBSTR(s);
   BSTR bs = static_cast<BSTR>(ip.ToPointer());
   pin_ptr<BSTR> b = &bs;

   NativeTakesAString( bs );
   Marshal::FreeBSTR(ip);
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein BSTR von einer nicht verwalteten an eine nicht verwaltete Funktion übermittelt werden kann. Die empfangende verwaltete Funktion kann die Zeichenfolge in als BSTR verwenden oder <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> verwenden, um Sie in eine <xref:System.String> für die Verwendung mit anderen verwalteten Funktionen zu konvertieren. Da der Arbeitsspeicher, der den BSTR darstellt, auf dem nicht verwalteten Heap zugeordnet wird, ist keine anheften erforderlich, da keine Garbage Collection auf dem nicht verwalteten Heap vorhanden ist.

```cpp
// MarshalBSTR2.cpp
// compile with: /clr
#define WINVER 0x0502
#define _AFXDLL
#include <afxwin.h>

#include <iostream>
using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed

void ManagedTakesAString(BSTR bstr) {
   String^ s = Marshal::PtrToStringBSTR(static_cast<IntPtr>(bstr));
   Console::WriteLine("(managed) convered BSTR to String: '{0}'", s);
}

#pragma unmanaged

void UnManagedFunc() {
   BSTR bs = SysAllocString(L"test string");
   printf_s("(unmanaged) passing BSTR to managed func...\n");
   ManagedTakesAString(bs);
}

#pragma managed

int main() {
   UnManagedFunc();
}
```

## <a name="see-also"></a>Siehe auch

[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
