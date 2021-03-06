---
title: -TLBID (especificar ID de recurso para TypeLib) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
dev_langs:
- C++
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e34e4d27c374fddd7710431e3a09f6a9ccfc802d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701301"
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID (especificar ID do recurso para TypeLib)

```
/TLBID:id
```

## <a name="arguments"></a>Arguments

*id*<br/>
Um valor especificado pelo usuário para uma biblioteca de tipos criada pelo vinculador. Ela substitui a ID de recurso padrão de 1.

## <a name="remarks"></a>Comentários

Ao compilar um programa que usa atributos, o vinculador criará uma biblioteca de tipos. O vinculador atribuirá uma ID de recurso de 1 para a biblioteca de tipos.

Se esta ID de recurso está em conflito com um dos seus recursos existentes, você pode especificar o outra ID com /TLBID. O intervalo de valores que você pode passar para `id` é de 1 a 65535.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do vinculador no ambiente de desenvolvimento do Visual Studio

1. Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, consulte [configuração de propriedades do projeto Visual C++](../../ide/working-with-project-properties.md).

1. Clique o **vinculador** pasta.

1. Clique o **IDL incorporado** página de propriedades.

1. Modificar a **ID de recurso TypeLib** propriedade.

### <a name="to-set-this-linker-option-programmatically"></a>Para definir esta opção do vinculador por meio de programação

1. Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>.

## <a name="see-also"></a>Consulte também

[Definindo opções de vinculador](../../build/reference/setting-linker-options.md)<br/>
[Opções do vinculador](../../build/reference/linker-options.md)