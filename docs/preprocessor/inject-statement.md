---
title: inject_statement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inject_statement
dev_langs:
- C++
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb3bdc2b4e00cd9e2167adeb0ad7d3023af9eb2e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384202"
---
# <a name="injectstatement"></a>inject_statement
**Específico do C++**  
  
Insere seu argumento como texto de origem no cabeçalho da biblioteca de tipos.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
inject_statement("source_text")  
```  
  
### <a name="parameters"></a>Parâmetros  
*source_text*  
Texto de origem a ser inserido no arquivo de cabeçalho da biblioteca de tipos.  
  
## <a name="remarks"></a>Comentários  
 
O texto é colocado no início da declaração do namespace que envolve o conteúdo da biblioteca de tipos no arquivo de cabeçalho.  
  
**FIM de específico de C++**  
  
## <a name="see-also"></a>Consulte também  
 
[atributos de #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import diretiva](../preprocessor/hash-import-directive-cpp.md)