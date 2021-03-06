---
title: _umul128 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __umul128
dev_langs:
- C++
helpviewer_keywords:
- __umul128 intrinsic
ms.assetid: 13684df3-3ac7-467c-b258-a0e93bc490b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6ca4db1103494c8c55d792391ac714311a3a7cd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444067"
---
# <a name="umul128"></a>_umul128

**Seção específica da Microsoft**

Multiplica dois inteiros sem sinal de 64 bits passados como os primeiros dois argumentos e coloca os 64 bits altos do produto no inteiro de 64 bits sem sinal apontado pelo `HighProduct` e retorna os 64 bits baixos do produto.

## <a name="syntax"></a>Sintaxe

```
unsigned __int64 _umul128( 
   unsigned __int64 Multiplier, 
   unsigned __int64 Multiplicand, 
   unsigned __int64 *HighProduct 
);
```

#### <a name="parameters"></a>Parâmetros

*Multiplicador*<br/>
[in] O primeiro inteiro de 64 bits para multiplicar.

*Multiplicando*<br/>
[in] O segundo inteiro de 64 bits para multiplicar.

*HighProduct*<br/>
[out] Os 64 bits altos do produto.

## <a name="return-value"></a>Valor de retorno

Os 64 bits baixos do produto.

## <a name="requirements"></a>Requisitos

|Intrínseco|Arquitetura|Cabeçalho|
|---------------|------------------|------------|
|`_umul128`|ARM, x64|\<intrin.h>|

## <a name="example"></a>Exemplo

```
// umul128.c
// processor: IPF, x64

#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_umul128)

int main()
{
    unsigned __int64 a = 0x0fffffffffffffffI64;
    unsigned __int64 b = 0xf0000000I64;
    unsigned __int64 c, d;

    d = _umul128(a, b, &c);

    printf_s("%#I64x * %#I64x = %#I64x%I64x\n", a, b, c, d);
}
```

```Output
0xfffffffffffffff * 0xf0000000 = 0xeffffffffffffff10000000
```

**Fim da seção específica da Microsoft**

## <a name="see-also"></a>Consulte também

[Intrínsecos do compilador](../intrinsics/compiler-intrinsics.md)