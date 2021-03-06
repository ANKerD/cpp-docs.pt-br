---
title: _com_error::HelpContext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HelpContext
dev_langs:
- C++
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c2a1810410194f1261da907199a3b6665e5be30
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074364"
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext

**Seção específica da Microsoft**

Chama a função `IErrorInfo::GetHelpContext`.

## <a name="syntax"></a>Sintaxe

```
DWORD HelpContext( ) const throw( );
```

## <a name="return-value"></a>Valor de retorno

Retorna o resultado da `IErrorInfo::GetHelpContext` para o `IErrorInfo` registrado no `_com_error` objeto. Se nenhum `IErrorInfo` é registrado, ele retorna um zero.

## <a name="remarks"></a>Comentários

Qualquer falha ao chamar o `IErrorInfo::GetHelpContext` método é ignorado.

**Fim da seção específica da Microsoft**

## <a name="see-also"></a>Consulte também

[Classe _com_error](../cpp/com-error-class.md)