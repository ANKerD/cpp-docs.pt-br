---
title: Estrutura InterfaceListHelper | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceListHelper
dev_langs:
- C++
helpviewer_keywords:
- InterfaceListHelper structure
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b8d8b44f6b3732c19977e6839e96d4ab5013a112
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788403"
---
# <a name="interfacelisthelper-structure"></a>Estrutura InterfaceListHelper

Oferece suporte a infraestrutura do WRL e não se destina a ser usado diretamente do seu código.

## <a name="syntax"></a>Sintaxe

```cpp
template <
    typename T0,
    typename T1 = Nil,
    typename T2 = Nil,
    typename T3 = Nil,
    typename T4 = Nil,
    typename T5 = Nil,
    typename T6 = Nil,
    typename T7 = Nil,
    typename T8 = Nil,
    typename T9 = Nil
>
struct InterfaceListHelper;

template <typename T0>
struct InterfaceListHelper<T0, Nil, Nil, Nil, Nil, Nil, Nil, Nil, Nil>;
```

### <a name="parameters"></a>Parâmetros

*T0*<br/>
Parâmetro de modelo 0, que é necessário.

*T1*<br/>
Parâmetro de modelo 1, que, por padrão, não é especificado.

*T2*<br/>
Parâmetro de modelo 2, que, por padrão, não é especificado. O terceiro parâmetro de modelo.

*T3*<br/>
Parâmetro de modelo 3, que, por padrão, não é especificado.

*T4*<br/>
Parâmetro de modelo 4, que, por padrão, não é especificado.

*T5*<br/>
Parâmetro de modelo 5, que, por padrão, não é especificado.

*T6*<br/>
Parâmetro de modelo 6, que, por padrão, não é especificado.

*T7*<br/>
Parâmetro de modelo 7, que, por padrão, não é especificado.

*T8*<br/>
Parâmetro de modelo 8, que, por padrão, não é especificado.

*T9*<br/>
Parâmetro de modelo 9, que, por padrão, não é especificado.

## <a name="remarks"></a>Comentários

Cria um `InterfaceList` tipo por recursivamente aplicando os argumentos de parâmetro de modelo especificado.

O **InterfaceListHelper** modelo usa o parâmetro de modelo *T0* para definir o primeiro membro de dados em um `InterfaceList` estrutura e, em seguida, recursivamente se aplica a  **InterfaceListHelper** modelo para quaisquer parâmetros restantes do modelo. **InterfaceListHelper** para quando não houver nenhum parâmetro de modelo restantes.

## <a name="members"></a>Membros

### <a name="public-typedefs"></a>Typedefs públicos

|Nome|Descrição|
|----------|-----------------|
|`TypeT`|Um sinônimo para o tipo de InterfaceList.|

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`InterfaceListHelper`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** Implements. h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Consulte também

[Namespace Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)