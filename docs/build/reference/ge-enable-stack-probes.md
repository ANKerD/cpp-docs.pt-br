---
title: -Ge (habilitar sondas de pilha) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ge
dev_langs:
- C++
helpviewer_keywords:
- -Ge compiler option [C++]
- enable stack probes
- /Ge compiler option [C++]
- stack, stack probes
- stack probes
- stack checking calls
- Ge compiler option [C++]
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1819e3e8aa5f48c36b8fc48641f13ac6059043e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720915"
---
# <a name="ge-enable-stack-probes"></a>/Ge (habilitar sondas de pilha)

Ativa sondas de pilha para cada chamada de função que requer o armazenamento para variáveis locais.

## <a name="syntax"></a>Sintaxe

```
/Ge
```

## <a name="remarks"></a>Comentários

Esse mecanismo é útil se você reescrever a funcionalidade de sonda de pilha. É recomendável que você use [/Gh (habilitar penter função de gancho)](../../build/reference/gh-enable-penter-hook-function.md) em vez de reescrever a sonda de pilha.

[/GS (chamadas de verificação de pilha de controle)](../../build/reference/gs-control-stack-checking-calls.md) tem o mesmo efeito.

**/GE** é preterido; a partir do Visual Studio 2005, o compilador gera automaticamente a verificação de pilha. Para obter uma lista de opções do compilador preterido, consulte **preteridos e removidos opções do compilador** na [opções de compilador listadas por categoria](../../build/reference/compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do compilador no ambiente de desenvolvimento do Visual Studio

1. Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, confira [Trabalhando com propriedades do projeto](../../ide/working-with-project-properties.md).

1. Clique o **C/C++** pasta.

1. Clique o **linha de comando** página de propriedades.

1. Digite a opção de compilador na **opções adicionais** caixa.

### <a name="to-set-this-compiler-option-programmatically"></a>Para definir essa opção do compilador via programação

- Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Consulte também

[Opções do Compilador](../../build/reference/compiler-options.md)<br/>
[Definindo opções do compilador](../../build/reference/setting-compiler-options.md)