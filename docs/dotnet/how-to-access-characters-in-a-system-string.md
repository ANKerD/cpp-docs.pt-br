---
title: 'Como: acessar caracteres em um System:: String | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6c5c4c6032330a58a6f1ea9fb85d3da57c28a177
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416182"
---
# <a name="how-to-access-characters-in-a-systemstring"></a>Como acessar caracteres em um System::String

Você pode acessar os caracteres de um <xref:System.String> funções de objeto para chamadas de alto desempenho para não gerenciado que usam `wchar_t*` cadeias de caracteres. O método produz um ponteiro interior para o primeiro caractere do <xref:System.String> objeto. Esse ponteiro pode ser manipulado diretamente ou fixado e passado para uma função esperando um comum `wchar_t` cadeia de caracteres.

## <a name="example"></a>Exemplo

`PtrToStringChars` Retorna um <xref:System.Char>, que é um ponteiro interior (também conhecido como um `byref`). Como tal, está sujeito à coleta de lixo. Você não precisa que fixar esse ponteiro, a menos que você vai passá-lo para uma função nativa.

Considere o código a seguir.  A fixação não é necessária porque `ppchar` é um ponteiro interior, e se o coletor de lixo move a cadeia de caracteres que ele aponte para, ele também atualizará `ppchar`. Sem um [pin_ptr (C + + / CLI)](../windows/pin-ptr-cpp-cli.md), o código funcionará e não tê o potencial impacto no desempenho causada pela fixação.

Se você passar `ppchar` para uma função nativa, em seguida, ele deve ser um ponteiro de fixação; o coletor de lixo não será capaz de atualizar todos os ponteiros no quadro de pilha não gerenciada.

```
// PtrToStringChars.cpp
// compile with: /clr
#include<vcclr.h>
using namespace System;

int main() {
   String ^ mystring = "abcdefg";

   interior_ptr<const Char> ppchar = PtrToStringChars( mystring );

   for ( ; *ppchar != L'\0'; ++ppchar )
      Console::Write(*ppchar);
}
```

```Output
abcdefg
```

## <a name="example"></a>Exemplo

Este exemplo mostra onde a anexação é necessária.

```
// PtrToStringChars_2.cpp
// compile with: /clr
#include <string.h>
#include <vcclr.h>
// using namespace System;

size_t getlen(System::String ^ s) {
   // Since this is an outside string, we want to be secure.
   // To be secure, we need a maximum size.
   size_t maxsize = 256;
   // make sure it doesn't move during the unmanaged call
   pin_ptr<const wchar_t> pinchars = PtrToStringChars(s);
   return wcsnlen(pinchars, maxsize);
};

int main() {
   System::Console::WriteLine(getlen("testing"));
}
```

```Output
7
```

## <a name="example"></a>Exemplo

Um ponteiro interior tem todas as propriedades de um ponteiro de C++ nativo. Por exemplo, você pode usá-lo para percorrer uma estrutura de dados vinculado e fazer inserções e exclusões usando somente um ponteiro:

```
// PtrToStringChars_3.cpp
// compile with: /clr /LD
using namespace System;
ref struct ListNode {
   Int32 elem;
   ListNode ^ Next;
};

void deleteNode( ListNode ^ list, Int32 e ) {
   interior_ptr<ListNode ^> ptrToNext = &list;
   while (*ptrToNext != nullptr) {
      if ( (*ptrToNext) -> elem == e )
         *ptrToNext = (*ptrToNext) -> Next;   // delete node
      else
         ptrToNext = &(*ptrToNext) -> Next;   // move to next node
   }
}
```

## <a name="see-also"></a>Consulte também

[Usando interop do C++ (PInvoke implícito)](../dotnet/using-cpp-interop-implicit-pinvoke.md)