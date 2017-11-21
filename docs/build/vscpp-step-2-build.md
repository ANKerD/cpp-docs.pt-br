---
title: 'Etapa 2: criar e executar um projeto de aplicativo de console C++ | Microsoft Docs'
description: Instalar o suporte do Visual Studio para Visual C++
ms.custom: mvc
ms.date: 10/17/2017
ms.topic: get-started-article
ms.technology: devlang-C++
ms.devlang: C++
dev_langs: C++
ms.assetid: 45138d71-719d-42dc-90d7-1d0ca31a2f55
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 20a8bafa69631ef8df1fb20f613dfbb81578f94a
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2017
---
# <a name="build-and-run-a-c-console-app-project"></a>Compilar e executar um projeto de aplicativo de console C++

Quando você criar um projeto de aplicativo de console C++ e inseriu o código, compilação e executá-lo no Visual Studio e, em seguida, executá-lo como um aplicativo autônomo da linha de comando.

## <a name="prerequisites"></a>Pré-requisitos

- Ter o Visual Studio com o desenvolvimento de área de trabalho com carga de trabalho C++ instalado e em execução no seu computador. Se ele ainda não estiver instalado, siga as etapas em [etapa 0 - suporte instalar C++ no Visual Studio](../build/vscpp-step-0-installation.md).

- Criar um "Olá, mundo!" projeto e insira seu código-fonte. Se você ainda não tiver feito isso ainda, siga as etapas em [etapa 1: criar um projeto de aplicativo de console C++](../build/vscpp-step-1-create.md).

Se o Visual Studio tem esta aparência, você estará pronto para compilar e executar seu aplicativo:

   ![Pronto para criar o novo projeto](../build/media/vscpp-ready-to-build.png "pronto para criar o novo projeto")

## <a name="build-and-run-your-code-in-visual-studio"></a>Compilar e executar seu código no Visual Studio

1. Para criar seu projeto, escolha **compilar solução** do **criar** menu. O **saída** janela mostra os resultados do processo de compilação.

   ![Compilar o projeto](../build/media/vscpp-build-solution.gif "compilar o projeto")

1. Para executar o código, na barra de menus, escolha **depurar**, **iniciar sem depuração**.

   ![Inicie o projeto](../build/media/vscpp-start-without-debugging.gif "iniciar o projeto")

    Uma janela do console é aberto e, em seguida, executa seu aplicativo. Quando você inicia um aplicativo de console no Visual Studio, executar seu código, em seguida, imprime "Pressione qualquer tecla para continuar. . ." para que você possa ver a saída.

Parabéns! Você criou seu primeiro "Olá, mundo!" aplicativo de console no Visual Studio! Pressione uma tecla para fechar a janela do console e retornar ao Visual Studio.

[Encontrei um problema.](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>Executar seu código em uma janela de comando

Normalmente, os aplicativos de console são executados no prompt de comando, não no Visual Studio. Depois que seu aplicativo é criado pelo Visual Studio, você pode executá-lo em qualquer janela de comando. Aqui está como localizar e executar seu aplicativo de novo em uma janela de prompt de comando.

1. Em **Solution Explorer**, selecione a Solução HelloWorld e com o botão direito para abrir o menu de contexto. Escolha **Abrir pasta no Explorador de arquivos** para abrir um **Explorador de arquivos** janela na pasta da Solução HelloWorld.

1. No **Explorador de arquivos** janela, abra a pasta de depuração. Essa exibição contém seu aplicativo, HelloWorld.exe e alguns outros arquivos de depuração. Selecione HelloWorld.exe, mantenha pressionada a tecla Shift e clique para abrir o menu de contexto. Escolha **cópia como caminho** para copiar o caminho para seu aplicativo na área de transferência.

1. Para abrir uma janela de prompt de comando, pressione Windows-R para abrir o **executar** caixa de diálogo. Insira *cmd.exe* no **abrir** caixa de texto, escolha **Okey** para executar uma janela de prompt de comando.

1. Na janela do prompt de comando, clique com botão direito para colar o caminho para seu aplicativo no prompt de comando. Pressione Enter para executar seu aplicativo.

   ![Executar o aplicativo no prompt de comando](../build/media/vscpp-run-in-cmd.gif "executar o aplicativo no prompt de comando")

Parabéns, você criou e executar um aplicativo de console no Visual Studio!

[Encontrei um problema.](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>Próximas etapas

Depois que você criou e executar esse aplicativo simple, você está pronto para projetos mais complexos. Consulte os guias de início rápido, tutoriais e código de exemplo para obter exemplos de coisas que você pode fazer em C++ usando o Visual Studio.

## <a name="troubleshooting-guide"></a>Guia de solução de problemas

Vir aqui para soluções para problemas comuns ao criar seu primeiro projeto C++.

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>Compilar e executar seu código em problemas do Visual Studio

Se linhas onduladas vermelhas aparecem em qualquer coisa no editor de código fonte, a compilação pode ter erros ou avisos. Verifique se o seu código corresponde o exemplo no caso de ortografia e pontuação.

[Voltar.](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>Executar seu código em uma janela de comando problemas

Você também pode navegar para a pasta de solução de depuração na linha de comando para executar seu aplicativo. Você não pode executar seu aplicativo de outros diretórios sem especificar o caminho para o aplicativo. No entanto, você pode copiar o seu aplicativo para outro diretório e executá-lo lá.

[Voltar.](#run-your-code-in-a-command-window)


<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />