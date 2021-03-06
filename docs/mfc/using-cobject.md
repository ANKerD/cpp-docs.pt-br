---
title: Usando CObject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- examples [MFC], CObject
- root base class for MFC
- derived classes [MFC], from CObject
- MFC, base class
- CObject class [MFC]
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f421624f16a11f02dc260ce95a9d2cf11fcd9fd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399126"
---
# <a name="using-cobject"></a>Usando CObject

[CObject](../mfc/reference/cobject-class.md) é a classe de base raiz para a maior parte do Microsoft Foundation Class Library (MFC). O `CObject` classe contém muitos recursos úteis que você pode incorporar em seus próprios objetos de programa, incluindo suporte à serialização, informações de classe de tempo de execução e saída de diagnóstico do objeto. Se você derivar a classe de `CObject`, sua classe pode explorar esses `CObject` recursos.

## <a name="what-do-you-want-to-do"></a>O que você deseja fazer

- [Derive uma classe de CObject](../mfc/deriving-a-class-from-cobject.md)

- [Adicionar suporte para informações de classe de tempo de execução, a criação dinâmica e a serialização à minha classe derivada](../mfc/specifying-levels-of-functionality.md)

- [Informações de classe de tempo de execução de acesso](../mfc/accessing-run-time-class-information.md)

- [Criar objetos dinamicamente](../mfc/dynamic-object-creation.md)

- [Os dados do objeto de despejo para fins de diagnóstico](/previous-versions/visualstudio/visual-studio-2010/sc15kz85\(v=vs.100\))

- Validar o estado do objeto interno (consulte [MFC ASSERT_VALID e CObject::assertvalid&lt;1}](reference/diagnostic-services.md#assert_valid))

- [Ter a classe serializar-se para o armazenamento persistente](../mfc/serialization-in-mfc.md)

- Ver uma lista de [perguntas frequentes sobre o CObject](../mfc/cobject-class-frequently-asked-questions.md)

## <a name="see-also"></a>Consulte também

[Conceitos](../mfc/mfc-concepts.md)<br/>
[Tópicos gerais do MFC](../mfc/general-mfc-topics.md)<br/>
[Estrutura CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)<br/>
[Arquivos](../mfc/files-in-mfc.md)<br/>
[Serialização](../mfc/serialization-in-mfc.md)

