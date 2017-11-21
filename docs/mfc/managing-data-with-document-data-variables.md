---
title: "Gerenciando dados com variáveis de dados de documento | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- documents [MFC], data storage
- friend classes [MFC]
- classes [MFC], friend
- data [MFC]
- data [MFC], documents
- collection classes [MFC], used by document object
- document data [MFC]
- member variables [MFC], document class [MFC]
ms.assetid: e70b87f4-8c30-49e5-8986-521c2ff91704
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: af24c461d579ee784487697cc376d9e8f0816643
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="managing-data-with-document-data-variables"></a>Gerenciando dados com variáveis de dados do documento
Implemente os dados do documento como variáveis de membro da classe do documento. Por exemplo, o programa de rabisco declara um membro de dados do tipo `CObList` — uma lista vinculada que armazena ponteiros para `CObject` objetos. Essa lista é usada para armazenar conjuntos de pontos que compõem um desenho de linha traçado.  
  
 Como você implementa os dados de membro do seu documento depende da natureza do seu aplicativo. Para ajudar a saída, MFC fornece um grupo de "classes de coleção" — matrizes, listas e mapas (dicionários), incluindo coleções com base em modelos do C++ — juntamente com classes que encapsulam a uma variedade de tipos de dados comuns, como `CString`, `CRect`, `CPoint`, `CSize`, e `CTime`. Para obter mais informações sobre essas classes, consulte o [visão geral da biblioteca de classe](../mfc/class-library-overview.md) no *referência MFC*.  
  
 Quando você define os dados de membro do documento, você adicionará geralmente funções de membro para a classe de documento para definir e obter itens de dados e executar outras operações útil neles.  
  
 As exibições acessar o objeto de documento usando o ponteiro da exibição no documento, instalado no modo de exibição no momento da criação. Você pode recuperar este ponteiro em funções de membro de um modo de exibição, chamando o `CView` função de membro **GetDocument**. Certifique-se de converter esse ponteiro para seu próprio tipo de documento. Em seguida, você pode acessar membros de documentos públicos através do ponteiro.  
  
 Se a transferência de dados frequentes requer acesso direto, ou você deseja usar os membros não públicos da classe do documento, convém fazer com que a exibição de classe um amigo (em termos de C++) da classe do documento.  
  
## <a name="see-also"></a>Consulte também  
 [Usando documentos](../mfc/using-documents.md)
