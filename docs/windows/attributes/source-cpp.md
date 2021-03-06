---
title: fonte (C++ COM atributo) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.source
dev_langs:
- C++
helpviewer_keywords:
- source attribute
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 81ea5c45aff148d8f0683d0058963571bc02a57a
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790218"
---
# <a name="source-c"></a>source (C++)

Em uma classe, especifica as interfaces de origem do objeto COM para pontos de conexão. Em uma propriedade ou método, indica que o membro retorna um objeto ou uma VARIANTE que é uma origem de eventos.

## <a name="syntax"></a>Sintaxe

```cpp
[ source(interfaces) ]
```

### <a name="parameters"></a>Parâmetros

*interfaces*<br/>
Uma ou mais interfaces que você especifique quando você aplica a origem do atributo a uma classe. Esse parâmetro não é usado quando o código-fonte é aplicada a uma propriedade ou método.

## <a name="remarks"></a>Comentários

O **fonte** atributo C++ tem a mesma funcionalidade que o [origem](/windows/desktop/Midl/source) atributo MIDL.

Você pode usar o [padrão](default-cpp.md) atributo para especificar a interface de origem padrão para um objeto.

## <a name="example"></a>Exemplo

```cpp
// cpp_attr_ref_source.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid(11111111-1111-1111-1111-111111111111)]
__interface b
{
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]
   HRESULT get_I([out, retval]long *i);
};

[object, uuid(11111111-1111-1111-1111-111111111131)]
__interface c
{
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]
   HRESULT et_I([out, retval]long *i);
};

[coclass, default(c), uuid(11111111-1111-1111-1111-111111111132)]
class N : public b
{
};

[coclass, source(c), default(b, c), uuid(11111111-1111-1111-1111-111111111133)]
class NN : public b
{
};
```

## <a name="requirements"></a>Requisitos

### <a name="attribute-context"></a>Atributo de contexto

|||
|-|-|
|**Aplica-se a**|**classe**, **struct**, **interface**|
|**Repetível**|Não|
|**Atributos obrigatórios**|`coclass` (quando aplicado à classe ou struct)|
|**Atributos inválidos**|Nenhum|

Para obter mais informações sobre os contextos de atributo, consulte [contextos de atributo](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Consulte também

[Atributos de IDL](idl-attributes.md)<br/>
[Atributos de classe](class-attributes.md)<br/>
[Atributos de método](method-attributes.md)<br/>
[coclass](coclass.md)  