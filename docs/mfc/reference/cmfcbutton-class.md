---
title: Classe CMFCButton | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCButton
- AFXBUTTON/CMFCButton
- AFXBUTTON/CMFCButton::CleanUp
- AFXBUTTON/CMFCButton::EnableFullTextTooltip
- AFXBUTTON/CMFCButton::EnableMenuFont
- AFXBUTTON/CMFCButton::EnableWindowsTheming
- AFXBUTTON/CMFCButton::GetToolTipCtrl
- AFXBUTTON/CMFCButton::IsAutoCheck
- AFXBUTTON/CMFCButton::IsAutorepeatCommandMode
- AFXBUTTON/CMFCButton::IsCheckBox
- AFXBUTTON/CMFCButton::IsChecked
- AFXBUTTON/CMFCButton::IsHighlighted
- AFXBUTTON/CMFCButton::IsPressed
- AFXBUTTON/CMFCButton::IsPushed
- AFXBUTTON/CMFCButton::IsRadioButton
- AFXBUTTON/CMFCButton::IsWindowsThemingEnabled
- AFXBUTTON/CMFCButton::SetAutorepeatMode
- AFXBUTTON/CMFCButton::SetCheckedImage
- AFXBUTTON/CMFCButton::SetFaceColor
- AFXBUTTON/CMFCButton::SetImage
- AFXBUTTON/CMFCButton::SetMouseCursor
- AFXBUTTON/CMFCButton::SetMouseCursorHand
- AFXBUTTON/CMFCButton::SetStdImage
- AFXBUTTON/CMFCButton::SetTextColor
- AFXBUTTON/CMFCButton::SetTextHotColor
- AFXBUTTON/CMFCButton::SetTooltip
- AFXBUTTON/CMFCButton::SizeToContent
- AFXBUTTON/CMFCButton::OnDraw
- AFXBUTTON/CMFCButton::OnDrawBorder
- AFXBUTTON/CMFCButton::OnDrawFocusRect
- AFXBUTTON/CMFCButton::OnDrawText
- AFXBUTTON/CMFCButton::OnFillBackground
- AFXBUTTON/CMFCButton::SelectFont
- AFXBUTTON/CMFCButton::m_bDrawFocus
- AFXBUTTON/CMFCButton::m_bHighlightChecked
- AFXBUTTON/CMFCButton::m_bRightImage
- AFXBUTTON/CMFCButton::m_bTransparent
- AFXBUTTON/CMFCButton::m_nAlignStyle
- AFXBUTTON/CMFCButton::m_nFlatStyle
dev_langs: C++
helpviewer_keywords:
- CMFCButton [MFC], CleanUp
- CMFCButton [MFC], EnableFullTextTooltip
- CMFCButton [MFC], EnableMenuFont
- CMFCButton [MFC], EnableWindowsTheming
- CMFCButton [MFC], GetToolTipCtrl
- CMFCButton [MFC], IsAutoCheck
- CMFCButton [MFC], IsAutorepeatCommandMode
- CMFCButton [MFC], IsCheckBox
- CMFCButton [MFC], IsChecked
- CMFCButton [MFC], IsHighlighted
- CMFCButton [MFC], IsPressed
- CMFCButton [MFC], IsPushed
- CMFCButton [MFC], IsRadioButton
- CMFCButton [MFC], IsWindowsThemingEnabled
- CMFCButton [MFC], SetAutorepeatMode
- CMFCButton [MFC], SetCheckedImage
- CMFCButton [MFC], SetFaceColor
- CMFCButton [MFC], SetImage
- CMFCButton [MFC], SetMouseCursor
- CMFCButton [MFC], SetMouseCursorHand
- CMFCButton [MFC], SetStdImage
- CMFCButton [MFC], SetTextColor
- CMFCButton [MFC], SetTextHotColor
- CMFCButton [MFC], SetTooltip
- CMFCButton [MFC], SizeToContent
- CMFCButton [MFC], OnDraw
- CMFCButton [MFC], OnDrawBorder
- CMFCButton [MFC], OnDrawFocusRect
- CMFCButton [MFC], OnDrawText
- CMFCButton [MFC], OnFillBackground
- CMFCButton [MFC], SelectFont
- CMFCButton [MFC], m_bDrawFocus
- CMFCButton [MFC], m_bHighlightChecked
- CMFCButton [MFC], m_bRightImage
- CMFCButton [MFC], m_bTransparent
- CMFCButton [MFC], m_nAlignStyle
- CMFCButton [MFC], m_nFlatStyle
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
caps.latest.revision: "35"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f27516bc2cd878bb0886133e7c27099c03ff5026
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcbutton-class"></a>Classe CMFCButton
O `CMFCButton` classe adiciona a funcionalidade para o [CButton](../../mfc/reference/cbutton-class.md) classe como alinhar o texto do botão, combinando o texto do botão e uma imagem, selecionando um cursor e especificando uma dica de ferramenta.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CMFCButton : public CButton  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|`CMFCButton::CMFCButton`|Construtor padrão.|  
|`CMFCButton::~CMFCButton`|Destruidor.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CMFCButton::CleanUp](#cleanup)|Redefine as variáveis internas e libera os recursos alocados, como imagens, bitmaps e ícones.|  
|`CMFCButton::CreateObject`|Usado pelo framework para criar uma instância dinâmica desse tipo de classe.|  
|`CMFCButton::DrawItem`|Chamado pelo framework quando um aspecto visual de um botão de desenho proprietário é alterado. (Substitui [CButton::DrawItem](../../mfc/reference/cbutton-class.md#drawitem).)|  
|[CMFCButton::EnableFullTextTooltip](#enablefulltexttooltip)|Especifica se deve exibir o texto completo de uma dica de ferramenta em uma janela de dica de ferramenta grande ou uma versão truncada do texto em uma janela de dica de ferramenta pequeno.|  
|[CMFCButton::EnableMenuFont](#enablemenufont)|Especifica se a fonte de texto do botão é o mesmo que a fonte do menu de aplicativo.|  
|[CMFCButton::EnableWindowsTheming](#enablewindowstheming)|Especifica se o estilo da borda do botão corresponde ao tema atual do Windows.|  
|`CMFCButton::GetThisClass`|Usado pelo framework para obter um ponteiro para o [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objeto associado esse tipo de classe.|  
|[CMFCButton::GetToolTipCtrl](#gettooltipctrl)|Retorna uma referência para o controle de dica de ferramenta subjacente.|  
|[CMFCButton::IsAutoCheck](#isautocheck)|Indica se uma caixa de seleção ou botão de opção é um botão automático.|  
|[CMFCButton::IsAutorepeatCommandMode](#isautorepeatcommandmode)|Indica se um botão é definido para o modo de repetição automática.|  
|[CMFCButton::IsCheckBox](#ischeckbox)|Indica se um botão é um botão de caixa de seleção.|  
|[CMFCButton::IsChecked](#ischecked)|Indica se o botão atual é verificado.|  
|[CMFCButton::IsHighlighted](#ishighlighted)|Indica se um botão é realçado.|  
|[CMFCButton::IsPressed](#ispressed)|Indica se um botão é enviada por push e realçado.|  
|[CMFCButton::IsPushed](#ispushed)|Indica se um botão é pressionado.|  
|[CMFCButton::IsRadioButton](#isradiobutton)|Indica se um botão é um botão de opção.|  
|[CMFCButton::IsWindowsThemingEnabled](#iswindowsthemingenabled)|Indica se o estilo da borda do botão corresponde ao tema atual do Windows.|  
|`CMFCButton::OnDrawParentBackground`|Desenha o plano de fundo do pai do botão na área especificada. (Substitui [AFX_GLOBAL_DATA::DrawParentBackground](../../mfc/reference/afx-global-data-structure.md)|  
|`CMFCButton::PreTranslateMessage`|Converte as mensagens de janela antes de serem distribuídos para o [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) e [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) funções do Windows. (Substitui [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCButton::SetAutorepeatMode](#setautorepeatmode)|Define um botão no modo de repetição automática.|  
|[CMFCButton::SetCheckedImage](#setcheckedimage)|Define a imagem de um botão de ativação.|  
|[CMFCButton::SetFaceColor](#setfacecolor)|Define a cor de plano de fundo para o texto do botão.|  
|[CMFCButton::SetImage](#setimage)|Define a imagem de um botão.|  
|[CMFCButton::SetMouseCursor](#setmousecursor)|Define a imagem do cursor.|  
|[CMFCButton::SetMouseCursorHand](#setmousecursorhand)|Define o cursor para a imagem de uma mão.|  
|[CMFCButton::SetStdImage](#setstdimage)|Usa um `CMenuImages` objeto para definir a imagem do botão.|  
|[CMFCButton::SetTextColor](#settextcolor)|Define a cor do texto do botão de um botão que não está selecionado.|  
|[CMFCButton::SetTextHotColor](#settexthotcolor)|Define a cor do texto do botão de um botão que está selecionado.|  
|[CMFCButton::SetTooltip](#settooltip)|Associa uma dica de ferramenta com um botão.|  
|[CMFCButton::SizeToContent](#sizetocontent)|Redimensiona um botão para conter o texto do botão e imagem.|  
  
### <a name="protected-methods"></a>Métodos Protegidos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CMFCButton::OnDraw](#ondraw)|Chamado pelo framework para desenhar um botão.|  
|[CMFCButton::OnDrawBorder](#ondrawborder)|Chamado pelo framework para desenhar a borda de um botão.|  
|[CMFCButton::OnDrawFocusRect](#ondrawfocusrect)|Chamado pelo framework para desenhar o retângulo de foco para um botão.|  
|[CMFCButton::OnDrawText](#ondrawtext)|Chamado pelo framework para desenhar o texto do botão.|  
|[CMFCButton::OnFillBackground](#onfillbackground)|Chamado pelo framework para desenhar o plano de fundo do texto do botão.|  
|[CMFCButton::SelectFont](#selectfont)|Recupera a fonte que está associada com o contexto de dispositivo especificado.|  
  
### <a name="data-members"></a>Membros de Dados  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CMFCButton::m_bDrawFocus](#m_bdrawfocus)|Indica se deve desenhar um retângulo de foco em torno de um botão.|  
|[CMFCButton::m_bHighlightChecked](#m_bhighlightchecked)|Indica se é para realçar um botão de estilo BS_CHECKBOX quando o cursor passa sobre ele.|  
|[CMFCButton::m_bRightImage](#m_brightimage)|Indica se deve exibir uma imagem à direita do botão.|  
|[CMFCButton::m_bTransparent](#m_btransparent)|Indica se o botão é transparente.|  
|[CMFCButton::m_nAlignStyle](#m_nalignstyle)|Especifica o alinhamento do texto do botão.|  
|[CMFCButton::m_nFlatStyle](#m_nflatstyle)|Especifica o estilo do botão como sem borda, simples, ponto-e- simples de ou 3D.|  
  
## <a name="remarks"></a>Comentários  
 Outros tipos de botões derivam o `CMFCButton` classe, como o [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md) classe, que dá suporte a hiperlinks, e o `CMFCColorButton` classe, que oferece suporte a uma caixa de diálogo do seletor de cores.  
  
 O estilo de um `CMFCButton` objeto pode ser *3D*, *simples*, *ponto-e-simples* ou *nenhuma borda*. Texto do botão pode ser alinhado na parte esquerda, superior ou centro de um botão. Em tempo de execução, você pode controlar se o botão exibe o texto, uma imagem ou texto e imagem. Você também pode especificar que uma imagem específica de cursor exibida quando o cursor passa sobre um botão.  
  
 Criar um controle de botão diretamente em seu código ou usando o **Assistente de classe MFC** ferramenta e um modelo de caixa de diálogo. Se você criar um controle de botão diretamente, adicione um `CMFCButton` variável ao seu aplicativo e, em seguida, chame o construtor e `Create` métodos do `CMFCButton` objeto. Se você usar o **Assistente de classe MFC**, adicione um `CButton` variável ao seu aplicativo e, em seguida, altere o tipo da variável de `CButton` para `CMFCButton`.  
  
 Para processar mensagens de notificação em um aplicativo de caixa de diálogo, adicione uma entrada de mapa de mensagem e um manipulador de eventos de cada notificação. As notificações enviadas por uma `CMFCButton` objeto são iguais àquelas enviadas por uma `CButton` objeto.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra como configurar as propriedades de um botão usando vários métodos no `CMFCButton` classe. O exemplo é parte do [exemplo novos controles](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]  
[!code-cpp[NVC_MFC_NewControls#32](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_3.cpp)]  
[!code-cpp[NVC_MFC_NewControls#33](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_4.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxbutton.h  
  
##  <a name="cleanup"></a>CMFCButton::CleanUp  
 Redefine as variáveis internas e libera os recursos alocados, como imagens, bitmaps e ícones.  
  
```  
virtual void CleanUp();
```  
  
##  <a name="enablefulltexttooltip"></a>CMFCButton::EnableFullTextTooltip  
 Especifica se deve exibir o texto completo de uma dica de ferramenta em uma janela de dica de ferramenta grande ou uma versão truncada do texto em uma janela de dica de ferramenta pequeno.  
  
```  
void EnableFullTextTooltip(BOOL bOn=TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bOn`  
 `TRUE`Para exibir todo o texto; `FALSE` para texto de exibição truncado.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="enablemenufont"></a>CMFCButton::EnableMenuFont  
 Especifica se a fonte de texto do botão é o mesmo que a fonte do menu de aplicativo.  
  
```  
void EnableMenuFont(
    BOOL bOn=TRUE,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bOn`  
 `TRUE`Para usar a fonte do menu de aplicativo como a fonte de texto do botão. `FALSE` para usar a fonte do sistema. O padrão é `TRUE`.  
  
 [in] `bRedraw`  
 `TRUE`redesenhar imediatamente a tela; Caso contrário, `FALSE`. O padrão é `TRUE`.  
  
### <a name="remarks"></a>Comentários  
 Se você não usar esse método para especificar a fonte do texto de botão, você pode especificar a fonte com o [CWnd::SetFont](../../mfc/reference/cwnd-class.md#setfont) método. Se você não especificar uma fonte Afinal, a estrutura define uma fonte padrão.  
  
##  <a name="enablewindowstheming"></a>CMFCButton::EnableWindowsTheming  
 Especifica se o estilo da borda do botão corresponde ao tema atual do Windows.  
  
```  
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bEnable`  
 `TRUE`Para usar o tema atual do Windows para desenhar bordas do botão; `FALSE` não usar o tema do Windows. O padrão é `TRUE`.  
  
### <a name="remarks"></a>Comentários  
 Este método afeta todos os botões no seu aplicativo que derivam de `CMFCButton` classe.  
  
##  <a name="gettooltipctrl"></a>CMFCButton::GetToolTipCtrl  
 Retorna uma referência para o controle de dica de ferramenta subjacente.  
  
```  
CToolTipCtrl& GetToolTipCtrl();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Uma referência para o controle de dica de ferramenta subjacente.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="isautocheck"></a>CMFCButton::IsAutoCheck  
 Indica se uma caixa de seleção ou botão de opção é um botão automático.  
  
```  
BOOL IsAutoCheck() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o botão tiver o estilo BS_AUTOCHECKBOX ou BS_AUTORADIOBUTTON; Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="isautorepeatcommandmode"></a>CMFCButton::IsAutorepeatCommandMode  
 Indica se um botão é definido para o modo de repetição automática.  
  
```  
BOOL IsAutorepeatCommandMode() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 TRUE se o botão está definido para o modo de repetição automática; Caso contrário, FALSE.  
  
### <a name="remarks"></a>Comentários  
 Use o [CMFCButton::SetAutorepeatMode](#setautorepeatmode) método para definir um botão para o modo de repetição automática.  
  
##  <a name="ischeckbox"></a>CMFCButton::IsCheckBox  
 Indica se um botão é um botão de caixa de seleção.  
  
```  
BOOL IsCheckBox() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 TRUE se o botão tiver estilo BS_CHECKBOX ou BS_AUTOCHECKBOX; Caso contrário, FALSE.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="ischecked"></a>CMFCButton::IsChecked  
 Indica se o botão atual é verificado.  
  
```  
BOOL IsChecked() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o botão atual está marcado. Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 A estrutura usa maneiras diferentes para indicar que diferentes tipos de botões são verificados. Por exemplo, um botão de opção é verificado quando ele contém um ponto. uma caixa de seleção é marcada quando ela contém um **X**.  
  
##  <a name="ishighlighted"></a>CMFCButton::IsHighlighted  
 Indica se um botão é realçado.  
  
```  
BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 TRUE se o botão é realçado; Caso contrário, FALSE.  
  
### <a name="remarks"></a>Comentários  
 Um botão fica realçado quando o mouse passa sobre o botão.  
  
##  <a name="ispressed"></a>CMFCButton::IsPressed  
 Indica se um botão é enviada por push e realçado.  
  
```  
BOOL IsPressed() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 TRUE se o botão for pressionado; Caso contrário, FALSE.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="ispushed"></a>CMFCButton::IsPushed  
 Indica se um botão é pressionado.  
  
```  
BOOL IsPushed() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 TRUE se o botão está pressionado; Caso contrário, FALSE.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="isradiobutton"></a>CMFCButton::IsRadioButton  
 Indica se um botão é um botão de opção.  
  
```  
BOOL IsRadioButton() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 TRUE se o estilo do botão for BS_RADIOBUTTON ou BS_AUTORADIOBUTTON; Caso contrário, FALSE.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="iswindowsthemingenabled"></a>CMFCButton::IsWindowsThemingEnabled  
 Indica se o estilo da borda do botão corresponde ao tema atual do Windows.  
  
```  
static BOOL IsWindowsThemingEnabled();
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o estilo da borda do botão corresponde ao tema atual do Windows; Caso contrário, `FALSE`.  
  
##  <a name="m_bdrawfocus"></a>CMFCButton::m_bDrawFocus  
 Indica se deve desenhar um retângulo de foco em torno de um botão.  
  
```  
BOOL m_bDrawFocus;  
```  
  
### <a name="remarks"></a>Comentários  
 Definir o `m_bDrawFocus` membro `TRUE` para especificar que a estrutura de desenhar um retângulo de foco ao redor do texto do botão e se o botão recebe o foco da imagem.  
  
 O `CMFCButton` construtor inicializa este membro `TRUE`.  
  
##  <a name="m_bhighlightchecked"></a>CMFCButton::m_bHighlightChecked  
 Indica se é para realçar um botão de estilo BS_CHECKBOX quando o cursor passa sobre ele.  
  
```  
BOOL m_bHighlightChecked;  
```  
  
### <a name="remarks"></a>Comentários  
 Definir o `m_bHighlightChecked` membro `TRUE` para especificar que a estrutura de destacar um botão de estilo BS_CHECKBOX quando o mouse passa sobre ele.  
  
##  <a name="m_brightimage"></a>CMFCButton::m_bRightImage  
 Indica se deve exibir uma imagem à direita do botão.  
  
```  
BOOL m_bRightImage;  
```  
  
### <a name="remarks"></a>Comentários  
 Definir o `m_bRightImage` membro `TRUE` para especificar que a estrutura exibirá a imagem do botão à direita do rótulo de texto do botão.  
  
##  <a name="m_btransparent"></a>CMFCButton::m_bTransparent  
 Indica se o botão é transparente.  
  
```  
BOOL m_bTransparent;  
```  
  
### <a name="remarks"></a>Comentários  
 Definir o `m_bTransparent` membro `TRUE` para especificar que a estrutura fará o botão transparente. O `CMFCButton` construtor inicializa este membro `FALSE`.  
  
##  <a name="m_nalignstyle"></a>CMFCButton::m_nAlignStyle  
 Especifica o alinhamento do texto do botão.  
  
```  
AlignStyle m_nAlignStyle;  
```  
  
### <a name="remarks"></a>Comentários  
 Use um dos seguintes `CMFCButton::AlignStyle` valores de enumeração para especificar o alinhamento do texto do botão:  
  
|Valor|Descrição|  
|-----------|-----------------|  
|ALIGN_CENTER|(Padrão) Alinha o texto do botão para o centro do botão.|  
|ALIGN_LEFT|Alinha o texto do botão à esquerda do botão.|  
|ALIGN_RIGHT|Alinha o texto do botão à direita do botão.|  
  
 O `CMFCButton` construtor inicializa este membro ALIGN_CENTER.  
  
##  <a name="m_nflatstyle"></a>CMFCButton::m_nFlatStyle  
 Especifica o estilo do botão como sem borda, simples, ponto-e- simples de ou 3D.  
  
```  
FlatStyle  m_nFlatStyle;  
```  
  
### <a name="remarks"></a>Comentários  
 A seguinte tabela lista o `CMFCButton::m_nFlatStyle` valores de enumeração que especificam a aparência de um botão.  
  
|Valor|Descrição|  
|-----------|-----------------|  
|BUTTONSTYLE_3D|(Padrão) O botão parece ter lados altos, tridimensionais. Quando o botão é clicado, o botão é exibido seja pressionado em um recuo de profundidade.|  
|BUTTONSTYLE_FLAT|Quando não fará uma pausa o mouse sobre o botão, o botão parece ser bidimensional e não tem lados gerados. Quando o mouse passa sobre o botão, o botão parece ter lados baixos, tridimensionais. Quando o botão é clicado, o botão é exibido seja pressionado em um recuo superficial.|  
|BUTTONSTYLE_SEMIFLAT|O botão parece ter lados baixos, tridimensionais. Quando o botão é clicado, o botão é exibido seja pressionado em um recuo de profundidade.|  
|BUTTONSTYLE_NOBORDERS|O botão não ter gerado lados e sempre aparece bidimensional. O botão não parece ser pressionado em um recuo quando ele for clicado.|  
  
 O `CMFCButton` construtor inicializa este membro `BUTTONSTYLE_3D`.  
  
### <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra como definir os valores de `m_nFlatStyle` variável de membro no `CMFCButton` classe. Este exemplo é parte do [exemplo novos controles](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#29](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]  
  
##  <a name="ondraw"></a>CMFCButton::OnDraw  
 Chamado pelo framework para desenhar um botão.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pDC`  
 Um ponteiro para um contexto de dispositivo.  
  
 [in] `rect`  
 Uma referência a um retângulo que circunda o botão.  
  
 [in] `uiState`  
 O estado atual do botão. Para obter mais informações, consulte o `itemState` membro o [estrutura DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) tópico.  
  
### <a name="remarks"></a>Comentários  
 Substitua este método para usar seu próprio código para desenhar um botão.  
  
##  <a name="ondrawborder"></a>CMFCButton::OnDrawBorder  
 Chamado pelo framework para desenhar a borda de um botão.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pDC`  
 Um ponteiro para um contexto de dispositivo.  
  
 [in] `rectClient`  
 Uma referência a um retângulo que circunda o botão.  
  
 [in] `uiState`  
 O estado atual do botão. Para obter mais informações, consulte o `itemState` membro o [estrutura DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) tópico.  
  
### <a name="remarks"></a>Comentários  
 Substitua este método para usar seu próprio código para desenhar a borda.  
  
##  <a name="ondrawfocusrect"></a>CMFCButton::OnDrawFocusRect  
 Chamado pelo framework para desenhar o retângulo de foco para um botão.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pDC`  
 Um ponteiro para um contexto de dispositivo.  
  
 [in] `rectClient`  
 Uma referência a um retângulo que circunda o botão.  
  
### <a name="remarks"></a>Comentários  
 Substitua este método para usar seu próprio código para desenhar o retângulo de foco.  
  
##  <a name="ondrawtext"></a>CMFCButton::OnDrawText  
 Chamado pelo framework para desenhar o texto do botão.  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    const CRect& rect,  
    const CString& strText,  
    UINT uiDTFlags,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pDC`  
 Um ponteiro para um contexto de dispositivo.  
  
 [in] `rect`  
 Uma referência a um retângulo que circunda o botão.  
  
 [in] `strText`  
 O texto a ser desenhado.  
  
 [in] `uiDTFlags`  
 Sinalizadores que especificam como formatar o texto. Para obter mais informações, consulte o `nFormat` parâmetro o [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) método.  
  
 [in] `uiState`  
 (Reservado).  
  
### <a name="remarks"></a>Comentários  
 Substitua este método para usar seu próprio código para desenhar o texto do botão.  
  
##  <a name="onfillbackground"></a>CMFCButton::OnFillBackground  
 Chamado pelo framework para desenhar o plano de fundo do texto do botão.  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pDC`  
 Um ponteiro para um contexto de dispositivo.  
  
 [in] `rectClient`  
 Uma referência a um retângulo que circunda o botão.  
  
### <a name="remarks"></a>Comentários  
 Substitua este método para usar seu próprio código para desenhar o plano de fundo de um botão.  
  
##  <a name="selectfont"></a>CMFCButton::SelectFont  
 Recupera a fonte que está associada com o contexto de dispositivo especificado.  
  
```  
virtual CFont* SelectFont(CDC* pDC);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pDC`  
 Um ponteiro para um contexto de dispositivo.  
  
### <a name="return-value"></a>Valor de retorno  
 Substitua este método para usar seu próprio código para recuperar a fonte.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="setautorepeatmode"></a>CMFCButton::SetAutorepeatMode  
 Define um botão no modo de repetição automática.  
  
```  
void SetAutorepeatMode(int nTimeDelay=500);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nTimeDelay`  
 Um número não negativo que especifica o intervalo entre as mensagens enviadas para a janela pai. O intervalo é medido em milissegundos e seu valor padrão é 500 milissegundos. Especifique zero para desativar o modo de mensagem de repetição automática.  
  
### <a name="remarks"></a>Comentários  
 Este método faz com que o botão constantemente enviar mensagens WM_COMMAND para a janela pai até que o botão é liberado, ou o `nTimeDelay` parâmetro for definido como zero.  
  
##  <a name="setcheckedimage"></a>CMFCButton::SetCheckedImage  
 Define a imagem de um botão de ativação.  
  
```  
void SetCheckedImage(
    HICON hIcon,  
    BOOL bAutoDestroy=TRUE,  
    HICON hIconHot=NULL,  
    HICON hIconDisabled=NULL,  
    BOOL bAlphaBlend=FALSE);

 
void SetCheckedImage(
    HBITMAP hBitmap,  
    BOOL bAutoDestroy=TRUE,  
    HBITMAP hBitmapHot=NULL,  
    BOOL bMap3dColors=TRUE,  
    HBITMAP hBitmapDisabled=NULL);

 
void SetCheckedImage(
    UINT uiBmpResId,  
    UINT uiBmpHotResId=0,  
    UINT uiBmpDsblResID=0);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `hIcon`  
 Identificador para o ícone que contém o bitmap e a máscara para a nova imagem.  
  
 [in] `bAutoDestroy`  
 `TRUE`para especificar que os recursos de bitmap ser destruído automaticamente. Caso contrário, `FALSE`. O padrão é `TRUE`.  
  
 [in] `hIconHot`  
 Identificador para o ícone que contém a imagem para o estado selecionado.  
  
 [in] `hBitmap`  
 Identificador para o bitmap que contém a imagem para o estado não selecionado.  
  
 [in] `hBitmapHot`  
 Identificador para o bitmap que contém a imagem para o estado selecionado.  
  
 [in] `bMap3dColors`  
 Especifica uma cor transparente para o plano de fundo do botão; ou seja, a face do botão. `TRUE`Para usar o valor de cor RGB (192, 192, 192); `FALSE` para usar o valor de cor definido pelo `AFX_GLOBAL_DATA::clrBtnFace`.  
  
 [in] `uiBmpResId`  
 ID do recurso para a imagem não selecionado.  
  
 [in] `uiBmpHotResId`  
 ID do recurso para a imagem selecionada.  
  
 [in] `hIconDisabled`  
 Identificador para o ícone para a imagem desabilitado.  
  
 [in] `hBitmapDisabled`  
 Identificador para o bitmap que contém a imagem desabilitada.  
  
 [in] `uiBmpDsblResID`  
 ID do recurso do bitmap desabilitado.  
  
 [in] `bAlphaBlend`  
 `TRUE`Para usar somente imagens de 32 bits que usam o canal alfa. `FALSE`, para não usar somente as imagens de canal alfa. O padrão é `FALSE`.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="setfacecolor"></a>CMFCButton::SetFaceColor  
 Define a cor de plano de fundo para o texto do botão.  
  
```  
void SetFaceColor(
    COLORREF crFace,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `crFace`  
 Um valor de cor RGB.  
  
 [in] `bRedraw`  
 `TRUE`redesenhar a tela imediatamente. Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 Use esse método para definir uma nova cor de preenchimento para o plano de fundo do botão (face). Observe que o plano de fundo não será preenchido quando o [CMFCButton::m_bTransparent](#m_btransparent) variável de membro é `TRUE`.  
  
##  <a name="setimage"></a>CMFCButton::SetImage  
 Define a imagem de um botão.  
  
```  
void SetImage(
    HICON hIcon,  
    BOOL bAutoDestroy=TRUE,  
    HICON hIconHot=NULL,  
    HICON hIconDisabled=NULL,  
    BOOL bAlphaBlend=FALSE);

 
void SetImage(
    HBITMAP hBitmap,  
    BOOL bAutoDestroy=TRUE,  
    HBITMAP hBitmapHot=NULL,  
    BOOL bMap3dColors=TRUE,  
    HBITMAP hBitmapDisabled=NULL);

 
void SetImage(
    UINT uiBmpResId,  
    UINT uiBmpHotResId=0,  
    UINT uiBmpDsblResID=0);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `hIcon`  
 Identificador para o ícone que contém o bitmap e a máscara para a nova imagem.  
  
 [in] `bAutoDestroy`  
 `TRUE`para especificar que os recursos de bitmap ser destruído automaticamente. Caso contrário, `FALSE`. O padrão é `TRUE`.  
  
 [in] `hIconHot`  
 Identificador para o ícone que contém a imagem para o estado selecionado.  
  
 [in] `hBitmap`  
 Identificador para o bitmap que contém a imagem para o estado não selecionado.  
  
 [in] `hBitmapHot`  
 Identificador para o bitmap que contém a imagem para o estado selecionado.  
  
 [in] `uiBmpResId`  
 ID do recurso para a imagem não selecionado.  
  
 [in] `uiBmpHotResId`  
 ID do recurso para a imagem selecionada.  
  
 [in] `bMap3dColors`  
 Especifica uma cor transparente para o plano de fundo do botão; ou seja, a face do botão. `TRUE`Para usar o valor de cor RGB (192, 192, 192); `FALSE` para usar o valor de cor definido pelo `AFX_GLOBAL_DATA::clrBtnFace`.  
  
 [in] `hIconDisabled`  
 Identificador para o ícone para a imagem desabilitado.  
  
 [in] `hBitmapDisabled`  
 Identificador para o bitmap que contém a imagem desabilitada.  
  
 [in] `uiBmpDsblResID`  
 ID do recurso do bitmap desabilitado.  
  
 [in] `bAlphaBlend`  
 `TRUE`Para usar somente imagens de 32 bits que usam o canal alfa. `FALSE`, para não usar somente as imagens de canal alfa. O padrão é `FALSE`.  
  
### <a name="remarks"></a>Comentários  
  
### <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra como usar várias versões do `SetImage` método o `CMFCButton` classe. O exemplo é parte do [exemplo novos controles](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]  
  
##  <a name="setmousecursor"></a>CMFCButton::SetMouseCursor  
 Define a imagem do cursor.  
  
```  
void SetMouseCursor(HCURSOR hcursor);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `hcursor`  
 O identificador de um cursor.  
  
### <a name="remarks"></a>Comentários  
 Use esse método para associar uma imagem de cursor, como o cursor de mão, com o botão. O cursor é carregado a partir dos recursos do aplicativo.  
  
### <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra como usar o `SetMouseCursor` método o `CMFCButton` classe. O exemplo é parte do código de [exemplo novos controles](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#30](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]  
  
##  <a name="setmousecursorhand"></a>CMFCButton::SetMouseCursorHand  
 Define o cursor para a imagem de uma mão.  
  
```  
void SetMouseCursorHand();
```  
  
### <a name="remarks"></a>Comentários  
 Use esse método para associar a imagem de cursor de uma mão com o botão. O cursor é carregado a partir dos recursos do aplicativo.  
  
##  <a name="setstdimage"></a>CMFCButton::SetStdImage  
 Usa um `CMenuImages` objeto para definir a imagem do botão.  
  
```  
void SetStdImage(
    CMenuImages::IMAGES_IDS id,  
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,  
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `id`  
 Um dos identificadores de imagem do botão que é definido no `CMenuImage::IMAGES_IDS` enumeração. Os valores de imagem especificam imagens como setas, pins e botões de opção.  
  
 [in] `state`  
 Um dos identificadores de estado de imagem de botão que é definido no `CMenuImages::IMAGE_STATE` enumeração. Os estados de imagem especificar cores do botão como cinza de preto, cinza claro cinza, branco e escuro. O valor padrão é `CMenuImages::ImageBlack`.  
  
 [in] `idDisabled`  
 Um dos identificadores de imagem do botão que é definido no `CMenuImage::IMAGES_IDS` enumeração. A imagem indica que o botão está desabilitado. O valor padrão é a primeira imagem do botão ( `CMenuImages::IdArrowDown`).  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="settextcolor"></a>CMFCButton::SetTextColor  
 Define a cor do texto do botão de um botão que não está selecionado.  
  
```  
void SetTextColor(COLORREF clrText);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `clrText`  
 Um valor de cor RGB.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="settexthotcolor"></a>CMFCButton::SetTextHotColor  
 Define a cor do texto do botão de um botão que está selecionado.  
  
```  
void SetTextHotColor(COLORREF clrTextHot);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `clrTextHot`  
 Um valor de cor RGB.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="settooltip"></a>CMFCButton::SetTooltip  
 Associa uma dica de ferramenta com um botão.  
  
```  
void SetTooltip(LPCTSTR lpszToolTipText);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `lpszToolTipText`  
 Ponteiro para o texto de dica de ferramenta. Especifique NULL para desativar a dica de ferramenta.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="sizetocontent"></a>CMFCButton::SizeToContent  
 Redimensiona um botão para conter o texto do botão e imagem.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bCalcOnly`  
 `TRUE`para calcular, mas não alterar, o novo tamanho do botão. `FALSE` para alterar o tamanho do botão. O padrão é `FALSE`.  
  
### <a name="return-value"></a>Valor de retorno  
 Um `CSize` objeto que contém o novo tamanho do botão.  
  
### <a name="remarks"></a>Comentários  
 Por padrão, esse método calcula um novo tamanho que inclui uma margem horizontal de 10 pixels e uma margem vertical de 5 pixels.  
  
## <a name="see-also"></a>Consulte também  
 [Gráfico de hierarquia](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Classe CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)   
 [Classe CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)   
 [Classe CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)