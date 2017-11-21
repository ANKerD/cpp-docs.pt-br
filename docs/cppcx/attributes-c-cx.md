---
title: Atributos (C + + CX) | Microsoft Docs
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 4cffb903bcfa22654d4b8ff65609342fab267412
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="attributes-ccx"></a>Atributos (C++/CX)
Um atributo é um tipo especial de classe ref que pode ser acrescentando no início entre colchetes para tipos de tempo de execução do Windows e métodos para especificar determinados comportamentos na criação de metadados. Vários atributos predefinidos — por exemplo, [Windows::Foundation::Metadata::WebHostHidden](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx)— geralmente são usados em C + + código CX. Este exemplo mostra como o atributo é aplicado a uma classe:  
  
 [!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]  
  
## <a name="custom-attributes"></a>Atributos personalizados  
 Você também pode definir atributos personalizados. Atributos personalizados devem estar de acordo com essas regras de tempo de execução do Windows:  
  
-   Atributos personalizados podem conter somente campos públicos.  
  
-   Os campos de atributo personalizado podem ser inicializados quando o atributo é aplicado a uma classe.  
  
-   Um campo pode ser de um destes tipos:  
  
    -   int32 (int)  
  
    -   uint32 (int não assinado)  
  
    -   bool  
  
    -   Platform::String^  
  
    -   Windows::Foundation::HResult  
  
    -   Platform::Type^  
  
    -   classe enum pública (inclui enums definidos pelo usuário)  
  
 O exemplo a seguir mostra como definir um atributo personalizado e inicializá-lo quando você for usá-lo.  
  
 [!code-cpp[cx_attributes#02](../cppcx/codesnippet/CPP/cx_attributes/class1.h#02)]  
  
## <a name="see-also"></a>Consulte também  
 [Sistema de tipos (C++/CX)](../cppcx/type-system-c-cx.md)   
 [Referência de linguagem do Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Referência de namespaces](../cppcx/namespaces-reference-c-cx.md)