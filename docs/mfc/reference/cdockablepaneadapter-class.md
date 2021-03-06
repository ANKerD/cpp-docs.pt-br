---
title: Classe CDockablePaneAdapter | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::GetWrappedWnd
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::LoadState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SaveState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SetWrappedWnd
dev_langs:
- C++
helpviewer_keywords:
- CDockablePaneAdapter [MFC], GetWrappedWnd
- CDockablePaneAdapter [MFC], LoadState
- CDockablePaneAdapter [MFC], SaveState
- CDockablePaneAdapter [MFC], SetWrappedWnd
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cec0a5c40d7937e8df20b5437b6dcc83b1b9ec1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441168"
---
# <a name="cdockablepaneadapter-class"></a>Classe CDockablePaneAdapter

Fornece suporte de encaixe para `CWnd`-painéis derivados.

## <a name="syntax"></a>Sintaxe

```
class CDockablePaneAdapter : public CDockablePane
```

## <a name="members"></a>Membros

### <a name="public-methods"></a>Métodos Públicos

|Nome|Descrição|
|----------|-----------------|
|[CDockablePaneAdapter::GetWrappedWnd](#getwrappedwnd)|Retorna a janela encapsulada.|
|[CDockablePaneAdapter::LoadState](#loadstate)|(Substitui [CDockablePane::LoadState](cdockablepane-class.md#loadstate).)|
|[CDockablePaneAdapter::SaveState](#savestate)|(Substitui [CDockablePane::SaveState](cdockablepane-class.md).)|
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||

## <a name="remarks"></a>Comentários

Normalmente, o framework cria uma instância de objetos dessa classe quando você usa o [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) ou [CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) métodos.

Se você desejar personalizar o `CDockablePaneAdapter` comportamento, basta derivar uma nova classe dele e definir as informações de classe de tempo de execução para uma janela com guias usando [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc).

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

[CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)

## <a name="requirements"></a>Requisitos

**Cabeçalho:** afxDockablePaneAdapter.h

##  <a name="getwrappedwnd"></a>  CDockablePaneAdapter::GetWrappedWnd

Retorna a janela subjacente para o adaptador de painel encaixável.

```
virtual CWnd* GetWrappedWnd() const;
```

### <a name="return-value"></a>Valor de retorno

Um ponteiro para a janela encapsulado.

### <a name="remarks"></a>Comentários

Use esta função para acessar a janela encapsulada.

##  <a name="loadstate"></a>  CDockablePaneAdapter::LoadState

Carrega o estado do painel do registro.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parâmetros

*lpszProfileName*<br/>
[in] O nome do perfil.

*nIndex*<br/>
[in] O índice de perfil.

*uiID*<br/>
[in] A ID do painel.

### <a name="return-value"></a>Valor de retorno

### <a name="remarks"></a>Comentários

##  <a name="savestate"></a>  CDockablePaneAdapter::SaveState

Salva o estado do painel no registro.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parâmetros

*lpszProfileName*<br/>
[in] O nome do perfil.

*nIndex*<br/>
[in] O índice do perfil (o padrão é a ID do controle da janela).

*uiID*<br/>
[in] A ID do painel.

### <a name="return-value"></a>Valor de retorno

### <a name="remarks"></a>Comentários

##  <a name="setwrappedwnd"></a>  CDockablePaneAdapter::SetWrappedWnd

Define a janela subjacente para o adaptador de painel encaixável.

```
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>Parâmetros

*Apropriei*<br/>
[in] Um ponteiro para a janela para o adaptador de painel encapsular.

### <a name="return-value"></a>Valor de retorno

### <a name="remarks"></a>Comentários

## <a name="see-also"></a>Consulte também

[Gráfico da hierarquia](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[Classe CDockablePane](../../mfc/reference/cdockablepane-class.md)
