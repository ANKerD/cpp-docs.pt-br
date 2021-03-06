---
title: -clr (Common Language Runtime Compilation) | Microsoft Docs
ms.custom: ''
ms.date: 09/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLR
- VC.Project.VCNMakeTool.CompileAsManaged
- VC.Project.VCCLCompilerTool.CompileAsManaged
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, common language runtime option
- -clr compiler option [C++]
- clr compiler option [C++]
- /clr compiler option [C++]
- Managed Extensions for C++, compiling
- common language runtime, /clr compiler option
ms.assetid: fec5a8c0-40ec-484c-a213-8dec918c1d6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dcd5739f2fb0663609ce7bcabc920cc3aa20d8e1
ms.sourcegitcommit: 338e1ddc2f3869d92ba4b73599d35374cf1d5b69
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2018
ms.locfileid: "46494407"
---
# <a name="clr-common-language-runtime-compilation"></a>/clr (compilação do Common Language Runtime)

Permite que aplicativos e componentes usem recursos do CLR (Common Language Runtime).

## <a name="syntax"></a>Sintaxe

> **/CLR**[**:**_opções_]

## <a name="arguments"></a>Arguments

*options*<br/>
Uma ou mais das seguintes opções, separados por vírgulas.

- nenhum

   Sem opções **/clr** cria metadados para o aplicativo. Os metadados podem ser consumidos por outros aplicativos CLR e permite que o aplicativo consuma dados nos metadados de outros componentes CLR e tipos. Para obter mais informações, consulte [Assemblies mistos (nativos e gerenciados)](../../dotnet/mixed-native-and-managed-assemblies.md).

- **puro**

   **/CLR: pure foi preterido**. A opção é removida no Visual Studio 2017. É recomendável que você porta o código que deve ser a MSIL puro para c#.

- **seguro**

   **/CLR: safe é preterida**. A opção é removida no Visual Studio 2017. É recomendável que você porta o código que deve ser a MSIL seguro para c#.

- **noAssembly**

   **/CLR:noAssembly é preterida**. Use [/LN (Criar módulo de MSIL)](../../build/reference/ln-create-msil-module.md) em vez disso.

   Especifica que um manifesto do assembly não deve ser inserido no arquivo de saída. Por padrão, o **noAssembly** opção não estiver em vigor.

   Um programa gerenciado que não tem metadados de assembly no manifesto é conhecido como um *módulo*. O **noAssembly** opção pode ser usada somente para produzir um módulo. Se você compilar usando [/c](../../build/reference/c-compile-without-linking.md) e **/clr:noAssembly**, em seguida, especifique a [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) opção na fase de vinculador para criar um módulo.

   Antes do Visual C++ 2005, **/clr:noAssembly** necessária **/LD**. **/LD** agora está implícita quando você especifica **/clr:noAssembly**.

- **initialAppDomain**

   Permite que um aplicativo do Visual C++ executar a versão 1 do CLR.  Um aplicativo que é compilado usando **initialAppDomain** não deve ser usado por um aplicativo que usa o ASP.NET porque ele não é suportado na versão 1 do CLR.

- **/nostdlib**

   Instrui o compilador para ignorar o diretório de \clr padrão. O compilador produz erros se você estiver incluindo várias versões de uma DLL como System. dll. Usando essa opção permite especificar a estrutura específica para usar durante a compilação.

## <a name="remarks"></a>Comentários

Código gerenciado é o código que pode ser inspecionado e gerenciado pelo CLR. Código gerenciado pode acessar objetos gerenciados. Para obter mais informações, consulte [/clr Restrições](../../build/reference/clr-restrictions.md).

Para obter informações sobre como desenvolver aplicativos que definem e consumam tipos gerenciados, consulte [extensões de componentes para plataformas de tempo de execução](../../windows/component-extensions-for-runtime-platforms.md).

Um aplicativo compilado usando **/clr** pode ou não conter dados gerenciados.

Para habilitar a depuração em um aplicativo gerenciado, consulte [/ASSEMBLYDEBUG (Adicionar DebuggableAttribute)](../../build/reference/assemblydebug-add-debuggableattribute.md).

Somente os tipos CLR serão instanciados no heap coletado como lixo. Para obter mais informações, consulte [Classes e Structs](../../windows/classes-and-structs-cpp-component-extensions.md). Para compilar uma função para código nativo, use o `unmanaged` pragma. Para obter mais informações, consulte [gerenciado, não gerenciado](../../preprocessor/managed-unmanaged.md).

Por padrão, **/clr** não está em vigor. Quando **/clr** está em vigor, **/MD** também está em vigor. Para obter mais informações, consulte [/MD, /MT, /LD (usar biblioteca em tempo de execução)](../../build/reference/md-mt-ld-use-run-time-library.md). **/MD** garante que as versões multi-threaded e vinculadas dinamicamente as rotinas de tempo de execução são selecionadas dos arquivos de cabeçalho padrão (. h). O multithreading é necessário para porque o coletor de lixo do CLR executa os finalizadores em um thread auxiliar de programação gerenciada.

Se você compilar usando **/c**, você pode especificar o tipo CLR do arquivo de saída resultante com [/CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md).

**/CLR** implica **/EHa**e nenhum outro **/EH** opções têm suporte para **/clr**. Para obter mais informações, consulte [/EH (modelo de tratamento de exceção)](../../build/reference/eh-exception-handling-model.md).

Para obter informações sobre como determinar o tipo de imagem CLR de um arquivo, consulte [/clrheader](../../build/reference/clrheader.md).

Todos os módulos passados para determinada invocação do vinculador devem ser compilados usando a mesma opção de compilador da biblioteca de tempo de execução (**/MD** ou **/LD**).

Use o [/ASSEMBLYRESOURCE.](../../build/reference/assemblyresource-embed-a-managed-resource.md) opção de vinculador para inserir um recurso em um assembly. [/ DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md), [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md), e [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) opções do vinculador também permitem que você personalize como um assembly é criado.

Quando **/clr** for usado, o `_MANAGED` símbolo é definido como 1. Para obter mais informações, consulte [Macros predefinidas](../../preprocessor/predefined-macros.md).

As variáveis globais em um arquivo de objeto nativo são inicializadas primeiro (durante DllMain se o executável é uma DLL) e, em seguida, as variáveis globais na seção gerenciada são inicializados (antes de qualquer código gerenciado é executado). `#pragma` [init_seg](../../preprocessor/init-seg.md) só afeta a ordem de inicialização nas categorias gerenciadas e não gerenciados.

## <a name="metadata-and-unnamed-classes"></a>Metadados e Classes sem nome

Classes sem nome serão exibido nos metadados nomeados da seguinte maneira: `$UnnamedClass$` *crc-de-atual-file-name*`$`*índice*`$`, onde *índice*é uma contagem sequencial das classes sem nome na compilação. Por exemplo, o exemplo de código a seguir gera uma classe sem nome nos metadados.

```cpp
// clr_unnamed_class.cpp
// compile by using: /clr /LD
class {} x;
```

Use ildasm.exe para exibir os metadados.

## <a name="see-also"></a>Consulte também

[Opções do Compilador](../../build/reference/compiler-options.md)<br/>
[Definindo opções do compilador](../../build/reference/setting-compiler-options.md)