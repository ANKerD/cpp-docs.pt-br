---
title: Página de propriedades de Diretórios do VC++ | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCDirectories.IncludePath
- VC.Project.VCDirectories.ReferencePath
- VC.Project.VCDirectories.SourcePath
- VC.Project.VCDirectories.LibraryWPath
- VC.Project.VCDirectories.ExecutablePath
- VC.Project.VCDirectories.LibraryPath
- VS.ToolsOptionsPages.Projects.VCDirectories
- VC.Project.VCDirectories.ExcludePath
dev_langs:
- C++
helpviewer_keywords:
- VC++ Directories Property Page
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 238f26e8955d4be676c3bf37f7cc8b2d842b3de9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394424"
---
# <a name="vc-directories-property-page-windows"></a>Página de propriedades de Diretórios do VC++ (Windows)

Use esta página de propriedades para informar o Visual Studio de quais diretórios devem ser usados ao compilar o projeto atualmente selecionado. Para definir os diretórios para vários projetos em uma solução, use uma folha de propriedades personalizadas, conforme descrito em [Criando configurações de propriedade reutilizáveis](working-with-project-properties.md#bkmkPropertySheets).

Para obter a versão do Linux desta página, confira [Diretórios do VC++ (Linux C++)](../linux/prop-pages/directories-linux.md).

Para acessar a página de propriedades de **Diretórios do VC++**:

1. Se a janela do **Gerenciador de Soluções** não estiver visível, no menu principal, escolha **Exibir** > **Gerenciador de Soluções**.
1. Clique com o botão direito do mouse em um nó do projeto (não na solução de nível superior) e escolha **Propriedades**.
1. No painel esquerdo da caixa de diálogo **Páginas de Propriedades**, selecione **Propriedades de Configuração** > **Diretórios do VC++**.

As propriedades de Diretórios do VC++ se aplicam a um projeto, não ao nó da solução de nível superior. Se as propriedades de **Diretórios do VC++** não forem exibidas em **Propriedades de Configuração**, selecione um nó do projeto do C++ na janela do **Gerenciador de Soluções**:

![Selecionar o nó do projeto](media/vcppdir.png "Selecionar o nó do projeto para ver as propriedades de Diretórios do VC++")

Observe que a página de propriedades de **Diretórios do VC++** para projetos multiplataforma tem outra aparência. Para obter informações específicas a projetos do Linux C++, confira [Diretórios do VC++ (Linux C++)](../linux/prop-pages/directories-linux.md).

Caso você não esteja familiarizado com as *propriedades do projeto* no Visual Studio, talvez seja útil ler primeiro [Trabalhando com propriedades do projeto](working-with-project-properties.md).

As configurações padrão para as propriedades de **Diretórios do VC++** dependem do tipo de projeto. Para projetos da área de trabalho, elas incluem os locais das ferramentas do C++ de determinado Conjunto de Ferramentas da Plataforma e o local do SDK do Windows. Altere o **Conjunto de Ferramentas da Plataforma** e a **versão do SDK do Windows** na página **Propriedades de Configuração** > **Geral**.

Para exibir os valores para um dos diretórios:

1. Selecione uma das propriedades na página **Diretórios do VC++**. Por exemplo, escolha **Diretórios de Biblioteca**.
1. Escolha o botão de seta para baixo ao final do campo de valor da propriedade.
1. No menu suspenso, escolha **Editar**.

![Editar Diretórios de Biblioteca](media/vcppdir_libdir_edit.png "Caixa de diálogo para editar os caminhos da biblioteca")

Agora você verá uma caixa de diálogo como esta:

![Mostrar Diretórios de Biblioteca](media/vcppdir_libdir.png "Caixa de diálogo para adicionar ou remover caminhos da biblioteca")

Use essa caixa de diálogo para exibir os diretórios atuais. No entanto, caso deseje alterar ou adicionar um diretório, será melhor usar o **Gerenciador de Propriedades** para criar uma folha de propriedades ou modificar a folha de propriedades do usuário padrão. Para obter mais informações, confira [Criando configurações de propriedade reutilizáveis](working-with-project-properties.md#bkmkPropertySheets).

Conforme mostrado acima, muitos dos caminhos herdados são fornecidos como macros.  Para examinar o valor atual de uma macro, escolha o botão **Macros** no canto inferior direito da caixa de diálogo. Observe que muitas macros dependem do tipo de configuração. Uma macro em um build de depuração pode ser avaliada como um caminho diferente comparado à mesma macro em um build de versão.

Pesquise correspondências parciais ou completas na caixa de edição. A ilustração a seguir mostra todas as macros que contêm a cadeia de caracteres "WindowsSDK" e também mostra o caminho atual para o qual a macro é avaliada:

![Veja os valores da macro](media/vcppdir_libdir_macros.png "Caixa de diálogo para editar macros")

Observação: a lista é populada conforme você digita. Não pressione **Enter**.

Para obter mais informações sobre macros e por que você deve usá-las em vez de caminhos embutidos em código, sempre que possível, confira [Trabalhando com propriedades do projeto](../ide/working-with-project-properties.md#bkmkPropertiesVersusMacros).

Para obter uma lista das macros geralmente usadas, confira [Macros comuns para comandos e propriedades de build](https://docs.microsoft.com/en-us/cpp/ide/common-macros-for-build-commands-and-properties).

Defina suas próprias macros de duas maneiras:
-   Defina variáveis de ambiente em um Prompt de Comando do Desenvolvedor. Todas as variáveis de ambiente são tratadas como propriedades/macros do MSBuild.
-   Defina macros do usuário em um arquivo .props. Para obter mais informações, confira [Macros da página de propriedades](working-with-project-properties.md#bkmkPropertiesVersusMacros).

Para obter mais informações, confira estas postagens no blog: [Diretórios do VC++](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx), [Propriedades herdadas e folha de propriedades](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx) e [Guia de Atualização de Projeto do Visual Studio 2010 C++](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx).

## <a name="directory-types"></a>Tipos de diretório

Você também pode especificar outros diretórios, como a seguir.

**Diretórios Executáveis**<br/>
Diretórios onde procurar por arquivos executáveis. Corresponde à variável de ambiente **PATH**.

**Incluir Diretórios**<br/>
Diretórios nos quais procurar por arquivos de inclusão que são referenciados no código-fonte. Corresponde à variável de ambiente **INCLUDE**.

**Diretórios de Referência**<br/>
Diretórios nos quais pesquisar arquivos de assembly e de módulo (metadados) referenciados no código-fonte pela diretiva [#using](../preprocessor/hash-using-directive-cpp.md). Corresponde à variável de ambiente **LIBPATH**.

**Diretórios de Biblioteca**<br/>
Diretórios onde procurar por arquivos de bibliotecas (.lib); isso inclui as bibliotecas em tempo de execução. Corresponde à variável de ambiente **LIB**. Essa configuração não se aplica a arquivos .obj; para criar um vínculo com um arquivo .obj, na página de propriedades de **Propriedades de Configuração** > **Vinculador** > **Geral**, selecione **Dependências de Bibliotecas Adicionais** e, em seguida, especifique o caminho relativo do arquivo. Para obter mais informações, confira [Páginas de propriedades do Vinculador](../ide/linker-property-pages.md).

**Diretórios de Biblioteca WinRT**<br/>
Diretórios nos quais pesquisar arquivos de biblioteca WinRT para uso em aplicativos UWP (Plataforma Universal do Windows).

**Diretórios de Origem**<br/>
Diretórios onde procurar por arquivos de origem para uso para o IntelliSense.

**Excluir Diretórios**<br/>
Antes de cada compilação, o Visual Studio consulta o carimbo de data/hora em todos os arquivos para determinar se um deles foi modificado desde a compilação anterior. Se o projeto tem bibliotecas grandes estáveis, potencialmente, você pode acelerar os tempos de build excluindo esses diretórios da verificação de carimbo de data/hora.

## <a name="sharing-the-settings"></a>Compartilhando as configurações

Você pode compartilhar propriedades do projeto com outros usuários ou em vários computadores. Para obter mais informações, confira [Trabalhando com propriedades do projeto](../ide/working-with-project-properties.md).
