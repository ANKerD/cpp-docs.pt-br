---
title: __segmentlimit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __segmentlimit
dev_langs:
- C++
helpviewer_keywords:
- __segmentlimit intrinsic
- lsl instruction
ms.assetid: d0bc3630-90cb-4185-8667-686fd41e23d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d31210194f9b9f1c9808176cd7e5495df8da1ebb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395304"
---
# <a name="segmentlimit"></a>__segmentlimit

**Seção específica da Microsoft**

Gera o `lsl` instrução (limite de segmento de carga).

## <a name="syntax"></a>Sintaxe

```
unsigned long __segmentlimit( 
   unsigned long a 
);
```

#### <a name="parameters"></a>Parâmetros

*a*<br/>
[in] Uma constante que especifica o seletor de segmento.

## <a name="return-value"></a>Valor de retorno

O limite de segmento do seletor de segmento especificado pelo `a`, desde que o seletor é válido e visíveis no nível de permissão atual.

## <a name="requirements"></a>Requisitos

|Intrínseco|Arquitetura|
|---------------|------------------|
|`__segmentlimit`|x86, x64|

**Arquivo de cabeçalho** \<intrin. h >

## <a name="remarks"></a>Comentários

Se o limite de segmento não pode ser recuperado, essa instrução falhará. Em caso de falha, essa instrução limpa o sinalizador ZF e o valor retornado será indefinido.

Essa rotina só está disponível como função intrínseca.

## <a name="example"></a>Exemplo

```
#include <stdio.h>

#ifdef _M_IX86
typedef unsigned int READETYPE;
#else
typedef unsigned __int64 READETYPE;
#endif

#define EFLAGS_ZF      0x00000040
#define KGDT_R3_DATA    0x0020
#define RPL_MASK        0x3

extern "C"
{
unsigned long __segmentlimit (unsigned long);
READETYPE __readeflags();
}

#pragma intrinsic(__readeflags)
#pragma intrinsic(__segmentlimit)

int main(void)
{
   const unsigned long initsl = 0xbaadbabe;
   READETYPE eflags = 0;
   unsigned long sl = initsl;

   printf("Before: segment limit =0x%x eflags =0x%x\n", sl, eflags);
   sl = __segmentlimit(KGDT_R3_DATA + RPL_MASK);

   eflags = __readeflags();

   printf("After: segment limit =0x%x eflags =0x%x eflags.zf = %s\n", sl, eflags, (eflags & EFLAGS_ZF) ? "set" : "clear");

   // If ZF is set, the call to lsl succeeded; if ZF is clear, the call failed.
   printf("%s\n", eflags & EFLAGS_ZF ? "Success!": "Fail!");

   // You can verify the value of sl to make sure that the instruction wrote to it
   printf("sl was %s\n", (sl == initsl) ? "unchanged" : "changed");

   return 0;
}
```

```Output
Before: segment limit =0xbaadbabe eflags =0x0
After: segment limit =0xffffffff eflags =0x256 eflags.zf = set
Success!
sl was changed
```

**Fim da seção específica da Microsoft**

## <a name="see-also"></a>Consulte também

[Intrínsecos do compilador](../intrinsics/compiler-intrinsics.md)