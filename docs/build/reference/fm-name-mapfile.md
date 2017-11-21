---
title: -Fm (Mapfile de nome) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /fm
dev_langs: C++
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 153a91d25a45a86f01885b679f039f41390dc291
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="fm-name-mapfile"></a>/Fm (mapfile de nome)
Informa o vinculador para produzir um arquivo de mapa que contém uma lista de segmentos na ordem em que aparecem no arquivo .exe correspondente ou DLL.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
/Fmpathname  
```  
  
## <a name="remarks"></a>Comentários  
 Por padrão, o arquivo de mapa recebe o nome base do arquivo de origem C ou C++ correspondente com um. Extensão do mapa.  
  
 Especificando **/Fm** tem o mesmo efeito como se você tiver especificado o [/MAP (Gerar Mapfile)](../../build/reference/map-generate-mapfile.md) opção de vinculador.  
  
 Se você especificar [/c (compilar sem vinculação)](../../build/reference/c-compile-without-linking.md) para suprimir a vinculação, **/Fm** não tem nenhum efeito.  
  
 Símbolos globais em um arquivo de mapa geralmente têm um ou mais sublinhados porque o compilador adiciona um sublinhado à esquerda para nomes de variável. Vários símbolos globais que aparecem no arquivo de mapa são usados internamente pelo compilador e as bibliotecas padrão.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do compilador no ambiente de desenvolvimento do Visual Studio  
  
1.  Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, consulte [trabalhar com propriedades do projeto](../../ide/working-with-project-properties.md).  
  
2.  Clique o **C/C++** pasta.  
  
3.  Clique o **linha de comando** página de propriedades.  
  
4.  Digite a opção de compilador no **opções adicionais** caixa.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Para definir essa opção do compilador via programação  
  
-   Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Consulte também  
 [Arquivo de saída (/ F) opções](../../build/reference/output-file-f-options.md)   
 [Opções do compilador](../../build/reference/compiler-options.md)   
 [Definindo opções do compilador](../../build/reference/setting-compiler-options.md)   
 [Especificando o nome de caminho](../../build/reference/specifying-the-pathname.md)