---
title: Classe CDefaultCharTraits | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69b6a7b94e993641452154ede11d65929424df5e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095749"
---
# <a name="cdefaultchartraits-class"></a>Classe CDefaultCharTraits

Essa classe fornece duas funções estáticas para a conversão de caracteres entre letras maiusculas e minúsculas.

## <a name="syntax"></a>Sintaxe

```
template <typename T>
class CDefaultCharTraits
```

#### <a name="parameters"></a>Parâmetros

*T*<br/>
O tipo de dados a serem armazenados na coleção.

## <a name="members"></a>Membros

### <a name="public-methods"></a>Métodos Públicos

|Nome|Descrição|
|----------|-----------------|
|[CDefaultCharTraits::CharToLower](#chartolower)|(Estático) Chame essa função para converter um caractere em maiusculas.|
|[CDefaultCharTraits::CharToUpper](#chartoupper)|(Estático) Chame essa função para converter um caractere em minúsculas.|

## <a name="remarks"></a>Comentários

Essa classe fornece funções que são utilizadas pela classe [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).

## <a name="requirements"></a>Requisitos

**Cabeçalho:** atlcoll.h

##  <a name="chartolower"></a>  CDefaultCharTraits::CharToLower

Chame essa função para converter um caractere em minúsculas.

```
static wchar_t CharToLower(wchar_t x);
static char CharToLower(char x);
```

### <a name="parameters"></a>Parâmetros

*x*<br/>
O caractere a ser convertido em minúsculas.

### <a name="example"></a>Exemplo

[!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]

##  <a name="chartoupper"></a>  CDefaultCharTraits::CharToUpper

Chame essa função para converter um caractere em maiusculas.

```
static wchar_t CharToUpper(wchar_t x);
static char CharToUpper(char x);
```

### <a name="parameters"></a>Parâmetros

*x*<br/>
O caractere a ser convertido em maiúsculas.

## <a name="see-also"></a>Consulte também

[Visão geral da classe](../../atl/atl-class-overview.md)
