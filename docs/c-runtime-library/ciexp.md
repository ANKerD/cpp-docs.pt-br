---
title: _CIexp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _CIexp
apilocation:
- msvcr120.dll
- msvcr80.dll
- msvcr110.dll
- msvcr100.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- CIexp
- _CIexp
dev_langs:
- C++
helpviewer_keywords:
- CIexp intrinsic
- _CIexp intrinsic
ms.assetid: f8a3e3b7-fa57-41a3-9983-6c81914cbb55
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ede1870c17a5c78a1580bee03cc84908abdf2f33
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234080"
---
# <a name="ciexp"></a>_CIexp

Calcula o exponencial do valor superior na pilha.

## <a name="syntax"></a>Sintaxe

```
void __cdecl _CIexp();
```

## <a name="remarks"></a>Comentários

Esta versão da função `exp` tem uma convenção de chamada especializada que o compilador compreende. Ele acelera a execução porque ele evita que cópias sejam geradas e ajuda na alocação de registro.

O valor resultante é colocado na parte superior da pilha.

## <a name="requirements"></a>Requisitos

**Plataforma:** x86

## <a name="see-also"></a>Consulte também

[Referência da Função Alfabética](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[exp, expf, expl](../c-runtime-library/reference/exp-expf.md)