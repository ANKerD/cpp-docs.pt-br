---
title: "CDynamicAccessor::Close | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDynamicAccessor::Close"
  - "ATL.CDynamicAccessor.Close"
  - "CDynamicAccessor.Close"
  - "CDynamicAccessor::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Método Close"
ms.assetid: 2a28ded2-d7ed-4e80-90bf-143133c93feb
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::Close
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Desassocia todas as colunas, o liberará memória alocada, e libera o ponteiro de interface de [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) na classe.  
  
## Sintaxe  
  
```  
  
void Close( ) throw( );  
  
```  
  
## Requisitos  
 **Header:** atldbcli.h  
  
## Consulte também  
 [Classe CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)