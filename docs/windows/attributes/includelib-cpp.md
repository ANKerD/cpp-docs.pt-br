---
title: includelib (atributo de COM do C++) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.includelib
dev_langs:
- C++
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6be5bb96f819bf1f1b0ba90d345a3c2d312daeea
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790280"
---
# <a name="includelib-c"></a>includelib (C++)

Faz com que um arquivo. IDL ou. h a serem incluídos no arquivo. idl gerado.

## <a name="syntax"></a>Sintaxe

```cpp
[ includelib(name.idl) ];
```

### <a name="parameters"></a>Parâmetros

*Name.idl*<br/>
O nome do arquivo. IDL que você deseja que seja incluído como parte do arquivo. idl gerado.

## <a name="remarks"></a>Comentários

O **includelib** C++ atributo faz com que um arquivo. IDL ou. h ser incluído no arquivo. idl gerado, após o `importlib` instrução.

## <a name="example"></a>Exemplo

O código a seguir é mostrado em um arquivo. cpp:

```cpp
// cpp_attr_ref_includelib.cpp
// compile with: /LD
[module(name="MyLib")];
[includelib("includelib.idl")];
```

## <a name="requirements"></a>Requisitos

### <a name="attribute-context"></a>Atributo de contexto

|||
|-|-|
|**Aplica-se a**|Em qualquer lugar|
|**Repetível**|Sim|
|**Atributos obrigatórios**|Nenhum|
|**Atributos inválidos**|Nenhum|

Para obter mais informações, consulte [contextos de atributo](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Consulte também

[Atributos de IDL](idl-attributes.md)<br/>
[Atributos independentes](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[importlib](importlib.md)  