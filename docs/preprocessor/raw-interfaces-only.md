---
title: raw_interfaces_only | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_interfaces_only
dev_langs:
- C++
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f217c0dad3bf74ab930cf1f66392fe22d9df832
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446538"
---
# <a name="rawinterfacesonly"></a>raw_interfaces_only
**Específico do C++**  
  
Suprime a geração de funções de wrapper de tratamento de erros e [propriedade](../cpp/property-cpp.md) declarações que usam essas funções wrapper.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
raw_interfaces_only  
```  
  
## <a name="remarks"></a>Comentários  
 
O **raw_interfaces_only** atributo também faz com que o prefixo padrão usado na nomeação as funções não são da propriedade a ser removido. Normalmente, é o prefixo **RAW _**. Se esse atributo for especificado, os nomes de função serão diretamente da biblioteca de tipos.  
  
Esse atributo permite que você exiba somente o conteúdo de nível baixo da biblioteca de tipos.  
  
**FIM de específico de C++**  
  
## <a name="see-also"></a>Consulte também  
 
[atributos de #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import diretiva](../preprocessor/hash-import-directive-cpp.md)