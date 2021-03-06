---
title: Gerenciamento de memória | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory [MFC]
- MFC, memory management
- memory allocation [MFC]
- memory [MFC], managing
- memory allocation [MFC], MFC
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4e83342dde85aae626c9fb83a9493f3e3dd668b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383981"
---
# <a name="memory-management"></a>Gerenciamento de memória

Esse grupo de artigos descreve como tirar proveito dos serviços de uso geral da Microsoft Foundation Class Library (MFC) relacionados ao gerenciamento de memória. Alocação de memória pode ser dividida em duas categorias principais: alocações e alocações de heap de quadro.

Uma diferença principal entre as técnicas de duas alocação é que com a alocação de quadro, que você normalmente trabalha com a memória real bloquear em si, embora com alocação de heap você sempre terá um ponteiro para o bloco de memória. Uma outra grande diferença entre os dois esquemas é que objetos de quadro são automaticamente excluídos, enquanto os objetos de heap devem ser excluídos explicitamente pelo programador.

Para obter informações sobre o gerenciamento de memória em programas para Windows não MFC, consulte [gerenciamento de memória](https://msdn.microsoft.com/library/windows/desktop/aa366779) no SDK do Windows.

## <a name="what-do-you-want-to-know-more-about"></a>O que você deseja saber mais sobre

- [Alocação de quadro](../mfc/memory-management-frame-allocation.md)

- [Alocação de heap](../mfc/memory-management-heap-allocation.md)

- [Ao alocar memória para uma matriz](../mfc/memory-management-examples.md)

- [Desalocando memória para uma matriz do heap](../mfc/memory-management-examples.md)

- [Ao alocar memória para uma estrutura de dados](../mfc/memory-management-examples.md)

- [Ao alocar memória para um objeto](../mfc/memory-management-examples.md)

- [Blocos de memória redimensionáveis](../mfc/memory-management-resizable-memory-blocks.md)

## <a name="see-also"></a>Consulte também

[Conceitos](../mfc/mfc-concepts.md)<br/>
[Tópicos gerais do MFC](../mfc/general-mfc-topics.md)

