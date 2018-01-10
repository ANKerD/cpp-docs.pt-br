---
title: __shiftright128 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __shiftright128
dev_langs: C++
helpviewer_keywords: __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 228c624c5c752a7c61178b60f8e75817fff62505
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="shiftright128"></a>__shiftright128
**Seção específica da Microsoft**  
  
 Desloca uma quantidade de 128 bits, representada como duas quantidades de 64 bits `LowPart` e `HighPart`, à esquerda por um número de bits especificado pelo `Shift` e retorna os 64 bits baixos do resultado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
unsigned __int64 __shiftright128(   
   unsigned __int64 LowPart,   
   unsigned __int64 HighPart,   
   unsigned char Shift   
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 [in] `LowPart`  
 Os 64 bits baixos da quantidade de 128 bits a deslocar.  
  
 [in] `HighPart`  
 Os 64 bits altos da quantidade de 128 bits a deslocar.  
  
 [in] `Shift`  
 O número de bits a deslocar.  
  
## <a name="return-value"></a>Valor de retorno  
 64 bits baixos do resultado.  
  
## <a name="requirements"></a>Requisitos  
  
|Intrínseco|Arquitetura|  
|---------------|------------------|  
|`__shiftright128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Arquivo de cabeçalho** \<intrin.h >  
  
## <a name="remarks"></a>Comentários  
 O valor `Shift` é sempre módulo 64 para que, por exemplo, se você chamar, `__shiftright128(0, 1, 64)`, a função deslocará os bits altos `0` para a esquerda e retornará uma parte baixa de `0` e não `1` como era previsto.  
  
## <a name="example"></a>Exemplo  
 Para obter um exemplo, consulte [__shiftleft128](../intrinsics/shiftleft128.md).  
  
**Fim da seção específica da Microsoft**  
  
## <a name="see-also"></a>Consulte também  
 [__shiftleft128](../intrinsics/shiftleft128.md)   
 [Intrínsecos do compilador](../intrinsics/compiler-intrinsics.md)