---
title: Solução de problemas de personalizações de build | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- build events [C++], troubleshooting
- builds [C++], build events
- troubleshooting [C++], builds
- build steps [C++], troubleshooting
- events [C++], build
- builds [C++], troubleshooting
- custom build steps [C++], troubleshooting
ms.assetid: e4ceb177-fbee-4ed3-a7d7-80f0d78c1d07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2821c851c5b4498250a78f33eb111dd5f20ae272
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43895143"
---
# <a name="troubleshooting-build-customizations"></a>Solucionando problemas de personalizações do build

Se os eventos ou as etapas de build personalizadas não estão funcionando conforme esperado, há várias coisas que você pode fazer para tentar entender o que está errado.

- Verifique se os arquivos gerados pelas etapas de build personalizadas correspondem aos arquivos declarados como saídas.

- Se as etapas de build personalizadas geram arquivos que são entradas ou dependências de outras etapas de build (personalizadas ou não), verifique se esses arquivos são adicionados ao projeto. Além disso, verifique se as ferramentas que consomem os arquivos são executadas após a etapa de build personalizada.

- Para exibir o que a etapa de build personalizada está realmente fazendo, adicione `@echo on` como o primeiro comando. As etapas e os eventos de build são colocados em um arquivo .bat temporário e executados quando o projeto é compilado. Portanto, você pode adicionar a verificação de erros aos comandos do evento ou da etapa de build.

- Examine o log de build no diretório de arquivos intermediários para ver o que realmente foi executado. O caminho e o nome do log de build é representado pela expressão de macro **$(IntDir)\\$(MSBuildProjectName).log** do **MSBuild**.

- Modifique as configurações do projeto para coletar mais do que a quantidade padrão de informações no log de build. No menu **Ferramentas**, clique em **Opções**. Na caixa de diálogo **Opções**, clique no nó **Projetos e Soluções** e, em seguida, clique no nó **Compilar e Executar**. Em seguida, na caixa **Detalhes do arquivo de log de build do projeto do MSBuild**, clique em **Detalhado**.

- Verifique os valores das macros de diretório ou de nome de arquivo que você está usando. Você pode ecoar as macros individualmente ou adicionar `copy %0 command.bat` ao início da etapa de build personalizada, o que copiará os comandos da etapa de build personalizada para command.bat com todas as macros expandidas.

- Execute os eventos e as etapas de build personalizadas individualmente para verificar o comportamento.

## <a name="see-also"></a>Consulte também

[Noções básicas sobre etapas e eventos compilação personalizada](../ide/understanding-custom-build-steps-and-build-events.md)