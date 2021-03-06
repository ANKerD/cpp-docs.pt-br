---
title: 'Classe Platform:: delegate | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Delegate
dev_langs:
- C++
helpviewer_keywords:
- Platform::Delegate Class
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78ac7cce43dbe08097c1e7b78423fadafc7f5309
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101905"
---
# <a name="platformdelegate-class"></a>Classe Platform::Delegate

Representa um objeto de função.

## <a name="syntax"></a>Sintaxe

```cpp
public delegate void delegate_name();
```

### <a name="members"></a>Membros

A classe Delegate possui os métodos Equals(), GetHashCode() e ToString() derivados do [Platform::Object Class](../cppcx/platform-object-class.md).

### <a name="remarks"></a>Comentários

Use a palavra-chave [delegate](../windows/delegate-cpp-component-extensions.md) para criar delegados; não use Platform::Delegate explicitamente. Para obter mais informações, consulte [Delegados](../cppcx/delegates-c-cx.md). Para obter um exemplo de como criar e consumir um delegado, consulte [Criando componentes do tempo de execução do Windows em C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

### <a name="requirements"></a>Requisitos

**Mínimo de cliente com suporte:** Windows 8

**Mínimo de servidor com suporte:** Windows Server 2012

**Namespace:** Platform

**Metadados:** platform.winmd

## <a name="see-also"></a>Consulte também

[Namespace Platform](../cppcx/platform-namespace-c-cx.md)