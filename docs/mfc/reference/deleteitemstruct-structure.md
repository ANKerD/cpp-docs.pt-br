---
title: Estrutura DELETEITEMSTRUCT | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DELETEITEMSTRUCT
dev_langs: C++
helpviewer_keywords: DELETEITEMSTRUCT structure [MFC]
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5be80d8b139f04daa0c44fc2808f61538843e3e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="deleteitemstruct-structure"></a>Estrutura DELETEITEMSTRUCT
O `DELETEITEMSTRUCT` estrutura descreve um item excluído de caixa de listagem ou caixa de combinação desenhados pelo proprietário.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
typedef struct tagDELETEITEMSTRUCT { /* ditms */  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    HWND hwndItem;  
    UINT itemData;  
} DELETEITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `CtlType`  
 Especifica **ODT_LISTBOX** (uma caixa de listagem de desenho proprietário) ou **ODT_COMBOBOX** (uma caixa de combinação do desenho proprietário).  
  
 `CtlID`  
 Especifica o identificador da caixa de listagem ou caixa de combinação.  
  
 `itemID`  
 Especifica o índice do item na caixa de listagem ou caixa de combinação que está sendo removido.  
  
 `hwndItem`  
 Identifica o controle.  
  
 `itemData`  
 Especifica os dados definidos pelo aplicativo para o item. Esse valor é passado para o controle no **lParam** parâmetro da mensagem que adiciona o item à caixa de listagem ou caixa de combinação.  
  
## <a name="remarks"></a>Comentários  
 Quando um item é removido da caixa de listagem ou caixa de combinação ou caixa de listagem ou caixa de combinação é destruída, o Windows envia o `WM_DELETEITEM` mensagem para o proprietário de cada item excluído. O **lParam** parâmetro da mensagem contém um ponteiro para essa estrutura.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atldbcli.h  
  
## <a name="see-also"></a>Consulte também  
 [Estruturas, estilos, retornos de chamada e mapas de mensagem](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)

