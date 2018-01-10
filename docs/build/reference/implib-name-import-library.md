---
title: "-IMPLIB (biblioteca de importações de Name) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /implib
- VC.Project.VCLinkerTool.ImportLIbrary
dev_langs: C++
helpviewer_keywords:
- IMPLIB linker option
- /IMPLIB linker option
- -IMPLIB linker option
- import libraries, overriding default name
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 523fc171aa8df3d0b4c6e09909db7c2c1dc0b833
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="implib-name-import-library"></a>/IMPLIB (nomear biblioteca de importações)
  
> /IMPLIB:*filename*  
  
## <a name="parameters"></a>Parâmetros  
  
*filename*  
Um nome de usuário especificado para a biblioteca de importação. Ele substitui o nome padrão.  
  
## <a name="remarks"></a>Comentários  
  
A opção /IMPLIB substitui o nome padrão para a biblioteca de importação LINK cria quando ele cria um programa que contém exportações. O nome padrão é formado pelo nome base do arquivo de saída principal e a extensão. lib. Um programa contém exportações se forem especificadas uma ou mais das seguintes opções:  
  
-   O [dllexport](../../cpp/dllexport-dllimport.md) palavra-chave no código-fonte  
  
-   [Exportações](../../build/reference/exports.md) instrução em um arquivo. def  
  
-   Um [/exportação](../../build/reference/export-exports-a-function.md) especificação em um comando LINK  
  
 LINK ignora /IMPLIB quando uma biblioteca de importação não está sendo criada. Se nenhuma exportação for especificada, o LINK não cria uma biblioteca de importação. Se um arquivo de exportação é usado na compilação, o LINK pressupõe que uma biblioteca de importação já existe e não cria uma. Para obter informações sobre bibliotecas de importação e exportação de arquivos, consulte [referência LIB](../../build/reference/lib-reference.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do vinculador no ambiente de desenvolvimento do Visual Studio  
  
1.  Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, consulte [configuração Visual C++ Project Properties](../../ide/working-with-project-properties.md).  
  
2.  Clique o **vinculador** pasta.  
  
3.  Clique o **avançado** página de propriedades.  
  
4.  Modificar o **biblioteca de importação** propriedade.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Para definir esta opção do vinculador por meio de programação  
  
-   Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>.  
  
## <a name="see-also"></a>Consulte também  
 [Definindo opções de vinculador](../../build/reference/setting-linker-options.md)   
 [Opções do vinculador](../../build/reference/linker-options.md)