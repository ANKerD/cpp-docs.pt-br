---
title: Classe SafeIntException | Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException Class
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException class
- SafeIntException, constructor
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4ffd82f80b8af0b53ca86ca3daded84580e1e07b
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235731"
---
# <a name="safeintexception-class"></a>Classe SafeIntException

O `SafeInt` classe usa `SafeIntException` para identificar o motivo pelo qual uma operação matemática não pode ser concluída.

## <a name="syntax"></a>Sintaxe

```cpp
class SafeIntException;
```

## <a name="members"></a>Membros

### <a name="public-constructors"></a>Construtores Públicos

Nome                                                    | Descrição
------------------------------------------------------- | ------------------------------------
[SafeIntException::SafeIntException](#safeintexception) | Cria um objeto `SafeIntException`.

## <a name="remarks"></a>Comentários

O [classe SafeInt](../windows/safeint-class.md) é a única classe que usa o `SafeIntException` classe.

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`SafeIntException`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** safeint

**Namespace:** MSL:: Utilities

## <a name="safeintexception"></a>SafeIntException::SafeIntException

Cria um objeto `SafeIntException`.

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>Parâmetros

*Código*<br/>
[in] Um valor de dados enumerado que descreve o erro que ocorreu.

### <a name="remarks"></a>Comentários

Os valores possíveis para *código* são definidos no arquivo safeint. Para sua conveniência, os possíveis valores também são listados aqui.

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`
