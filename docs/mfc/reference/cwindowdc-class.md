---
title: Classe CWindowDC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
dev_langs: C++
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6d31f2dd9ce5855a6d31bf5896643de72cb6135a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="cwindowdc-class"></a>Classe CWindowDC
Derivado de `CDC`.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CWindowDC : public CDC  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CWindowDC::CWindowDC](#cwindowdc)|Constrói um objeto `CWindowDC`.|  
  
### <a name="protected-data-members"></a>Membros de dados protegidos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CWindowDC::m_hWnd](#m_hwnd)|O `HWND` ao qual este `CWindowDC` está anexado.|  
  
## <a name="remarks"></a>Comentários  
 Chama a função do Windows [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx)em tempo de construção e [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx) em tempo de destruição. Isso significa que um `CWindowDC` objeto acessa a área da tela inteira de um [CWnd](../../mfc/reference/cwnd-class.md) (áreas de cliente e não cliente).  
  
 Para obter mais informações sobre como usar `CWindowDC`, consulte [contextos de dispositivo](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: afxwin.h  
  
##  <a name="cwindowdc"></a>CWindowDC::CWindowDC  
 Constrói um `CWindowDC` que acessa a área da tela inteira (cliente e não cliente) do objeto de `CWnd` objeto apontada pelo `pWnd`.  
  
```  
explicit CWindowDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pWnd`  
 A janela cuja área cliente irá acessar o objeto de contexto de dispositivo.  
  
### <a name="remarks"></a>Comentários  
 O construtor chama a função do Windows [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947).  
  
 Uma exceção (do tipo `CResourceException`) é gerada se o Windows `GetWindowDC` chamada falhará. Um contexto de dispositivo pode não estar disponível se o Windows já alocado todos os seus contextos de dispositivo disponível. Seu aplicativo compete para os cinco comuns contextos de exibição disponíveis a qualquer momento no Windows.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>CWindowDC::m_hWnd  
 O `HWND` do `CWnd` ponteiro é usado para construir o `CWindowDC` objeto.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Comentários  
 `m_hWnd`é uma variável protegida do tipo `HWND`.  
  
### <a name="example"></a>Exemplo  
  Consulte o exemplo para [CWindowDC::CWindowDC](#cwindowdc).  
  
## <a name="see-also"></a>Consulte também  
 [Classe CDC](../../mfc/reference/cdc-class.md)   
 [Gráfico de hierarquia](../../mfc/hierarchy-chart.md)   
 [Classe CDC](../../mfc/reference/cdc-class.md)