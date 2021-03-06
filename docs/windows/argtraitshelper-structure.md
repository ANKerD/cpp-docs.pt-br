---
title: Estrutura ArgTraitsHelper | Microsoft Docs
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
- event/Microsoft::WRL::Details::ArgTraitsHelper::args
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraitsHelper structure
- Microsoft::WRL::Details::ArgTraitsHelper::args constant
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b608f5da893019d7700891968dcdc06489c563ea
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234223"
---
# <a name="argtraitshelper-structure"></a>Estrutura ArgTraitsHelper

Oferece suporte a infraestrutura do WRL e não se destina a ser usado diretamente do seu código.

## <a name="syntax"></a>Sintaxe

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>Parâmetros

*TDelegateInterface*<br/>
Uma interface de delegado.

## <a name="remarks"></a>Comentários

Ajuda a definir as características comuns de argumentos do delegado.

## <a name="members"></a>Membros

### <a name="public-typedefs"></a>Typedefs públicos

Nome         | Descrição
------------ | ------------------------------------------------------
`methodType` | Um sinônimo de `decltype(&TDelegateInterface::Invoke)`.
`Traits`     | Um sinônimo de `ArgTraits<methodType>`.

### <a name="public-constants"></a>Constantes públicas

Nome                           | Descrição
------------------------------ | ---------------------------------------------------------------------------------------------------------------------
[Argtraitshelper:: args](#args) | Ajuda [argtraits:: args](#args) manter a contagem do número de parâmetros `Invoke` método da interface de um delegado.

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`ArgTraitsHelper`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** Event. h

**Namespace:** Microsoft::WRL::Details

## <a name="args"></a>Argtraitshelper:: args

Oferece suporte a infraestrutura do WRL e não se destina a ser usado diretamente do seu código.

```cpp
static const int args = Traits::args;
```

### <a name="remarks"></a>Comentários

Ajuda `ArgTraitsHelper::args` manter a contagem do número de parâmetros `Invoke` método da interface de um delegado.
