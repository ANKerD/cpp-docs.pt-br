---
title: Classe COleException | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
dev_langs: C++
helpviewer_keywords:
- COleException [MFC], Process
- COleException [MFC], m_sc
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1a26ab8bb81487346908a4d1d7596ad33b5c3c31
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="coleexception-class"></a>Classe COleException
Representa uma condição de exceção relacionada a uma operação de OLE.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class COleException : public CException  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-methods"></a>Métodos Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[COleException::Process](#process)|Converte uma exceção capturada em um código de retorno OLE.|  
  
### <a name="public-data-members"></a>Membros de Dados Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[COleException::m_sc](#m_sc)|Contém o código de status que indica o motivo da exceção.|  
  
## <a name="remarks"></a>Comentários  
 O `COleException` classe inclui um membro de dados pública que contém o código de status indicando o motivo da exceção.  
  
 Em geral, você não deve criar um `COleException` objeto diretamente; em vez disso, você deve chamar [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Para obter mais informações sobre exceções, consulte os artigos [de tratamento de exceção (MFC)](../../mfc/exception-handling-in-mfc.md) e [exceções: exceções OLE](../../mfc/exceptions-ole-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxdisp.h  
  
##  <a name="m_sc"></a>COleException::m_sc  
 Este membro de dados contém o código de status OLE que indica o motivo da exceção.  
  
```  
SCODE m_sc;  
```  
  
### <a name="remarks"></a>Comentários  
 O valor da variável é definido [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Para obter mais informações sobre `SCODE`, consulte [estrutura de códigos de erro COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) no SDK do Windows.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]  
  
##  <a name="process"></a>COleException::Process  
 Chamar o **processo** função de membro para converter uma exceção capturada em um código de status OLE.  
  
```  
static SCODE PASCAL Process(const CException* pAnyException);
```  
  
### <a name="parameters"></a>Parâmetros  
 *pAnyException*  
 Ponteiro para uma exceção capturada.  
  
### <a name="return-value"></a>Valor de retorno  
 Um código de status OLE.  
  
### <a name="remarks"></a>Comentários  
  
> [!NOTE]
>  Essa função é **estático**.  
  
 Para obter mais informações sobre `SCODE`, consulte [estrutura de códigos de erro COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) no SDK do Windows.  
  
### <a name="example"></a>Exemplo  
  Consulte o exemplo para [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo MFC CALCDRIV](../../visual-cpp-samples.md)   
 [Classe CException](../../mfc/reference/cexception-class.md)   
 [Gráfico da hierarquia](../../mfc/hierarchy-chart.md)


