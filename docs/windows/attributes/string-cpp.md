---
title: cadeia de caracteres (C++ COM atributo) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.string
dev_langs:
- C++
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 24d11a056d248e27be236f710cdd0532b3beca2d
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790245"
---
# <a name="string-c"></a>string (C++)

Indica que o unidimensional **char**, **wchar_t**, `byte` (ou equivalente) matriz ou o ponteiro para essa matriz deve ser tratado como uma cadeia de caracteres.

## <a name="syntax"></a>Sintaxe

```cpp
[string]
```

## <a name="remarks"></a>Comentários

O **cadeia de caracteres** atributo C++ tem a mesma funcionalidade que o [cadeia de caracteres](/windows/desktop/Midl/string) atributo MIDL.

## <a name="example"></a>Exemplo

O código a seguir mostra como usar **cadeia de caracteres** em uma interface e em um typedef:

```cpp
// cpp_attr_ref_string.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, string] typedef char a[21];
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   [id(1)] HRESULT Method3([in, string] char *pC);
};
```

## <a name="requirements"></a>Requisitos

### <a name="attribute-context"></a>Atributo de contexto

|||
|-|-|
|**Aplica-se a**|Matriz ou ponteiro para uma matriz, o parâmetro de interface, o método de interface|
|**Repetível**|Não|
|**Atributos obrigatórios**|Nenhum|
|**Atributos inválidos**|Nenhum|

Para obter mais informações sobre os contextos de atributo, consulte [contextos de atributo](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Consulte também

[Atributos de IDL](idl-attributes.md)<br/>
[Atributos de matriz](array-attributes.md)<br/>
[export](export.md)  