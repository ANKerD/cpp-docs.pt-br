---
title: -GR (Habilitar informações de tipo de tempo de execução) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gr
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
dev_langs:
- C++
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24ef844c716d64e609440d41bf55db20308c02f1
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712238"
---
# <a name="gr-enable-run-time-type-information"></a>/GR (habilitar informações de tipo de tempo de execução)

Adiciona código para verificar tipos de objeto em tempo de execução.

## <a name="syntax"></a>Sintaxe

```
/GR[-]
```

## <a name="remarks"></a>Comentários

Quando **/GR** estiver ativado, o compilador define o `_CPPRTTI` macro do pré-processador. Por padrão, **/GR** está em. **/GR-.** desabilita as informações de tipo de tempo de execução.

Use **/GR** se o compilador não consegue resolver estaticamente um tipo de objeto em seu código. Normalmente, você precisa de **/GR** quando seu código usa a opção [operador dynamic_cast](../../cpp/dynamic-cast-operator.md) ou [typeid](../../cpp/typeid-operator.md). No entanto, **/GR** aumenta o tamanho das seções da imagem. RDATA. Se seu código não usa **dynamic_cast** ou **typeid**, **/GR-.** pode produzir uma imagem menor.

Para obter mais informações sobre a verificação de tipo de tempo de execução, consulte [informações de tipo de tempo de execução](../../cpp/run-time-type-information.md) na *referência da linguagem C++*.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do compilador no ambiente de desenvolvimento do Visual Studio

1. Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, confira [Trabalhando com propriedades do projeto](../../ide/working-with-project-properties.md).

1. Clique o **C/C++** pasta.

1. Clique o **linguagem** página de propriedades.

1. Modificar a **habilitar informações de tipo de tempo de execução** propriedade.

### <a name="to-set-this-compiler-option-programmatically"></a>Para definir essa opção do compilador via programação

- Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>.

## <a name="see-also"></a>Consulte também

[Opções do Compilador](../../build/reference/compiler-options.md)<br/>
[Definindo opções do compilador](../../build/reference/setting-compiler-options.md)