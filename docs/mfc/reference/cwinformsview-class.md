---
title: Classe CWinFormsView | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsView
- AFXWINFORMS/CWinFormsView
- AFXWINFORMS/CWinFormsView::CWinFormsView
- AFXWINFORMS/CWinFormsView::GetControl
dev_langs: C++
helpviewer_keywords:
- CWinFormsView [MFC], CWinFormsView
- CWinFormsView [MFC], GetControl
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0d3551252d04dc97f6e2b4dd13df61edda576744
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="cwinformsview-class"></a>Classe CWinFormsView
Fornece funcionalidade genérica para a hospedagem de um controle de formulários do Windows como uma exibição MFC.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CWinFormsView : public CView;  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CWinFormsView::CWinFormsView](#cwinformsview)|Constrói um objeto `CWinFormsView`.|  
  
### <a name="public-methods"></a>Métodos Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CWinFormsView::GetControl](#getcontrol)|Recupera um ponteiro para o controle de formulários do Windows.|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Nome||  
|----------|-|  
|[Controle de CWinFormsView::operator ^](#operator_control)|Converte um tipo como um ponteiro para um controle de formulários do Windows.|  
  
## <a name="remarks"></a>Comentários  
 MFC usa o `CWinFormsView` classe para hospedar um controle de formulários do Windows do .NET Framework em uma exibição MFC. O controle é um filho do modo nativo e ocupa toda a área cliente do modo de exibição do MFC. O resultado é semelhante a um `CFormView` exibição, permitindo que você aproveite o designer de formulários do Windows e tempo de execução a criar modos de exibição baseado em formulário avançados.  
  
 Para obter mais informações sobre como usar formulários do Windows, consulte [usando um controle de usuário do Windows Form no MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
> [!NOTE]
>  Integração de formulários do Windows MFC funciona apenas em projetos que vincular dinamicamente a MFC (projetos no qual AFXDLL é definido).  
  
> [!NOTE]
>  CWinFormsView não oferece suporte a janela separadora MFC ( [CSplitterWnd classe](../../mfc/reference/csplitterwnd-class.md)). No momento apenas o Windows Forms divisor controle tem suporte.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxwinforms.h  
  
##  <a name="cwinformsview"></a>CWinFormsView::CWinFormsView  
 Constrói um objeto `CWinFormsView`.  
  
```  
CWinFormsView(System::Type^ pManagedViewType);  
```  
  
### <a name="parameters"></a>Parâmetros  
 `pManagedViewType`  
 Um ponteiro para o tipo de dados do controle de usuário de formulários do Windows.   
  
### <a name="example"></a>Exemplo  
 No exemplo a seguir, o `CUserView` classe herda de `CWinFormsView` e passa o tipo de `UserControl1` para o `CWinFormsView` construtor. `UserControl1`é um controle personalizado no ControlLibrary1.dll.  
  
 [!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]  
  
 [!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]  
  
##  <a name="getcontrol"></a>CWinFormsView::GetControl  
 Recupera um ponteiro para o controle de formulários do Windows.  
  
```  
System::Windows::Forms::Control^ GetControl() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um ponteiro para um `System.Windows.Forms.Control` objeto.  
  
### <a name="remarks"></a>Comentários  
 Para obter um exemplo de como usar formulários do Windows, consulte [usando um controle de usuário do Windows Form no MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_control"></a>Controle de CWinFormsView::operator ^  
 Converte um tipo como um ponteiro para um controle de formulários do Windows.  
  
```  
operator System::Windows::Forms::Control^() const;  
```  
  
### <a name="remarks"></a>Comentários  
 Este operador permite que você passe uma `CWinFormsView` exibição para funções que aceitam um ponteiro para um controle de formulários do Windows do tipo <xref:System.Windows.Forms.Control>.  
  
### <a name="example"></a>Exemplo  
  Consulte [CWinFormsView::GetControl](#getcontrol).  
  
## <a name="see-also"></a>Consulte também  
 [Gráfico de hierarquia](../../mfc/hierarchy-chart.md)   
 [Classe CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md)   
 [Classe CWinFormsDialog](../../mfc/reference/cwinformsdialog-class.md)   
 [Classe CFormView](../../mfc/reference/cformview-class.md)