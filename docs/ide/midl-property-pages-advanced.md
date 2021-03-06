---
title: 'Páginas de propriedades de MIDL: Avançado | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCMidlTool.ErrorCheckBounds
- VC.Project.VCMidlTool.ErrorCheckStubData
- VC.Project.VCMidlTool.ErrorCheckAllocations
- VC.Project.VCMidlTool.CPreprocessOptions
- VC.Project.VCMidlTool.UndefinePreprocessorDefinitions
- VC.Project.VCMidlTool.EnableErrorChecks
- VC.Project.VCMidlTool.RedirectOutputAndErrors
- VC.Project.VCMidlTool.ErrorCheckEnumRange
- VC.Project.VCMidlTool.StructMemberAlignment
- VC.Project.VCMidlTool.ErrorCheckRefPointers
- VC.Project.VCMidlTool.ValidateParameters
dev_langs:
- C++
helpviewer_keywords:
- MIDL, property pages
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 11c7d4b437e77e5acfe363fd3b4125477eceb0f2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394953"
---
# <a name="midl-property-pages-advanced"></a>Páginas de propriedade MIDL: avançado

A página de propriedades **Avançado** na pasta **MIDL** especifica as seguintes opções do compilador MIDL:

- Habilitar Verificação de Erros ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- Verificar Alocações ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- Verificar Limites ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- Verificar Intervalo de Enumeração ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- Verificar Ponteiros de Referência ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- Verificar Dados Stub ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- Validar Parâmetros ([/robust](https://msdn.microsoft.com/library/windows/desktop/aa367363)) \*

- Alinhamento de Membro do Struct ([/Zp](https://msdn.microsoft.com/library/windows/desktop/aa367388))

- Redirecionar Saída ([/o](https://msdn.microsoft.com/library/windows/desktop/aa367351))

- Opções de 	Pré-processo C ([/cpp_opt](https://msdn.microsoft.com/library/windows/desktop/aa367318))

- Excluir Definições de Pré-processador ([/U](https://msdn.microsoft.com/library/windows/desktop/aa367373))

\* /robust destina-se apenas ao uso durante o build de um computador Windows 2000 ou posterior. Se você compilar um projeto ATL e desejar usar /robust, altere esta linha no arquivo dlldatax.c:

```
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM
to
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM
```

Para obter informações sobre como acessar a página de propriedades **Avançado** na pasta **MIDL**, confira [Trabalhando com propriedades do projeto](../ide/working-with-project-properties.md).

Para obter informações sobre como acessar as opções de MIDL para projetos do C++ de forma programática, confira <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>.

## <a name="see-also"></a>Consulte também

[Páginas de propriedades de MIDL](../ide/midl-property-pages.md)