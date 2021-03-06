---
title: 'DLLs não MFC: Visão geral | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- non-MFC DLLs [C++]
- DLLs [C++], non-MFC
ms.assetid: 1ed5d1ee-e20c-47d7-801d-87ea26a73842
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30a6fef31dee39cc6337b9b8b7dd3b66ee3adb67
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702579"
---
# <a name="non-mfc-dlls-overview"></a>DLLs que não sejam MFC: visão geral

Uma DLL não MFC é uma DLL que não usa internamente MFC e as funções exportadas na DLL podem ser chamadas por arquivos executáveis do MFC ou não MFC. Funções normalmente são exportadas de uma DLL não MFC usando a interface padrão do C.

Para obter mais informações sobre DLLs não MFC, consulte [bibliotecas de vínculo dinâmico](https://msdn.microsoft.com/library/windows/desktop/ms682589) no SDK do Windows.

## <a name="what-do-you-want-to-do"></a>O que você deseja fazer?

- [Passo a passo: Criando e usando uma biblioteca de vínculo dinâmico](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)

- [Exportação de uma DLL](../build/exporting-from-a-dll.md)

- [Vincular um executável a uma DLL](../build/linking-an-executable-to-a-dll.md)

- [Inicialize um DLL](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Que mais você deseja saber?

- [DLLs MFC regulares vinculadas estaticamente ao MFC](../build/regular-dlls-statically-linked-to-mfc.md)

- [DLLs MFC regulares vinculadas dinamicamente ao MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)

- [DLLs de extensão do MFC: visão geral](../build/extension-dlls-overview.md)

## <a name="see-also"></a>Consulte também

[Tipos de DLLs](../build/kinds-of-dlls.md)