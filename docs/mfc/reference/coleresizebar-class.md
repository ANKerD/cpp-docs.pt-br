---
title: Classe COleResizeBar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
dev_langs:
- C++
helpviewer_keywords:
- COleResizeBar [MFC], COleResizeBar
- COleResizeBar [MFC], Create
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf1e2b447b4cfe0e2f503d2263354f3537bbb849
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391378"
---
# <a name="coleresizebar-class"></a>Classe COleResizeBar

Um tipo de barra de controle que dá suporte ao redimensionamento de itens OLE no local.

## <a name="syntax"></a>Sintaxe

```
class COleResizeBar : public CControlBar
```

## <a name="members"></a>Membros

### <a name="public-constructors"></a>Construtores Públicos

|Nome|Descrição|
|----------|-----------------|
|[COleResizeBar::COleResizeBar](#coleresizebar)|Constrói um objeto `COleResizeBar`.|

### <a name="public-methods"></a>Métodos Públicos

|Nome|Descrição|
|----------|-----------------|
|[COleResizeBar::Create](#create)|Cria e inicializa uma janela filho do Windows e associa-o para o `COleResizeBar` objeto.|

## <a name="remarks"></a>Comentários

`COleResizeBar` os objetos aparecem como uma [CRectTracker](../../mfc/reference/crecttracker-class.md) com uma borda hachurada e externo alças de redimensionamento.

`COleResizeBar` objetos são geralmente embedded membros dos objetos de janela com moldura derivados de [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) classe.

Para obter mais informações, consulte o artigo [ativação](../../mfc/activation-cpp.md).

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`COleResizeBar`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** afxole.h

##  <a name="coleresizebar"></a>  COleResizeBar::COleResizeBar

Constrói um objeto `COleResizeBar`.

```
COleResizeBar();
```

### <a name="remarks"></a>Comentários

Chamar `Create` para criar o objeto de barra de redimensionamento.

##  <a name="create"></a>  COleResizeBar::Create

Cria uma janela filho e o associa com o `COleResizeBar` objeto.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_RESIZE_BAR);
```

### <a name="parameters"></a>Parâmetros

*pParentWnd*<br/>
Ponteiro para a janela pai da barra de redimensionamento.

*dwStyle*<br/>
Especifica o [estilo de janela](../../mfc/reference/styles-used-by-mfc.md#window-styles) atributos.

*nID*<br/>
Janela filho da barra de redimensionamento da ID.

### <a name="return-value"></a>Valor de retorno

Diferente de zero se a barra de redimensionamento foi criada; Caso contrário, 0.

## <a name="see-also"></a>Consulte também

[Exemplo MFC SUPERPAD](../../visual-cpp-samples.md)<br/>
[Classe CControlBar](../../mfc/reference/ccontrolbar-class.md)<br/>
[Gráfico da hierarquia](../../mfc/hierarchy-chart.md)<br/>
[Classe COleServerDoc](../../mfc/reference/coleserverdoc-class.md)
