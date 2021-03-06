---
title: Noções básicas sobre geração de manifesto para programas do C/C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91120d1c8485d43a447310440bbe0bab8f7e3b75
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726252"
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>Noções básicas sobre geração de manifesto para programas do C/C++

Um [manifesto](https://msdn.microsoft.com/library/aa375365) é um documento XML que pode ser um arquivo XML externo ou um recurso incorporado dentro de um aplicativo ou um assembly. O manifesto de um [aplicativo isolado](/windows/desktop/SbsCs/isolated-applications) é usado para gerenciar os nomes e versões de assemblies lado a lado a lado compartilhados aos quais o aplicativo deve associar em tempo de execução. O manifesto de um assembly lado a lado especifica suas dependências em nomes, versões, recursos e outros assemblies.

Há duas maneiras de criar um manifesto para um aplicativo isolado ou um assembly lado a lado. Primeiro, o autor do assembly pode criar manualmente um arquivo de manifesto seguindo regras e requisitos de nomenclatura. Como alternativa, se apenas um programa depende de assemblies do Visual C++, como o CRT, MFC, ATL ou outras pessoas, em seguida, um manifesto pode ser gerado automaticamente pelo vinculador.

Os cabeçalhos de bibliotecas do Visual C++ contêm informações de assembly e, quando as bibliotecas são incluídas no código do aplicativo, essas informações de assembly são usadas pelo vinculador para formar um manifesto para o binário final. O vinculador não insere o arquivo de manifesto dentro do binário e só pode gerar o manifesto como um arquivo externo. Com um manifesto de um arquivo externo pode não funcionar para todos os cenários. Por exemplo, é recomendável que os assemblies particulares têm inseridos manifestos. Em builds de linha de comando, como aqueles que usam nmake para compilar o código, um manifesto pode ser inserido usando a ferramenta de manifesto. Para obter mais informações, consulte [geração de manifesto na linha de comando](../build/manifest-generation-at-the-command-line.md). Ao compilar no Visual Studio, um manifesto pode ser inserido, definindo uma propriedade para a ferramenta de manifesto na **propriedades do projeto** caixa de diálogo, consulte [geração de manifesto no Visual Studio](../build/manifest-generation-in-visual-studio.md).

## <a name="see-also"></a>Consulte também

[Conceitos de aplicativos isolados e assemblies lado a lado](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[Compilando aplicativos isolados do C/C++ e assemblies lado a lado](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)