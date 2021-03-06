---
title: Arquivos de origem usando o MFC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- public members
- source files
- MFC, source files
- MFC source files
- comments, MFC
- private member access
- protected member access
- source files, MFC
ms.assetid: 3230e8fb-3b69-4ddf-9538-365ac7ea5e72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e63383e372227dc14ce90843b03b6cb0c029b52a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383849"
---
# <a name="using-the-mfc-source-files"></a>Usando os arquivos de origem MFC

A biblioteca Microsoft Foundation Class (MFC) fornece o código-fonte completo. Arquivos de cabeçalho (. h) estão no diretório \atlmfc\include; arquivos de implementação (. cpp) estão no diretório \atlmfc\src\mfc.

Essa família de artigos explica as convenções que usa o MFC para as várias partes de cada classe, o que significam esses comentários e o que você deve esperar encontrar em cada seção de comentário. Os assistentes do Visual C++ usam convenções semelhantes para as classes que foram criadas para você, e você provavelmente encontrará essas convenções úteis para seu próprio código.

Você pode estar familiarizado com o **pública**, **protegido**, e **privada** palavras-chave C++. Ao examinar os arquivos de cabeçalho MFC, você encontrará a cada classe pode ter vários de cada um deles. Por exemplo, funções e variáveis de membro público podem ser em mais de uma **pública** palavra-chave. Isso ocorre porque o MFC separa as variáveis de membro e funções com base em seu uso, não pelo tipo de acesso permitido. O MFC usa **privada** com moderação; até mesmo os itens consideraram detalhes de implementação geralmente são protegidos e muitas vezes são públicos. Embora o acesso aos detalhes de implementação não é recomendado, o MFC deixa a decisão para você.

Os arquivos de origem MFC e os arquivos criado pelo Assistente de aplicativo do MFC, você encontrará comentários como esses em declarações de classe (normalmente na ordem):

`// Constructors`

`// Attributes`

`// Operations`

`// Overridables`

`// Implementation`

Os tópicos abordados nesta família dos artigos incluem:

- [Um exemplo dos comentários](../mfc/an-example-of-the-comments.md)

- [O / / comentário de implementação](../mfc/decrement-implementation-comment.md)

- [O / / comentário sobre construtores](../mfc/decrement-constructors-comment.md)

- [O / / a atributos de comentário](../mfc/decrement-attributes-comment.md)

- [O / / comentário sobre operações](../mfc/decrement-operations-comment.md)

- [O / / comentário sobre substituíveis](../mfc/decrement-overridables-comment.md)

## <a name="see-also"></a>Consulte também

[Tópicos gerais do MFC](../mfc/general-mfc-topics.md)

