---
title: _com_error::_com_error | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89377e33e56b0796fc850c050c8e79eac86ee07d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040460"
---
# <a name="comerrorcomerror"></a>_com_error::_com_error

**Seção específica da Microsoft**

Constrói uma **com_error** objeto.

## <a name="syntax"></a>Sintaxe

```
_com_error(
   HRESULT hr,
   IErrorInfo* perrinfo = NULL,
   bool fAddRef=false) throw( );

_com_error( const _com_error& that ) throw( );
```

#### <a name="parameters"></a>Parâmetros

*hr*<br/>
Informações de HRESULT.

*perrinfo*<br/>
Objeto `IErrorInfo`.

*faddref=false&lt;1}*<br/>
O padrão faz com que o construtor chame AddRef em não nulo `IErrorInfo` interface. Isso fornece de referência correta de contagem no caso comum em que a propriedade da interface é passada para o **com_error** objeto, como:

```cpp
throw _com_error(hr, perrinfo);
```

Se você não quiser que seu código para transferir a propriedade para o **com_error** objeto e o `AddRef` é necessário para deslocar o `Release` no **com_error** destruidor, construir o objeto como a seguir:

```cpp
_com_error err(hr, perrinfo, true);
```

*Isso*<br/>
Um existente **com_error** objeto.

## <a name="remarks"></a>Comentários

O primeiro construtor cria um novo objeto dado um HRESULT e opcional `IErrorInfo` objeto. O segundo cria uma cópia de um existente **com_error** objeto.

**Fim da seção específica da Microsoft**

## <a name="see-also"></a>Consulte também

[Classe _com_error](../cpp/com-error-class.md)