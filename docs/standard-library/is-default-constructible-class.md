---
title: Classe is_default_constructible | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_default_constructible
ms.assetid: dd8f1c44-dae5-4258-891f-c5e048d94092
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c60732a374c7458cc9acedc8a8e5a880ebacbc1f
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102662"
---
# <a name="isdefaultconstructible-class"></a>Classe is_default_constructible

Testa se o tipo tem um construtor padrão.

## <a name="syntax"></a>Sintaxe

```cpp
template <class Ty>
struct is_default_constructible;
```

### <a name="parameters"></a>Parâmetros

*T*<br/>
O tipo a ser consultado.

## <a name="remarks"></a>Comentários

Uma instância do predicado de tipo será verdadeira se o tipo *T* é um tipo de classe que tem um construtor padrão, caso contrário, será falsa. Isso é equivalente ao predicado `is_constructible<T>`. Tipo de *T* deve ser um tipo completo, **void**, ou uma matriz de limite desconhecido.

## <a name="example"></a>Exemplo

```cpp
#include <type_traits>
#include <iostream>

struct Simple
{
    Simple() : val(0) {}
    int val;
};

struct Simple2
{
    Simple2(int v) : val(v) {}
    int val;
};

int main()
{
    std::cout << "is_default_constructible<Simple> == " << std::boolalpha
        << std::is_default_constructible<Simple>::value << std::endl;
    std::cout << "is_default_constructible<Simple2> == " << std::boolalpha
        << std::is_default_constructible<Simple2>::value << std::endl;

    return (0);
}

```

```Output
is_default_constructible<Simple> == true
is_default_constructible<Simple2> == false
```

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Consulte também

[<type_traits>](../standard-library/type-traits.md)<br/>
