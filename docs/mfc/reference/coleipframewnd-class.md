---
title: Classe COleIPFrameWnd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWnd [MFC], COleIPFrameWnd
- COleIPFrameWnd [MFC], OnCreateControlBars
- COleIPFrameWnd [MFC], RepositionFrame
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: debe4c271d2a6e6a82cde9acc75eaa28404ebb43
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443872"
---
# <a name="coleipframewnd-class"></a>Classe COleIPFrameWnd

A base para a janela de edição do seu aplicativo no local.

## <a name="syntax"></a>Sintaxe

```
class COleIPFrameWnd : public CFrameWnd
```

## <a name="members"></a>Membros

### <a name="public-constructors"></a>Construtores Públicos

|Nome|Descrição|
|----------|-----------------|
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|Constrói um objeto `COleIPFrameWnd`.|

### <a name="public-methods"></a>Métodos Públicos

|Nome|Descrição|
|----------|-----------------|
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|Chamado pelo framework quando um item é ativado para edição no local.|
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|Chamado pelo framework para reposicionar a janela de edição in-loco.|

## <a name="remarks"></a>Comentários

Essa classe cria e posições de controlam barras na janela de documento do aplicativo de contêiner. Ele também manipula notificações geradas por um incorporado [COleResizeBar](../../mfc/reference/coleresizebar-class.md) objeto quando o usuário redimensiona a janela de edição in-loco.

Para obter mais informações sobre como usar `COleIPFrameWnd`, consulte o artigo [ativação](../../mfc/activation-cpp.md).

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** afxole.h

##  <a name="coleipframewnd"></a>  COleIPFrameWnd::COleIPFrameWnd

Constrói um `COleIPFrameWnd` do objeto e inicializa suas informações de estado no local, que são armazenadas em uma estrutura do tipo OLEINPLACEFRAMEINFO.

```
COleIPFrameWnd();
```

### <a name="remarks"></a>Comentários

Para obter mais informações, consulte [OLEINPLACEFRAMEINFO](/windows/desktop/api/oleidl/ns-oleidl-tagoifi) no SDK do Windows.

##  <a name="oncreatecontrolbars"></a>  COleIPFrameWnd::OnCreateControlBars

A estrutura chama o `OnCreateControlBars` funcionar quando um item é ativado para edição no local.

```
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,
    CWnd* pWndDoc);


virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,
    CFrameWnd* pWndDoc);
```

### <a name="parameters"></a>Parâmetros

*pWndFrame*<br/>
Ponteiro para a janela do quadro do aplicativo de contêiner.

*pWndDoc*<br/>
Ponteiro para a janela de nível de documento do contêiner. Pode ser NULL se o contêiner for um aplicativo SDI.

### <a name="return-value"></a>Valor de retorno

Diferente de zero em caso de êxito; Caso contrário, 0.

### <a name="remarks"></a>Comentários

A implementação padrão não faz nada. Substitua essa função para executar qualquer processamento especial exigido quando as barras de controle são criadas.

##  <a name="repositionframe"></a>  COleIPFrameWnd::RepositionFrame

A estrutura chama o `RepositionFrame` a função de membro para dispor barras de controle e reposicionar a janela de edição in-loco, portanto, tudo é visível.

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Parâmetros

*lpPosRect*<br/>
Ponteiro para um `RECT` estrutura ou um `CRect` que contém o local do objeto de quadro coordenadas de posição atual da janela, em pixels, relativa a área de cliente.

*lpClipRect*<br/>
Ponteiro para um `RECT` estrutura ou um `CRect` que contém o local do objeto de quadro coordenadas do retângulo de recorte atual da janela, em pixels, relativa a área de cliente.

### <a name="remarks"></a>Comentários

Layout das barras de controle na janela do contêiner é diferente do que é executada por uma janela de quadro não são OLE. A janela do quadro não são OLE calcula as posições das barras de controle e outros objetos de um tamanho de janela com moldura determinado, como em uma chamada para [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). A área de cliente é o que permanece depois que o espaço para barras de controle e outros objetos é subtraído. Um `COleIPFrameWnd` janela, por outro lado, posiciona barras de ferramentas de acordo com uma área de cliente. Em outras palavras, `CFrameWnd::RecalcLayout` funciona "de fora para dentro," enquanto `COleIPFrameWnd::RepositionFrame` funciona "de dentro para fora."

## <a name="see-also"></a>Consulte também

[Exemplo MFC HIERSVR](../../visual-cpp-samples.md)<br/>
[Classe CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Gráfico da hierarquia](../../mfc/hierarchy-chart.md)<br/>
[Classe CFrameWnd](../../mfc/reference/cframewnd-class.md)
