---
title: COLUMN_ENTRY_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COLUMN_ENTRY_TYPE
dev_langs: C++
helpviewer_keywords: COLUMN_ENTRY_TYPE macro
ms.assetid: ac424261-ff6c-443b-a197-2cec8d78d738
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 425f7e38002976d5510707768774f924f3627bc0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="columnentrytype"></a>COLUMN_ENTRY_TYPE
Representa uma associação para a coluna específica no banco de dados. Dá suporte a `type` parâmetro.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
COLUMN_ENTRY_TYPE (  
nOrdinal  
,   
wType  
,   
data  
 )  
  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `nOrdinal`  
 [in] O número da coluna.  
  
 `wType`  
 [in] Tipo de dados de entrada da coluna.  
  
 `data`  
 [in] O membro de dados correspondente no registro do usuário.  
  
## <a name="remarks"></a>Comentários  
 Essa macro é uma variante especializada do [COLUMN_ENTRY](../../data/oledb/column-entry.md) macro que fornece um meio de especificar o tipo de dados.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atldbcli.h  
  
## <a name="see-also"></a>Consulte também  
 [Macros e funções globais para modelos de consumidor OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)