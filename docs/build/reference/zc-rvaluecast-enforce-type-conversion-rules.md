---
title: '/ZC: rvaluecast (Impor regras de conversão de tipo) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 626cabbec169d541a63dd65c22a7380718613b79
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706583"
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast (Aplicar regras de conversão de tipo)

Quando o **/ZC: rvaluecast** opção for especificada, o compilador identifica corretamente um tipo de referência de rvalue como resultado de uma operação de conversão de acordo com o padrão c++11. Quando a opção não está especificada, o comportamento do compilador é o mesmo do Visual Studio 2012.

## <a name="syntax"></a>Sintaxe

> **/Zc:rvalueCast**[**-**]

## <a name="remarks"></a>Comentários

Se **/ZC: rvaluecast** for especificado, o compilador seguirá a seção 5.4 do padrão c++11 e tratará apenas expressões de conversão que resultem em tipos de não referência e expressões de conversão que resultem em referências rvalue para tipos de não função como tipos rvalue. Por padrão, ou se **/Zc:rvalueCast-** for especificado, o compilador não é compatível e trata todas as expressões de conversão que resultem em referências de rvalue como rvalues. Para conformidade e para eliminar erros no uso de conversões, recomendamos que você use **/ZC: rvaluecast**.

Por padrão, **/ZC: rvaluecast** está desativado (**/Zc:rvalueCast-**). O [/permissive--](permissive-standards-conformance.md) opção de compilador define implicitamente essa opção, mas ele pode ser substituído usando **/Zc:rvalueCast-**.

Use **/ZC: rvaluecast** se você passar uma expressão de conversão como um argumento para uma função que usa um tipo de referência de rvalue. O comportamento padrão causa o erro do compilador [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) quando o compilador determina incorretamente o tipo da expressão cast. Este exemplo mostra um erro do compilador em correto código quando **/ZC: rvaluecast** não for especificado:

```cpp
// Test of /Zc:rvalueCast
// compile by using:
// cl /c /Zc:rvalueCast- make_thing.cpp
// cl /c /Zc:rvalueCast make_thing.cpp

#include <utility>

template <typename T>
struct Thing {
   // Construct a Thing by using two rvalue reference parameters
   Thing(T&& t1, T&& t2)
      : thing1(t1), thing2(t2) {}

   T& thing1;
   T& thing2;
};

// Create a Thing, using move semantics if possible
template <typename T>
Thing<T> make_thing(T&& t1, T&& t2)
{
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));
}

struct Test1 {
   long a;
   long b;

   Thing<long> test() {
      // Use identity casts to create rvalues as arguments
      return make_thing(static_cast<long>(a), static_cast<long>(b));
   }
};
```

Talvez o comportamento do compilador padrão não relate o erro C2102 quando apropriado. Neste exemplo, o compilador não relatará um erro se o endereço de um rvalue criado por uma conversão de identidade é usado quando **/ZC: rvaluecast** não for especificado:

```cpp
int main() {
   int a = 1;
   int *p = &a;   // Okay, take address of lvalue
                  // Identity cast creates rvalue from lvalue;
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value
}
```

Para obter mais informações sobre problemas de conformidade no Visual C++, consulte [comportamento não padrão](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do compilador no ambiente de desenvolvimento do Visual Studio

1. Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, confira [Trabalhando com propriedades do projeto](../../ide/working-with-project-properties.md).

1. Selecione o **propriedades de configuração** > **C/C++** > **linha de comando** página de propriedades.

1. Modificar a **opções adicionais** propriedade incluir **/ZC: rvaluecast** e, em seguida, escolha **Okey**.

## <a name="see-also"></a>Consulte também

[/Zc (conformidade)](../../build/reference/zc-conformance.md)<br/>
