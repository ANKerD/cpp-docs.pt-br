---
title: Classe CSplitterWndEx | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
dev_langs: C++
helpviewer_keywords: CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e45a136941ccaf34108085a14ddefb64bcdb3fa4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="csplitterwndex-class"></a>Classe CSplitterWndEx



Representa uma janela separadora personalizada.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CSplitterWndEx : public CSplitterWnd  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|`CSplitterWndEx::CSplitterWndEx`|Construtor padrão.|  
|`CSplitterWndEx::~CSplitterWndEx`|Destruidor.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|Chamado pelo framework para desenhar uma janela separadora. (Substitui [CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|  
  
## <a name="remarks"></a>Comentários  
 Substituir o `OnDrawSplitter` método para personalizar a aparência dos componentes de gráfico de uma janela separadora.  
  
 O `CSplitterWndEx` classe é usada junto com o [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder), [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox), e [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) métodos, que são implementado por um Gerenciador de visual. Para fazer com que um Gerenciador de visual desenhar uma janela separadora em seu aplicativo, substitua as declarações da `CSplitterWnd` classe com o `CSplitterWndEx` classe. Para aplicativos de janela do quadro, a classe de janela separadora é declarada na classe CMainFrame que está localizada em mainfrm.h. Para obter um exemplo, consulte o `OutlookDemo` exemplo no diretório de exemplos.  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 [CSplitterWnd](csplitterwnd-class.md)  
   
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxsplitterwndex.h  
  
##  <a name="ondrawsplitter"></a>CSplitterWndEx::OnDrawSplitter  
 Chamado pelo framework para desenhar uma janela separadora.  
  
```  
virtual void OnDrawSplitter(  
   CDC* pDC,  
   ESplitType nType,  
   const CRect& rect   
);  
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pDC`  
 Ponteiro para o contexto de dispositivo. Se esse parâmetro for `NULL`, o framework redesenha a janela ativa.  
  
 [in] `nType`  
 Uma da `CSplitterWnd::ESplitType` valores de enumeração que especifica o elemento de janela separadora para desenhar. Os valores válidos são `splitBox`, `splitBar`, `splitIntersection`, e `splitBorder`.  
  
 [in] `rect`  
 Um retângulo que especifica as dimensões e o local para desenhar o elemento de janela de divisão especificada.  
  
### <a name="remarks"></a>Comentários  
  
## <a name="see-also"></a>Consulte também  
 [Gráfico de hierarquia](../hierarchy-chart.md)   
 [Classes](mfc-classes.md)   
 [Classe CSplitterWnd](csplitterwnd-class.md)   
 [Classe CMFCVisualManager](cmfcvisualmanager-class.md)