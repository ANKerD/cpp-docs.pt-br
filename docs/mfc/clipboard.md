---
title: Área de transferência | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- cutting and copying data
- copying data
- Clipboard
- Clipboard, programming
- transferring data
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48315b3608a5e66c2f94e1b06a038772dbb25bb4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380484"
---
# <a name="clipboard"></a>Área de Transferência

Essa família de artigos explica como implementar o suporte para a área de transferência do Windows em aplicativos MFC. A área de transferência do Windows é usada de duas maneiras:

- Implementação de comandos do menu Editar padrão, como Recortar, copiar e colar.

- Implementando uniforme de dados para transferir com arrastar e soltar (OLE).

A área de transferência é o método padrão do Windows de transferir dados entre uma origem e um destino. Ela também pode ser muito útil em operações de OLE. Com o advento do OLE, há dois mecanismos de área de transferência no Windows. A API de área de transferência do Windows padrão ainda estará disponível, mas ele tem sido complementado com o mecanismo de transferência de dados OLE. Transferência de uniforme de dados OLE (UDT) dá suporte a recortar, copiar e colar com a área de transferência e arrastar e soltar.

A área de transferência é um serviço de sistema compartilhado por toda sessão do Windows, portanto, ele não tem um identificador ou uma classe própria. Você gerencia a área de transferência por meio de funções de membro da classe [CWnd](../mfc/reference/cwnd-class.md).

## <a name="what-do-you-want-to-know-more-about"></a>O que você deseja saber mais sobre

- [Quando usar cada mecanismo da área de transferência](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)

- [Usando a API tradicional de área de transferência do Windows](../mfc/clipboard-using-the-windows-clipboard.md)

- [Usando o mecanismo de área de transferência OLE](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

- [Copiando e colando dados](../mfc/clipboard-copying-and-pasting-data.md)

- [Adicionando outros formatos](../mfc/clipboard-adding-other-formats.md)

- [A área de transferência do Windows](https://msdn.microsoft.com/library/ms648709)

- [Implementação de arrastar e soltar (OLE)](../mfc/drag-and-drop-ole.md)

## <a name="see-also"></a>Consulte também

[Elementos da Interface do usuário](../mfc/user-interface-elements-mfc.md)
