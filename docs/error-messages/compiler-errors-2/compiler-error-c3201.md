---
title: Erro do compilador C3201 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3201
dev_langs:
- C++
helpviewer_keywords:
- C3201
ms.assetid: ec19cd64-1789-40a3-b2db-dff2852b9d98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 466899de89e1f8760ec78e7d346ef949fab667be
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074247"
---
# <a name="compiler-error-c3201"></a>Erro do compilador C3201

a lista de parâmetros de modelo para o modelo de classe 'template' não coincide com a lista de parâmetros de modelo para o parâmetro de modelo 'template'

Você passou um modelo de classe no argumento para um modelo de classe que não utilize um parâmetro de modelo, ou você passou um número incompatível de argumentos de modelo para o argumento de modelo padrão.

```
// C3201.cpp
template<typename T1, typename T2>
class X1
{
};

template<template<typename T> class U = X1>   // C3201
class X2
{
};

template<template<typename T, typename V> class U = X1>   // OK
class X3
{
};
```