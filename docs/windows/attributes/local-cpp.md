---
title: local (C++ COM atributo) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.local
dev_langs:
- C++
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e24efe4d4ad4f4e28b93503ecf82936e3113c1ed
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790278"
---
# <a name="local-c"></a>local (C++)

Quando usado no cabeçalho da interface, permite que você use o compilador MIDL como um gerador de cabeçalho. Quando usado em uma função individual, designa um procedimento de local para o qual nenhuma stubs são gerados.

## <a name="syntax"></a>Sintaxe

```cpp
[local]
```

## <a name="remarks"></a>Comentários

O **local** atributo C++ tem a mesma funcionalidade que o [local](/windows/desktop/Midl/local) atributo MIDL.

## <a name="example"></a>Exemplo

Ver [call_as](call-as.md) para obter um exemplo de como usar **local**.

## <a name="requirements"></a>Requisitos

### <a name="attribute-context"></a>Atributo de contexto

|||
|-|-|
|**Aplica-se a**|**interface**, método de interface|
|**Repetível**|Não|
|**Atributos obrigatórios**|Nenhum|
|**Atributos inválidos**|`dispinterface`|

Para obter mais informações, consulte [contextos de atributo](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Consulte também

[Atributos de IDL](idl-attributes.md)<br/>
[Atributos de interface](interface-attributes.md)<br/>
[Atributos de método](method-attributes.md)<br/>
[call_as](call-as.md)  