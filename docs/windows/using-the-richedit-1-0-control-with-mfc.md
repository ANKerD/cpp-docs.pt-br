---
title: Usando o controle RichEdit 1.0 com MFC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- RichEdit 1.0 control
- rich edit controls, RichEdit 1.0
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3d6c5393b006602084a50d18c8cfe76d59d2d6ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="using-the-richedit-10-control-with-mfc"></a>Usando o controle RichEdit 1.0 com MFC
Para usar um controle RichEdit, você deve primeiro chamar [AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) para carregar o controle RichEdit 2.0 (RICHED20. DLL), ou chame [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) para carregar o controle de 1.0 RichEdit mais antigos (RICHED32. DLL).  
  
 Você pode usar atual [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) classe com o controle RichEdit 1.0 mais antigo, mas **CRichEditCtrl** só foi projetado para oferecer suporte o controle RichEdit 2.0. A maioria dos métodos funcionará como RichEdit 1.0 e 2.0 RichEdit são muito semelhantes, No entanto, observe que há algumas diferenças entre os controles 1.0 e 2.0, para que alguns métodos podem funcionar incorretamente ou não funcionar.  
  
## <a name="requirements"></a>Requisitos  
 MFC  
  
## <a name="see-also"></a>Consulte também  
 [O Editor de caixa de diálogo de solução de problemas](../windows/troubleshooting-the-dialog-editor.md)   
 [Editor de caixa de diálogo](../windows/dialog-editor.md)
