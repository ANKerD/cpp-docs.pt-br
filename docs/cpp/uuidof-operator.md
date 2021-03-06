---
title: operador uuidof | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __LIBID_cpp
- __uuidof_cpp
dev_langs:
- C++
helpviewer_keywords:
- __uuidof keyword [C++]
- __LIBID_ keyword [C++]
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84fd779d50fb481cffc97b61a65f255c6c8f52a1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056724"
---
# <a name="uuidof-operator"></a>Operador __uuidof

**Seção específica da Microsoft**

Recupera o GUID vinculado à expressão.

## <a name="syntax"></a>Sintaxe

```
__uuidof (expression)
```

## <a name="remarks"></a>Comentários

O *expressão* pode ser um nome de tipo, ponteiro, referência ou matriz desse tipo, um modelo especializado nesses tipos ou uma variável desses tipos. O argumento é válido enquanto o compilador puder usá-lo para localizar o GUID vinculado.

Um caso especial desse intrínseco é quando qualquer um dos **0** ou nulo for fornecido como o argumento. Nesse caso, **uuidof** retornará um GUID composto de zero.

Use essa palavra-chave para extrair o GUID vinculado a:

- Um objeto, o [uuid](../cpp/uuid-cpp.md) atributo estendido.

- Um bloco de biblioteca criado com o [módulo](../windows/module-cpp.md) atributo.

> [!NOTE]
>  Em uma compilação de depuração **uuidof** sempre inicializa um objeto dinamicamente (em tempo de execução). Em um build de versão **uuidof** pode estaticamente (no tempo de compilação) inicializar um objeto.

## <a name="example"></a>Exemplo

O código a seguir (compilado com ole32.lib) exibirá o uuid de um bloco de biblioteca criado com o atributo module:

```cpp
// expre_uuidof.cpp
// compile with: ole32.lib
#include "stdio.h"
#include "windows.h"

[emitidl];
[module(name="MyLib")];
[export]
struct stuff {
   int i;
};

int main() {
   LPOLESTR lpolestr;
   StringFromCLSID(__uuidof(MyLib), &lpolestr);
   wprintf_s(L"%s", lpolestr);
   CoTaskMemFree(lpolestr);
}
```

## <a name="comments"></a>Comentários

Em casos em que o nome da biblioteca não está no escopo, você pode usar `__LIBID_` em vez de **uuidof**. Por exemplo:

```cpp
StringFromCLSID(__LIBID_, &lpolestr);
```

**Fim da seção específica da Microsoft**

## <a name="see-also"></a>Consulte também

[Expressões com operadores unários](../cpp/expressions-with-unary-operators.md)<br/>
[Palavras-chave](../cpp/keywords-cpp.md)