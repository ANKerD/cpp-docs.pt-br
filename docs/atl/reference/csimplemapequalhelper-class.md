---
title: Classe CSimpleMapEqualHelper | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 654b801c61d00f179d6d7ef88763b323d6503873
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050574"
---
# <a name="csimplemapequalhelper-class"></a>Classe CSimpleMapEqualHelper

Essa classe é um auxiliar para o [CSimpleMap](../../atl/reference/csimplemap-class.md) classe.

## <a name="syntax"></a>Sintaxe

```
template <class TKey, class TVal>
class CSimpleMapEqualHelper
```

#### <a name="parameters"></a>Parâmetros

*TKey*<br/>
O elemento-chave.

*TVal*<br/>
O elemento de valor.

## <a name="members"></a>Membros

### <a name="public-methods"></a>Métodos Públicos

|Nome|Descrição|
|----------|-----------------|
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(Estático) Testes de duas chaves quanto à igualdade.|
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(Estático) Testa dois valores quanto à igualdade.|

## <a name="remarks"></a>Comentários

Essa classe de características é um suplemento para o `CSimpleMap` classe. Fornece métodos para comparar dois `CSimpleMap` igualdade de elementos (especificamente, os componentes de chave e valor) do objeto. Por padrão, as chaves e valores são comparados usando **Operator**, mas se o mapa contém tipos de dados complexos que não têm seu próprios operador de igualdade, essa classe pode ser substituída para fornecer a funcionalidade adicional necessária.

## <a name="requirements"></a>Requisitos

**Cabeçalho:** atlsimpcoll.h

##  <a name="isequalkey"></a>  CSimpleMapEqualHelper::IsEqualKey

Testes de duas chaves quanto à igualdade.

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>Parâmetros

*K1*<br/>
A primeira chave.

*K2*<br/>
A segunda chave.

### <a name="return-value"></a>Valor de retorno

Retorna VERDADEIRO se as chaves são iguais, caso contrário, false.

##  <a name="isequalvalue"></a>  CSimpleMapEqualHelper::IsEqualValue

Testa dois valores quanto à igualdade.

```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```

### <a name="parameters"></a>Parâmetros

*v1*<br/>
O primeiro valor.

*v2*<br/>
O segundo valor.

### <a name="return-value"></a>Valor de retorno

Retorna true se os valores forem iguais, caso contrário, false.

## <a name="see-also"></a>Consulte também

[Classe CSimpleMapEqualHelperFalse](../../atl/reference/csimplemapequalhelperfalse-class.md)<br/>
[Visão geral da classe](../../atl/atl-class-overview.md)
