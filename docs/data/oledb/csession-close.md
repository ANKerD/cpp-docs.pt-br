---
title: "CSession::Close | Microsoft Docs"
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
  - "CSession::Close"
  - "ATL.CSession.Close"
  - "CSession.Close"
  - "ATL::CSession::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Método Close"
ms.assetid: dc36c4c0-e588-4c0b-91d1-fc7dc5c8e7f4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSession::Close
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fecha a sessão, que foi aberta por [CSession::Open](../../data/oledb/csession-open.md).  
  
## Sintaxe  
  
```  
  
void Close( ) throw( );  
  
```  
  
## Comentários  
 Libera o ponteiro de **m\_spOpenRowset** .  
  
## Requisitos  
 **Header:** atldbcli.h  
  
## Consulte também  
 [Classe CSession](../../data/oledb/csession-class.md)