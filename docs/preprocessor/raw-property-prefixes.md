---
title: raw_property_prefixes | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ae69e26077692188b8e013e949592df26d7701a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420394"
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes
**Específico do C++**  
  
Especifica prefixos alternativos para três métodos da propriedade.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
### <a name="parameters"></a>Parâmetros  
*GetPrefix*  
Prefixo a ser usado para o `propget` métodos.  
  
*PutPrefix*  
Prefixo a ser usado para o `propput` métodos.  
  
*PutRefPrefix*  
Prefixo a ser usado para o `propputref` métodos.  
  
## <a name="remarks"></a>Comentários  
 
Por padrão, de baixo nível `propget`, `propput`, e `propputref` métodos são expostos por funções de membro nomeadas com prefixos de **get _**, **Put _**, e **PUTREF _** respectivamente. Esses prefixos são compatíveis com os nomes usados nos arquivos de cabeçalho gerados pelo MIDL.  
  
**FIM de específico de C++**  
  
## <a name="see-also"></a>Consulte também  
 
[atributos de #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import diretiva](../preprocessor/hash-import-directive-cpp.md)