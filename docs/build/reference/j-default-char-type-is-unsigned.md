---
title: -J (char padrão não é do tipo assinado) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned
- VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned
- /j
dev_langs:
- C++
helpviewer_keywords:
- defaults, char type
- char data type
- -J compiler option [C++]
- /J compiler option [C++]
- J compiler option [C++]
- default char type is unsigned
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 400985751d9ceebf7cc2c5f632cb33c5ba847bfe
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714279"
---
# <a name="j-default-char-type-is-unsigned"></a>/J (o tipo char padrão não é assinado)

Altera o padrão `char` tipo do `signed char` à `unsigned char`e o `char` tipo é estendido em zero quando ele é ampliado para um `int` tipo.

## <a name="syntax"></a>Sintaxe

```
/J
```

## <a name="remarks"></a>Comentários

Se um `char` valor for declarado explicitamente como `signed`, o **/J** opção não afeta e o valor será estendido com sinal quando ele é ampliado para um `int` tipo.

O **/J** opção define `_CHAR_UNSIGNED`, que é usado com `#ifndef` no arquivo Limits. h para definir o intervalo padrão do `char` tipo.

ANSI C e C++ não exigem uma implementação específica do `char` tipo. Essa opção é útil quando você estiver trabalhando com dados de caractere que eventualmente serão convertidos em um idioma diferente do inglês.

> [!NOTE]
>  Se você usar essa opção do compilador com da ATL/MFC, pode ser gerado um erro. Você pode desativar esse erro definindo `_ATL_ALLOW_CHAR_UNSIGNED`, essa solução alternativa não é suportada e pode não funcionar.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do compilador no ambiente de desenvolvimento do Visual Studio

1. No **Gerenciador de Soluções**, abra o menu de atalho para o projeto e escolha **Propriedades**.

1. No projeto **páginas de propriedades** caixa de diálogo, no painel esquerdo, em **propriedades de configuração**, expanda **C/C++** e, em seguida, selecione **delinhadecomando**.

1. No **opções adicionais** painel, especifique a **/J** opção de compilador.

### <a name="to-set-this-compiler-option-programmatically"></a>Para definir essa opção do compilador via programação

- Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>.

## <a name="see-also"></a>Consulte também

[Opções do Compilador](../../build/reference/compiler-options.md)<br/>
[Definindo opções do compilador](../../build/reference/setting-compiler-options.md)<br/>
[Trabalhando com Propriedades do Projeto](../../ide/working-with-project-properties.md)