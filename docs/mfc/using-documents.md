---
title: Usando documentos | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], C++ applications
- data [MFC], reading
- documents [MFC]
- files [MFC], writing to
- data [MFC], documents
- files [MFC]
- views [MFC], C++ applications
- document/view architecture [MFC], documents
- reading data [MFC], documents and views
- printing [MFC], documents
- writing to files [MFC]
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f039b2e81b52c753a1fb065572d4eac53d55ec9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428701"
---
# <a name="using-documents"></a>Usando documentos

Trabalhando juntos, documentos e exibições:

- Contêm, gerenciar e exibir seu aplicativo-específicas [dados](../mfc/managing-data-with-document-data-variables.md).

- Fornecer uma interface consiste [variáveis de dados de documento](../mfc/managing-data-with-document-data-variables.md) para manipulação dos dados.

- Participar [gravar e ler arquivos](../mfc/serializing-data-to-and-from-files.md).

- Participar [impressão](../mfc/role-of-the-view-in-printing.md).

- [Lidar com](../mfc/handling-commands-in-the-document.md) a maioria dos comandos e mensagens de seu aplicativo.

O documento é particularmente envolvido no gerenciamento de dados. Store seus dados, normalmente, nas variáveis de membro de classe de documento. A exibição usa essas variáveis para acessar os dados para exibição e atualizar. Mecanismo de serialização do documento padrão gerencia ler e gravar os dados para e de arquivos. Documentos também podem lidar com comandos (mas não as mensagens de Windows diferentes WM_COMMAND).

## <a name="what-do-you-want-to-know-more-about"></a>O que você deseja saber mais sobre

- [Derivando uma classe de documento de CDocument](../mfc/deriving-a-document-class-from-cdocument.md)

- [Gerenciando dados com variáveis de dados de documento](../mfc/managing-data-with-document-data-variables.md)

- [Serialização de dados para e de arquivos](../mfc/serializing-data-to-and-from-files.md)

- [Ignorando o mecanismo de serialização](../mfc/bypassing-the-serialization-mechanism.md)

- [Manipulando comandos no documento](../mfc/handling-commands-in-the-document.md)

- [A função de membro OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument)

- [A função de membro DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)

## <a name="see-also"></a>Consulte também

[Arquitetura de documento/exibição](../mfc/document-view-architecture.md)

