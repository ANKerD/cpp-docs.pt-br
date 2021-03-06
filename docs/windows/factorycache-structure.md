---
title: Estrutura FactoryCache | Microsoft Docs
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
- module/Microsoft::WRL::Details::FactoryCache::cookie
- module/Microsoft::WRL::Details::FactoryCache::factory
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::FactoryCache structure
- Microsoft::WRL::Details::FactoryCache::cookie data member
- Microsoft::WRL::Details::FactoryCache::factory data member
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d56779b5df33f75c9147d34b55f8c2fc65204a82
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234535"
---
# <a name="factorycache-structure"></a>Estrutura FactoryCache

Oferece suporte a infraestrutura de biblioteca de modelos de C++ de tempo de execução do Windows e não se destina a ser usado diretamente do seu código.

## <a name="syntax"></a>Sintaxe

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>Comentários

Contém o local de uma fábrica de classes e um valor que identifica um registrado wrt ou objeto de classe COM.

## <a name="members"></a>Membros

### <a name="public-data-members"></a>Membros de Dados Públicos

Nome                              | Descrição
--------------------------------- | ------------------------------------------------------------------------------------------------------------------------------
[Factorycache:: cookie](#cookie)   | Contém um valor que identifica um objeto de classe de tempo de execução do Windows ou COM registrado e é usado posteriormente para cancelar o registro do objeto.
[Factorycache:: Factory](#factory) | Aponta para uma fábrica de classes de tempo de execução do Windows ou COM.

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`FactoryCache`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="cookie"></a>Factorycache:: cookie

Oferece suporte a infraestrutura de biblioteca de modelos de C++ de tempo de execução do Windows e não se destina a ser usado diretamente do seu código.

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

### <a name="remarks"></a>Comentários

Contém um valor que identifica um objeto de classe de tempo de execução do Windows ou COM registrado e é usado posteriormente para cancelar o registro do objeto.

## <a name="factory"></a>Factorycache:: Factory

Oferece suporte a infraestrutura de biblioteca de modelos de C++ de tempo de execução do Windows e não se destina a ser usado diretamente do seu código.

```cpp
IUnknown* factory;
```

### <a name="remarks"></a>Comentários

Aponta para uma fábrica de classes de tempo de execução do Windows ou COM.
