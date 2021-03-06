---
title: _CIfmod | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _CIfmod
apilocation:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- _CIfmod
- CIfmod
dev_langs:
- C++
helpviewer_keywords:
- CIfmod intrinsic
- _CIfmod intrinsic
ms.assetid: 7c050653-7ec6-4810-b3a7-7a0057ea65ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 605febb4ad76051ca79e0b03388fbb7739ebb076
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234589"
---
# <a name="cifmod"></a>_CIfmod

Calcula o restante do ponto flutuante dos dois valores superiores na pilha.

## <a name="syntax"></a>Sintaxe

```
void __cdecl _CIfmod();
```

## <a name="remarks"></a>Comentários

Esta versão da função `fmod` tem uma convenção de chamada especializada que o compilador compreende. Ele acelera a execução porque ele evita que cópias sejam geradas e ajuda na alocação de registro.

O valor resultante é colocado na parte superior da pilha.

## <a name="requirements"></a>Requisitos

**Plataforma:** x86

## <a name="see-also"></a>Consulte também

[Referência da Função Alfabética](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[fmod, fmodf](../c-runtime-library/reference/fmod-fmodf.md)