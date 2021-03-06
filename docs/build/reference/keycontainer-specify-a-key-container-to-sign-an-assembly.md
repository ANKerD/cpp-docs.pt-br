---
title: -KEYCONTAINER (especificar um contêiner de chave para assinar um Assembly) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.KeyContainer
- /keycontainer
dev_langs:
- C++
helpviewer_keywords:
- KEYCONTAINER linker option
- /KEYCONTAINER linker option
- -KEYCONTAINER linker option
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 850a8173dba3e69eaf52fdf174674e1dba58a4d8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723756"
---
# <a name="keycontainer-specify-a-key-container-to-sign-an-assembly"></a>/KEYCONTAINER (especificar um contêiner de chave para assinar um assembly)

```
/KEYCONTAINER:name
```

## <a name="arguments"></a>Arguments

*name*<br/>
Contêiner que contém a chave. Coloque a cadeia de caracteres entre aspas duplas ("") se ele contiver um espaço.

## <a name="remarks"></a>Comentários

O vinculador cria um assembly assinado, inserindo uma chave pública no manifesto do assembly e assinando o assembly definitivo com a chave privada. Para gerar um arquivo de chave, digite [sn -k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* na linha de comando. **sn -i** instala o par de chaves no contêiner.

Se você compilar com [/LN](../../build/reference/ln-create-msil-module.md), o nome do arquivo de chave será mantido no módulo e incorporado no assembly que é criado quando você compila um assembly que inclui uma referência explícita para o módulo, por meio de [#using](../../preprocessor/hash-using-directive-cpp.md), ou ao vincular com [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).

Você também pode passar suas informações de criptografia para o compilador com [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md). Use [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md) se você quiser um assembly parcialmente assinado. Ver [Assemblies de nome forte (assinatura de Assembly) (C + + / CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) para obter mais informações sobre como assinar um assembly.

Outras opções de vinculador que afetam a geração de assembly são:

- [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)

- [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do vinculador no ambiente de desenvolvimento do Visual Studio

1. Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, consulte [configuração de propriedades do projeto Visual C++](../../ide/working-with-project-properties.md).

1. Clique o **vinculador** pasta.

1. Clique o **linha de comando** página de propriedades.

1. Digite a opção para o **opções adicionais** caixa.

### <a name="to-set-this-linker-option-programmatically"></a>Para definir esta opção do vinculador por meio de programação

- Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Consulte também

[Definindo opções de vinculador](../../build/reference/setting-linker-options.md)<br/>
[Opções do vinculador](../../build/reference/linker-options.md)