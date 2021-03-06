---
title: faststorefence | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __faststorefence_cpp
- __faststorefence
dev_langs:
- C++
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5047dbb2023272ab03cc7d49f877f0fcc38a7b76
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402181"
---
# <a name="faststorefence"></a>__faststorefence

**Seção específica da Microsoft**

Garantias de que cada referência anterior a memória, incluindo carregar e armazena referências de memória, é globalmente visível antes de qualquer referência de memória subsequente.

## <a name="syntax"></a>Sintaxe

```
void __faststorefence();
```

## <a name="requirements"></a>Requisitos

|Intrínseco|Arquitetura|
|---------------|------------------|
|`__faststorefence`|X64|

**Arquivo de cabeçalho** \<intrin. h >

## <a name="remarks"></a>Comentários

Gera uma sequência de instruções de barreira total de memória que garantias de carregar e armazenam operações emitido antes de intrínseco são globalmente continua visível antes da execução. O efeito é comparável ao mas mais rápido do que o `_mm_mfence` intrínseco x64 todas as plataformas.

Na plataforma AMD64, essa rotina gera uma instrução que é um limite de armazenamento mais rápido do que o `sfence` instrução. Para o código crítico em termos de tempo, use intrínsecos, em vez de `_mm_sfence` somente nas plataformas AMD64. Em plataformas Intel x64, o `_mm_sfence` instrução é mais rápida.

Essa rotina só está disponível como função intrínseca.

**Fim da seção específica da Microsoft**

## <a name="see-also"></a>Consulte também

[Intrínsecos do compilador](../intrinsics/compiler-intrinsics.md)