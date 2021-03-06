---
title: Construção de objetos em um estágio e dois estágios | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6454e34830591eccb2b696948d02f74ad8cebfd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426569"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>Construção de objetos em um e dois estágios

Você pode escolher entre duas técnicas para criar objetos gráficos, como canetas e pincéis:

- *Construção de um estágio*: construção e inicializar o objeto em um estágio, tudo isso com o construtor.

- *Construção de dois estágios*: construção e inicializar o objeto em duas fases separadas. O construtor cria o objeto e inicializa-o uma função de inicialização.

Construção de dois estágios sempre é mais segura. Na construção de um estágio, o construtor pode lançar uma exceção se você fornecer argumentos incorretos ou falha de alocação de memória. Esse problema é evitado com a construção de dois estágios, embora seja necessário que verificar se há falha. Em ambos os casos, destruir o objeto é o mesmo processo.

> [!NOTE]
>  Essas técnicas se aplicam à criação de quaisquer objetos, os objetos gráficos não apenas.

## <a name="example-of-both-construction-techniques"></a>Exemplo de ambas as técnicas de construção

O exemplo a seguir breve mostra ambos os métodos de construção de um objeto pen:

[!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]

### <a name="what-do-you-want-to-know-more-about"></a>O que você deseja saber mais sobre

- [Objetos gráficos](../mfc/graphic-objects.md)

- [Selecionando um objeto gráfico em um contexto de dispositivo](../mfc/selecting-a-graphic-object-into-a-device-context.md)

- [Contextos de dispositivo](../mfc/device-contexts.md)

- [Desenhando em uma exibição](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>Consulte também

[Objetos gráficos](../mfc/graphic-objects.md)

