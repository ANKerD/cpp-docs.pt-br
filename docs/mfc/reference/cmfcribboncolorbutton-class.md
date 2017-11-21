---
title: Classe CMFCRibbonColorButton | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
dev_langs: C++
helpviewer_keywords:
- CMFCRibbonColorButton [MFC], CMFCRibbonColorButton
- CMFCRibbonColorButton [MFC], AddColorsGroup
- CMFCRibbonColorButton [MFC], EnableAutomaticButton
- CMFCRibbonColorButton [MFC], EnableOtherButton
- CMFCRibbonColorButton [MFC], GetAutomaticColor
- CMFCRibbonColorButton [MFC], GetColor
- CMFCRibbonColorButton [MFC], GetColorBoxSize
- CMFCRibbonColorButton [MFC], GetColumns
- CMFCRibbonColorButton [MFC], GetHighlightedColor
- CMFCRibbonColorButton [MFC], RemoveAllColorGroups
- CMFCRibbonColorButton [MFC], SetColor
- CMFCRibbonColorButton [MFC], SetColorBoxSize
- CMFCRibbonColorButton [MFC], SetColorName
- CMFCRibbonColorButton [MFC], SetColumns
- CMFCRibbonColorButton [MFC], SetDocumentColors
- CMFCRibbonColorButton [MFC], SetPalette
- CMFCRibbonColorButton [MFC], UpdateColor
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
caps.latest.revision: "36"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6f199eb4adc257077ad91b0710cb62752f597b8e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcribboncolorbutton-class"></a>Classe CMFCRibbonColorButton
O `CMFCRibbonColorButton` classe implementa um botão de cor que você pode adicionar a uma barra de faixa de opções. Botão de cor da faixa de opções exibe um menu suspenso que contém um ou mais paletas de cores.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CMFCRibbonColorButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CMFCRibbonColorButton::AddColorsGroup](#addcolorsgroup)|Adiciona um grupo de cores para a área de cores regular.|  
|[CMFCRibbonColorButton::EnableAutomaticButton](#enableautomaticbutton)|Especifica se o **automáticas** botão é habilitado.|  
|[CMFCRibbonColorButton::EnableOtherButton](#enableotherbutton)|Permite que o **outros** botão.|  
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||  
|[CMFCRibbonColorButton::GetColor](#getcolor)|Retorna a cor atualmente selecionada.|  
|[CMFCRibbonColorButton::GetColorBoxSize](#getcolorboxsize)|Retorna o tamanho dos elementos da cor que aparecem na barra de cores.|  
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||  
|[CMFCRibbonColorButton::GetHighlightedColor](#gethighlightedcolor)|Retorna a cor do elemento atualmente selecionado na paleta de cores pop-up.|  
|[CMFCRibbonColorButton::RemoveAllColorGroups](#removeallcolorgroups)|Remove todos os grupos de cores da área de cores normal.|  
|[CMFCRibbonColorButton::SetColor](#setcolor)|Seleciona uma cor da área de cores normal.|  
|[CMFCRibbonColorButton::SetColorBoxSize](#setcolorboxsize)|Define o tamanho de todos os elementos de cor que aparecem na barra de cores.|  
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||  
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||  
|[CMFCRibbonColorButton::SetDocumentColors](#setdocumentcolors)|Especifica uma lista de valores RGB para exibir na área de cor do documento.|  
|[CMFCRibbonColorButton::SetPalette](#setpalette)||  
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||  
  
## <a name="remarks"></a>Comentários  
 Botão de cor da faixa de opções exibe uma barra de cores quando o usuário pressionar a ele. Por padrão, a barra de cores contém uma paleta de seleção de cor chamada a área de cores regular. Opcionalmente, a barra de cores pode exibir um **automático** botão, que permite ao usuário selecionar uma cor padrão, e um **outros** botão, que exibe uma paleta de cores de pop-up que contém cores adicionais.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra como usar vários métodos no `CMFCRibbonColorButton` classe. O exemplo mostra como construir um `CMFCRibbonColorButton` de objeto, definir a imagem grande, habilitar o **automático** botão, habilite o **outros** botão, defina o número de colunas, defina o tamanho de todos os elementos de cor que aparecem na barra de cores, adicionar um grupo de cores para a área de cores regular e especificar uma lista de valores RGB a ser exibida na área de cor do documento. Este trecho de código é parte do [desenhar cliente de exemplo](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxribboncolorbutton.h  
  
##  <a name="addcolorsgroup"></a>CMFCRibbonColorButton::AddColorsGroup  
 Adiciona um grupo de cores para a área de cores regular.  
  
```  
void AddColorsGroup(
    LPCTSTR lpszName,  
    const CList<COLORREF,COLORREF>& lstColors,  
    BOOL bContiguousColumns=FALSE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `lpszName`  
 O nome do grupo.  
  
 [in] `lstColors`  
 A lista de cores.  
  
 [in] `bContiguousColumns`  
 Controla como os itens de cor são exibidos no grupo. Se `TRUE`, os itens de cor são desenhados sem um espaçamento vertical. Se `FALSE`, os itens de cor são desenhados com um espaçamento vertical.  
  
### <a name="remarks"></a>Comentários  
 Use esta função para tornar a cor de pop-up Exibir vários grupos de cores. Você pode controlar como as cores são exibidas no grupo.  
  
##  <a name="cmfcribboncolorbutton"></a>CMFCRibbonColorButton::CMFCRibbonColorButton  
 Constrói um objeto `CMFCRibbonColorButton`.  
  
```  
CMFCRibbonColorButton();

 
CMFCRibbonColorButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    COLORREF color = RGB(0, 0, 0));

 
CMFCRibbonColorButton(
    UINT nID,  
    LPCTSTR lpszText,  
    BOOL bSimpleButtonLook,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    COLORREF color = RGB(0, 0, 0));
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nID`  
 Especifica a ID de comando para executar quando um usuário clica no botão de comando.  
  
 [in] `lpszText`  
 Especifica o texto a ser exibido no botão.  
  
 [in] `nSmallImageIndex`  
 O índice baseado em zero da imagem pequena seja exibido no botão.  
  
 [in] `color`  
 A cor do botão (o padrão é preto).  
  
 [in] `bSimpleButtonLook`  
 Se `TRUE`, o botão é desenhado como um retângulo simple.  
  
 [in] `nLargeImageIndex`  
 O índice baseado em zero da imagem grande para ser exibido no botão.  
  
### <a name="return-value"></a>Valor de retorno  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="enableautomaticbutton"></a>CMFCRibbonColorButton::EnableAutomaticButton  
 Especifica se o **automáticas** botão é habilitado.  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE,  
    LPCTSTR lpszToolTip=NULL,  
    BOOL bOnTop=TRUE,  
    BOOL bDrawBorder=FALSE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `lpszLabel`  
 O rótulo para o **automáticas** botão.  
  
 [in] `colorAutomatic`  
 Um valor RGB que especifica o **automáticas** cor do padrão do botão.  
  
 [in] `bEnable`  
 `TRUE`Se o **automáticas** botão estiver habilitado; `FALSE` se ele estiver desabilitado.  
  
 [in] `lpszToolTip`  
 A dica de ferramenta do **automáticas** botão.  
  
 [in] `bOnTop`  
 Especifica se o **automáticas** botão fica na parte superior, antes da paleta de cores.  
  
 [in] `bDrawBorder`  
 `TRUE`Se o aplicativo desenha uma borda em torno da barra de cores do botão de cor da faixa de opções. Na barra de cores exibe a cor atualmente selecionada. `FALSE`Se o aplicativo não desenhar uma borda  
  
##  <a name="enableotherbutton"></a>CMFCRibbonColorButton::EnableOtherButton  
 Permite que o **outros** botão.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    LPCTSTR lpszToolTip=NULL);
```  
  
### <a name="parameters"></a>Parâmetros  
 `lpszLabel`  
 O rótulo do botão.  
  
 `lpszToolTip`  
 O texto de dica de ferramenta para o **outros** botão.  
  
### <a name="remarks"></a>Comentários  
 O **outros** botão é o que é exibido abaixo do grupo de cores. Quando o usuário clica o **outros** botão, ele exibe uma caixa de diálogo de cor.  
  
##  <a name="getautomaticcolor"></a>CMFCRibbonColorButton::GetAutomaticColor  
 Recupera a cor do botão automático atual.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um valor de cor RGB que representa a cor do botão automático atual.  
  
### <a name="remarks"></a>Comentários  
 A cor do botão automático é definida pelo `colorAutomatic` parâmetro passado para o `CMFCRibbonColorButton::EnableAutomaticButton` método.  
  
##  <a name="getcolor"></a>CMFCRibbonColorButton::GetColor  
 Retorna a cor atualmente selecionada.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 A cor selecionada, clique no botão.  
  
##  <a name="getcolorboxsize"></a>CMFCRibbonColorButton::GetColorBoxSize  
 Retorna o tamanho dos elementos da cor que aparecem na barra de cores.  
  
```  
CSize GetColorBoxSize() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 O tamanho dos botões de cor na paleta de cores da lista suspensa.  
  
##  <a name="getcolumns"></a>CMFCRibbonColorButton::GetColumns  
 Obtém o número de itens em uma linha da exibição de galeria da faixa de opções cor do botão.  
  
```  
int GetColumns() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o número de ícones em cada linha.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="gethighlightedcolor"></a>CMFCRibbonColorButton::GetHighlightedColor  
 Retorna a cor do elemento atualmente selecionado na paleta de cores pop-up.  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 A cor do elemento atualmente selecionado na paleta de cores pop-up.  
  
##  <a name="removeallcolorgroups"></a>CMFCRibbonColorButton::RemoveAllColorGroups  
 Remove todos os grupos de cores da área de cores normal.  
  
```  
void RemoveAllColorGroups();
```  
  
##  <a name="setcolor"></a>CMFCRibbonColorButton::SetColor  
 Seleciona uma cor da área de cores normal.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `color`  
 Uma cor a ser definido.  
  
##  <a name="setcolorboxsize"></a>CMFCRibbonColorButton::SetColorBoxSize  
 Define o tamanho de todos os elementos de cor que aparecem na barra de cores.  
  
```  
void SetColorBoxSize(CSize sizeBox);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `sizeBox`  
 O novo tamanho dos botões de cor na paleta de cores.  
  
##  <a name="setcolorname"></a>CMFCRibbonColorButton::SetColorName  
 Define um novo nome para uma cor especificada.  
  
```  
static void __stdcall SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `color`  
 O valor RGB da cor.  
  
 [in] `strName`  
 O novo nome para a cor especificada.  
  
### <a name="remarks"></a>Comentários  
 Porque chama `CMFCColorBar::SetColorName`, esse método altera o nome da cor especificada em todos os `CMFCColorBar` objetos em seu aplicativo.  
  
##  <a name="setcolumns"></a>CMFCRibbonColorButton::SetColumns  
 Define o número de colunas exibidas na tabela de cores é apresentada ao usuário durante o processo de seleção de cor do usuário.  
  
```  
void SetColumns(int nColumns);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nColumns`  
 O número de ícones de cor para exibir em cada linha.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="setdocumentcolors"></a>CMFCRibbonColorButton::SetDocumentColors  
 Especifica uma lista de valores RGB para exibir na área de cor do documento.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `lpszLabel`  
 O texto a ser exibido com as cores do documento.  
  
 [in] `lstColors`  
 Uma referência a uma lista de valores RGB.  
  
##  <a name="setpalette"></a>CMFCRibbonColorButton::SetPalette  
 Especifica as cores padrão para exibir na tabela de cores que exibe o botão de cor.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pPalette`  
 Um ponteiro para uma paleta de cores.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="updatecolor"></a>CMFCRibbonColorButton::UpdateColor  
 Chamado pelo framework quando o usuário seleciona uma cor na tabela de cores exibida quando o usuário clica no botão de cor.  
  
```  
void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `color`  
 Cor selecionada pelo usuário.  
  
### <a name="remarks"></a>Comentários  
 O `CMFCRibbonColorButton::UpdateColor` método altera a cor do botão selecionado no momento e notificará seu pai, enviando um `WM_COMMAND` mensagem com um `BN_CLICKED` notificação padrão. Use o [CMFCRibbonColorButton::GetColor](#getcolor) método para recuperar a cor selecionada.  
  
## <a name="see-also"></a>Consulte também  
 [Gráfico de hierarquia](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Classe CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)