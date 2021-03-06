---
title: -WINMDFILE (especificar arquivo do winmd) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
dev_langs:
- C++
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d34bdfd2d80690efae8efbc1f95ba0c50a530af3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425776"
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE (Especifica o arquivo winmd)

Especifica o nome de arquivo para o arquivo de saída de metadados de tempo de execução do Windows (. winmd) que é gerado pelo [/WINMD](../../build/reference/winmd-generate-windows-metadata.md) a opção de vinculador.

```
/WINMDFILE:filename
```

## <a name="remarks"></a>Comentários

Use o valor especificado na `filename` para substituir o nome do arquivo. winmd padrão (`binaryname`. winmd). Observe que você não adicionar ". winmd" ao `filename`.  Se vários valores são listados na **/WINMDFILE** linha de comando, o último terá precedência.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do vinculador no ambiente de desenvolvimento do Visual Studio

1. Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, confira [Trabalhando com propriedades do projeto](../../ide/working-with-project-properties.md).

1. Selecione o **vinculador** pasta.

1. Selecione o **metadados do Windows** página de propriedades.

1. No **arquivo de metadados do Windows** , digite o local do arquivo.

## <a name="see-also"></a>Consulte também

[/WINMD (gerar metadados do Windows)](../../build/reference/winmd-generate-windows-metadata.md)<br/>
[Definindo opções de vinculador](../../build/reference/setting-linker-options.md)<br/>
[Opções do vinculador](../../build/reference/linker-options.md)