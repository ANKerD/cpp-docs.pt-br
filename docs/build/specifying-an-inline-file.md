---
title: Especificando um arquivo embutido | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73983094f10088920100b4fbbb8d870aee13f05e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720558"
---
# <a name="specifying-an-inline-file"></a>Especificando um arquivo embutido

Especificar dois colchetes angulares (<<) no comando onde *filename* deve ser exibido. Os colchetes angulares não pode ser uma expansão de macro.

## <a name="syntax"></a>Sintaxe

```
<<[filename]
```

## <a name="remarks"></a>Comentários

Quando o comando é executado, os colchetes angulares são substituídos por *filename*, se especificado, ou por um nome exclusivo gerado pelo NMAKE. Se especificado, *filename* deve seguir sem um espaço ou tabulação colchetes angulares. Um caminho é permitido. Nenhuma extensão é necessária ou supõe-se. Se *filename* for especificado, o arquivo é criado no atual ou o diretório especificado, substituindo qualquer arquivo com esse nome; caso contrário, ele é criado no diretório TMP (ou o diretório atual, se a variável de ambiente TMP não é definido). Se um anterior *filename* é reutilizado, NMAKE substituirá o arquivo anterior.

## <a name="see-also"></a>Consulte também

[Arquivos embutidos em um makefile](../build/inline-files-in-a-makefile.md)