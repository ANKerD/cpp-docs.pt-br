---
title: Estrutura IsSame | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsSame
- internal/Microsoft::WRL::Details::IsSame::value
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::IsSame structure
- Microsoft::WRL::Details::IsSame::value constant
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 26ecab69c2c31db51e137ad012bf67541e03a095
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788455"
---
# <a name="issame-structure"></a>Estrutura IsSame

Oferece suporte a infraestrutura do WRL e não se destina a ser usado diretamente do seu código.

## <a name="syntax"></a>Sintaxe

```cpp
template <typename T1, typename T2>
struct IsSame;

template <typename T1>
struct IsSame<T1, T1>;
```

### <a name="parameters"></a>Parâmetros

*T1*<br/>
Um tipo.

*T2*<br/>
Outro tipo.

## <a name="remarks"></a>Comentários

Testes se um tipo especificado é igual a outro tipo especificado.

## <a name="members"></a>Membros

### <a name="public-constants"></a>Constantes públicas

Nome                    | Descrição
----------------------- | --------------------------------------------------
[Issame:: Value](#value) | Indica se um tipo é igual a outro.

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`IsSame`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="value"></a>Issame:: Value

Oferece suporte a infraestrutura do WRL e não se destina a ser usado diretamente do seu código.

```cpp
template <typename T1, typename T2>
struct IsSame
{
    static const bool value = false;
};

template <typename T1>
struct IsSame<T1, T1>
{
    static const bool value = true;
};
```

### <a name="remarks"></a>Comentários

Indica se um tipo é igual a outro.

`value` está `true` se os parâmetros de modelo são os mesmos, e `false` se os parâmetros de modelo são diferentes.
