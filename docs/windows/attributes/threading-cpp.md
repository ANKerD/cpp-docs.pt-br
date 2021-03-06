---
title: Threading (atributo de COM do C++) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.threading
dev_langs:
- C++
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d6b343ec9342199727122ac89f6df77e532429ad
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790290"
---
# <a name="threading-c"></a>threading (C++)

Especifica o modelo de threading para um objeto COM.

## <a name="syntax"></a>Sintaxe

```cpp
[ threading(model=enumeration) ]
```

### <a name="parameters"></a>Parâmetros

*model*<br/>
(Opcional) Um dos seguintes modelos de threads:

- `apartment` (apartment threading)

- `neutral` (Componentes do .NET framework sem interface do usuário)

- `single` (threading simples)

- `free` (gratuito threading)

- `both` (apartment e threading livre)

O valor padrão é `apartment`.

## <a name="remarks"></a>Comentários

O **threading** atributo C++ não aparece no arquivo. idl gerado, mas será usado na implementação do seu objeto COM.

Em projetos ATL, se o [coclass](coclass.md) atributo também estiver presente, o modelo de threading especificado por *modelo* é passado como o parâmetro de modelo para o [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) classe , inseridos pelo `coclass` atributo.

O **threading** atributo também protege o acesso a um [event_source](event-source.md).

## <a name="example"></a>Exemplo

Consulte a [licenciado](licensed.md) exemplo para uso do exemplo **threading**.

## <a name="requirements"></a>Requisitos

### <a name="attribute-context"></a>Atributo de contexto

|||
|-|-|
|**Aplica-se a**|**classe**, **struct**|
|**Repetível**|Não|
|**Atributos obrigatórios**|**coclass**|
|**Atributos inválidos**|Nenhum|

Para obter mais informações sobre os contextos de atributo, consulte [contextos de atributo](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Consulte também

[Atributos de COM](com-attributes.md)<br/>
[Atributos Typedef, Enum, Union e Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Atributos de classe](class-attributes.md)<br/>
[Suporte de multithreading para código anterior (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Apartments neutros](/windows/desktop/cossdk/neutral-apartments)  