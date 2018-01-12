---
title: "TN047: Relaxando requisitos de transação do banco de dados | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.data
dev_langs: C++
helpviewer_keywords: TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 92631d96e8782a80275695ef4bf2623dc1bff833
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047: relaxando requisitos de transação de banco de dados
Esta Observação técnica, que abordamos os requisitos de transação das classes de banco de dados ODBC do MFC, agora é obsoleta. Antes de MFC 4.2, as classes de banco de dados necessários que cursores seja preservado no conjunto de registros após um **CommitTrans** ou **reversão** operação. Se o driver ODBC e um DBMS não oferecia suporte a esse nível de preservação de cursor, as classes de banco de dados não tiver habilitado a transações.  
  
 A partir do MFC 4.2, as classes de banco de dados têm reduzidas a restrição de exigir a preservação do cursor. Transações serão habilitadas se o driver oferece suporte a eles. No entanto, agora você deve verificar o efeito de um **CommitTrans** ou **reversão** operação no conjunto de registros aberto. Consulte as funções de membro [CDatabase::GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) e [CDatabase::GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) para obter mais informações.  
  
## <a name="see-also"></a>Consulte também  
 [Observações técnicas por número](../mfc/technical-notes-by-number.md)   
 [Observações técnicas por categoria](../mfc/technical-notes-by-category.md)
