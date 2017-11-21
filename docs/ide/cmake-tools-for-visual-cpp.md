---
title: CMake projetos em Visual C++ | Microsoft Docs
ms.custom: 
ms.date: 08/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 770b7f70e52859b1489b984d8aef3c3876a9ca83
ms.sourcegitcommit: 1b480aa74886930b3bd0435d71cfcc3ccda36424
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2017
---
# <a name="cmake-projects-in-visual-c"></a>CMake projetos em Visual C++
Este artigo pressupõe que você esteja familiarizado com CMake, uma ferramenta de plataforma cruzada, o código-fonte aberto para definir os processos de compilação que são executados em várias plataformas.  

Até recentemente, os usuários do Visual Studio podem usar CMake para gerar arquivos de projeto MSBuild, o IDE consumido para IntelliSense, navegação e compilação. A partir do Visual Studio de 2017, o **ferramentas do Visual C++ para CMake** componente usa o recurso de "Abrir pasta" para permitir que o IDE para consumo de arquivos de projeto CMake (como CMakeLists.txt) diretamente para fins de IntelliSense e pesquisa. Se você usar um gerador de Visual Studio, um arquivo de projeto temporário é gerado e passado para msbuild.exe, mas nunca é carregado para o IntelliSense ou navegação fins. 

**Visual Studio 2017 versão 15,3**: suporte é fornecido para geradores Ninja e o Visual Studio.

**Visual Studio 2017 versão 15.4**: é adicionado suporte para CMake no Linux. Para obter mais informações, consulte [configurar um projeto de CMake Linux](../linux/cmake-linux-project.md).

## <a name="installing"></a>Instalando o
Ferramentas do Visual C++ para CMake é instalada por padrão como parte do desenvolvimento da área de trabalho com carga de trabalho do C++.

![Componente CMake na carga de trabalho da área de trabalho do C++](media/cmake-install.png)
 
## <a name="ide-integration"></a>Integração de IDE
Quando você escolhe **arquivo | Abrir | Pasta** para abrir uma pasta que contém um arquivo CMakeLists.txt, acontece o seguinte:
- O Visual Studio adiciona um **CMake** item de menu ao menu principal, com comandos para exibir e editar scripts CMake. 
- **Gerenciador de soluções** exibe a estrutura de pastas e arquivos. 
- Visual Studio executa CMake.exe e gera o cache para o padrão de CMake *configuração*, que é x86 de depuração. A linha de comando CMake é exibida no **a janela de saída**, juntamente com a saída adicional de CMake.
- Em segundo plano, o Visual Studio inicia indexar os arquivos de origem para habilitar o IntelliSense, informações de navegação, refatoração e assim por diante. Conforme você trabalha, o Visual Studio monitora as alterações feitas no editor e também no disco para manter seu índice em sincronia com as fontes. Você pode abrir pastas que contenham qualquer número de projetos de CMake. Visual Studio detecta e configura todos os arquivos de CMakeLists.txt "raiz" em seu espaço de trabalho. Operações de CMake (configurar, desenvolver, depurar), bem como o C++ IntelliSense e pesquisa estão disponíveis para todos os projetos de CMake no espaço de trabalho.

![Projeto CMake com várias raízes](media/cmake-multiple-roots.png) 

## <a name="building-cmake-projects"></a>Construindo projetos do CMake
Para criar um projeto de CMake, você tem estas opções:
1. Selecione o destino na lista suspensa de depuração e pressione **F5** ou clique no botão "Executar". O projeto será automaticamente compilação pela primeira vez, assim como com soluções do Visual Studio.
2.  Clique com o botão direito no CMakeLists.txt e selecione a compilação no menu de contexto. Se você tiver vários destinos na estrutura de pasta, você pode optar por criar todos os ou apenas um destino específico, ou
  
3. No menu principal, selecione **compilar | Criar solução** (**F7** ou **Ctrl + Shift + B**) (certifique-se de que um destino CMake já está selecionado no **Item de inicialização** suspensa no **Geral** barra de ferramentas).

![Comando de menu build CMake](media/cmake-build-menu.png) 
 
Quando um gerador de Visual Studio é selecionado para a configuração ativa, MSBuild.exe é invocado com `-m -v:minimal` argumentos. Para personalizar a compilação, dentro do arquivo CMakeSettings.json, você pode especificar argumentos de linha de comando adicionais a serem passados para o sistema de compilação por meio de `buildCommandArgs` propriedade:

```json
"buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
```
Como se esperaria, resultados de compilação são mostrados na **a janela de saída** e **lista de erros**.
 
![Erros de compilação CMake](media/cmake-build-errors.png)

Em uma pasta com vários destinos de compilação, você pode escolher o item de compilação no menu CMake ou o menu de contexto CMakeLists.txt para especificar qual destino CMake para compilar. Pressionar **Ctrl + Shift + B** um CMake projeto compila o documento ativo atual. 

## <a name="debugging-the-project"></a>Depuração do projeto
Para depurar um projeto CMake, escolha a configuração desejada e pressione **F5**, ou pressione o botão Executar na barra de ferramentas. Se o botão Executar diz "Selecione o Item de inicialização", clique na seta para baixo e escolha o destino que você deseja executar. (Em um projeto de CMake, o "documento atual" opção só é válida para arquivos. cpp.) 

 ![Botão CMake executar](media/cmake-run-button.png)

 Pressionar **F5** será a primeira compilação do projeto se as alterações foram feitas desde a compilação anterior.

## <a name="configuring-cmake-debugging-sessions"></a>Configurando CMake as sessões de depuração
Todos os destinos CMake executável são mostrados na lista suspensa na barra de ferramentas geral de Item de inicialização. Para iniciar uma sessão de depuração, basta selecionar um e iniciar o depurador.

 ![Lista suspensa de item de inicialização CMake](media/cmake-startup-item-dropdown.png)

Você também pode iniciar uma sessão de depuração dos menus CMake.

Para personalizar as configurações do depurador para qualquer destino CMake executável em seu projeto, clique com botão direito no arquivo CMakeLists.txt específico e selecione **depuração e iniciar configurações**, quando você selecionar um destino de CMake no submenu, um arquivo chamado Launch.vs.JSON é criado. Esse arquivo é preenchido com informações sobre o destino CMake selecionado e permite que você especifique parâmetros adicionais, como argumentos de programa ou tipo de depurador. Para fazer referência a qualquer chave em um arquivo CMakeSettings.json, preceda-o com "cmake". em launch.vs.json. O exemplo a seguir mostra um arquivo de launch.vs.json simples que recebe o valor da chave "remoteCopySources" no arquivo CMakeSettings.json da configuração selecionada no momento:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
   {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "name": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "args": ["${cmake.remoteCopySources}"]
    }
  ]
}
```
Assim que você salvar o arquivo launch.vs.json, é criada uma entrada na lista suspensa de Item de inicialização com o novo nome. Editando o arquivo de launch.vs.json, você pode criar como muitas configurações de depuração que desejar para qualquer número de destinos de CMake.

**Visual Studio 2017 versão 15.4**: Launch.vs.json oferece suporte a variáveis que são declarados nos CMakeSettings.json (veja abaixo). Ele também tem um conceito do "currentDir", que será definido como o diretório atual do aplicativo Iniciar:

```json
{
"type": "default",
"project": "CMakeLists.txt",
"projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```
Quando você executa o aplicativo, o valor de `currentDir` é 

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```
 

## <a name="editing-cmakeliststxt-files"></a>Edição de arquivos CMakeLists.txt
Para editar um arquivo CMakeLists.txt, clique com botão direito no arquivo no **Solution Explorer** e escolha **abrir**. Se você fizer alterações no arquivo, uma barra de status amarelo aparece e informa que o IntelliSense atualizará e lhe dá a oportunidade de cancelar a operação de atualização. Para obter informações sobre CMakeLists.txt, consulte o [CMake documentação](https://cmake.org/documentation/).

  ![Edição de arquivos CMakeLists.txt](media/cmake-cmakelists.png)

Assim que você salvar o arquivo, a etapa de configuração será automaticamente execute novamente e exibir informações na janela de saída. Erros e avisos são mostrados na lista de erros ou janela de saída. Clique duas vezes em um erro na lista de erros para navegar até a linha incorreto no CMakeLists.txt.

  ![Erros de arquivo CMakeLists.txt](media/cmake-cmakelists-error.png)
 
## <a name="cmake_settings"></a>Configurações de CMake e configurações personalizadas
Por padrão, o Visual Studio fornece seis CMake as configurações padrão ("depurar x86", "versão x86", "x64-Debug", "x64-versão", "Linux-Debug" e "Versão do Linux"). Essas configurações definem como CMake.exe é chamado para criar o cache de CMake para um determinado projeto. Para modificar essas configurações, ou criar uma nova configuração personalizada, escolha **CMake | Alterar configuração CMake**e, em seguida, escolha o arquivo de CMakeLists.txt que aplicarão as configurações. As configurações de CMake de alteração também está disponível no menu de contexto do arquivo em **Gerenciador de soluções**. Este comando cria um arquivo CMakeSettings.json na pasta do projeto. Esse arquivo é usado para recriar o arquivo de cache CMake, por exemplo após uma operação de "Limpeza". 

  ![Comando de menu principal CMake para alterar as configurações](media/cmake-change-settings.png)
 
JSON IntelliSense ajuda a editar o arquivo CMakeSettings.json:

   ![IntelliSense CMake JSON](media/cmake-json-intellisense.png)

O exemplo a seguir mostra uma configuração de exemplo, você pode usar como ponto de partida para criar seus próprios em CMakeSettings.json:
```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },

```
1.  nome: o nome que será exibido na lista suspensa de configuração do C++. Esse valor de propriedade também pode ser usado como uma macro `${name}` para especificar outros valores de propriedade. Para obter um exemplo, consulte a definição de "buildRoot" no CMakeSettings.json.
2.  Gerador: é mapeado para a opção -G e especifica o gerador a ser usado. Essa propriedade também pode ser usada como uma macro `${generator}` para ajudar a especificar outros valores de propriedade. O Visual Studio atualmente suporta os geradores de CMake a seguir:
    - "Ninja"
    - "Visual Studio 2015 14"
    - "Visual Studio 2015 14 ARM"
    - "Visual Studio 2015 14 Win64"
    - "Visual Studio 15 2017"
    - "Visual Studio 15 2017 ARM"
    - "Visual Studio 15 2017 Win64"
    - 
Como Ninja destina-se a velocidades de compilações rápido em vez de flexibilidade e a função, ele é definido como padrão. No entanto, alguns projetos CMake será possível compilar corretamente usando Ninja. Se isso ocorrer, você pode instruir CMake para gerar um projeto do Visual Studio em vez disso. 

Para especificar um gerador de Visual Studio, abra o CMakeSettings.json no menu principal, escolhendo **CMake | Alterar as configurações de CMake**. Exclua "Ninja" e digite "V". Isso ativa o IntelliSense, que permite que você escolha o gerador de desejado.
3.  buildRoot: mapeia para - switch DCMAKE_BINARY_DIR e especifica qual cache CMake será criado. Se a pasta não existir, ele será criado.
4.  variáveis: contém um par de nome + valor das variáveis de CMake que será passado como - Dname = value para CMake. Se as instruções de compilação de projeto CMake especifiquem a adição de quaisquer variáveis diretamente para o arquivo de cache CMake, é recomendável que você adicioná-los aqui em vez disso.
5.  cmakeCommandArgs: especifica quaisquer opções adicionais que você deseja passar para CMake.exe.
6.  configurationType: define o tipo de configuração de compilação para o gerador de selecionada. Valores com suporte no momento são "Debug", "MinSizeRel", "Versão" e "RelWithDebInfo".

### <a name="environment-variables"></a>Variáveis de ambiente
CMakeSettings.json também oferece suporte a variáveis de ambiente consumo em qualquer uma das propriedades mencionadas acima. A sintaxe para usar é `${env.FOO}` para expandir o ambiente variável FOO %.
Você também tem acesso para macros internas dentro desse arquivo:
- `${workspaceRoot}`– fornece o caminho completo da pasta de espaço de trabalho
- `${workspaceHash}`– hash do local do espaço de trabalho. útil para criar um identificador exclusivo para o espaço de trabalho atual (por exemplo, para usar em caminhos de pastas)
- `${projectFile}`– o caminho completo do arquivo raiz CMakeLists.txt
- `${projectDir}`– o caminho completo da pasta do arquivo raiz CMakeLists.txt
- `${thisFile}`– o caminho completo do arquivo CMakeSettings.json
- `${name}`– o nome da configuração
- `${generator}`– o nome do gerador CMake usado nesta configuração de

### <a name="ninja-command-line-arguments"></a>Argumentos de linha de comando Ninja

Se os destinos estiverem especificados, cria o destino de 'default' (consulte o manual).

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Opção|Descrição|  
|--------------|------------|  
| -versão  | versão de impressão ninja ("1.7.1")| 
|   -C DIR   | Alterar para DIR antes de fazer mais nada| 
|   -f arquivo  | Especifique o arquivo de entrada de compilação [default=build.ninja]| 
|   N -j     | executar trabalhos N em paralelo [padrão = 14, derivada de CPUs disponíveis]| 
|   -k N     | prossiga até N trabalhos falharem [padrão = 1]| 
|   -l N     | não inicie novos trabalhos se a média de carga é maior que N| 
|   -n      | Seque executar (não execute comandos mas atue como tiveram êxito)| 
|   -v       | Mostrar todas as linhas de comando durante a compilação| 
|   -d modo  | Habilitar a depuração (-d lista para modos de uso)| 
|   -t ferramenta  | Execute um subtool (use -t lista para subferramentas). encerra toplevel opções; ainda mais os sinalizadores são passados para a ferramenta| 
|   -w sinalizador  | Ajustar avisos (avisos -w uma lista para uso)| 


### <a name="inherited-environments-visual-studio-2017-version-155"></a>Ambientes herdadas (Visual Studio de 2017 versão 15,5)

CmakeSettings.json agora dá suporte a ambientes de inherted. Esse recurso permite que você crie uma variável personalizada que:

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

Este campo define as variáveis que são passados automaticamente para CMake.exe quando ele é executado. O exemplo acima é o mesmo que executar "Desenvolvedor Prompt de comando para VS 2017" com o `-arch=amd64 -host_arch=amd64` argumentos.

A tabela a seguir mostra os valores com suporte e seus equivalentes de linha de comando:

|Nome do contexto|Descrição|  
|-----------|-----------------|
|vsdev|Ambiente do Visual Studio padrão|
|msvc_x86|Compilar para x86 usando x86 ferramentas|
|msvc_arm| Compilar para ARM usando x86 ferramentas|
|msvc_arm64|Compilar para ARM64 usando x86 ferramentas|
|msvc_x86_x64|Compilar para AMD64 usando x86 ferramentas|
|msvc_x64_x64|Compilar para AMD64 usando ferramentas de 64 bits|
|msvc_arm_x64|Compilar para ARM usando ferramentas de 64 bits|
|msvc_arm64_x64|Compilar para ARM64 usando as ferramentas de 64 bits|


Quando alterações significativas são feitas para o CMakeSettings.json ou CMakeLists.txt arquivos, o Visual Studio automaticamente executa novamente o CMake configurar etapa. Se a etapa de configuração concluída sem erros, as informações coletadas estarão disponíveis nos serviços de IntelliSense do C++ e linguagem e também na compilação e operações de depuração.

Quando vários projetos CMake usam o mesmo nome de configuração de CMake (por exemplo, x86-Debug), todos eles são configurados e criados (em sua própria pasta raiz de compilação) quando essa configuração é selecionada. Você pode depurar os destinos de todos os projetos CMake que participam de que a configuração CMake.

   ![CMake compilar apenas o item de menu](media/cmake-build-only.png)

Para limitar os builds e depurar sessões para um subconjunto dos projetos no espaço de trabalho, crie uma nova configuração com um nome exclusivo no arquivo CMakeSettings.json e aplique-o para apenas esses projetos. Quando essa configuração é selecionada, IntelliSense, compilar, e a depuração será ativada somente para aqueles especificados projetos.

## <a name="troubleshooting-cmake-cache-errors"></a>Solucionando problemas de erros de cache CMake
Se você precisar de mais informações sobre o estado do cache CMake para diagnosticar um problema, abra o menu principal CMake ou o menu de contexto CMakeLists.txt **Solution Explorer** para executar um destes comandos:
- **Exibir o Cache** abre o arquivo CMakeCache.txt da pasta raiz de compilação no editor. (Todas as edições feitas aqui CMakeCache.txt são apagadas se você limpar o cache. Para fazer alterações que persistem depois que o cache é limpo, consulte [CMake definições e configurações personalizadas](#cmake_settings) anteriormente neste artigo.)
- **Abra a pasta de Cache** abre uma janela do Explorer para a pasta raiz de compilação.  
- **Limpar Cache** exclui a pasta raiz de compilação para que o próximo CMake configurar etapa iniciada a partir de um cache limpo.
- **Gerar o Cache** força a etapa de gerar a ser executada, mesmo que o Visual Studio considera o ambiente atualizado.
