---
title: -execução-charset (definir conjunto de caracteres de execução) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- execution-charset
- /execution-charset
dev_langs:
- C++
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca6681fde6ae4e46dea62e0258138f567ef8ebc5
ms.sourcegitcommit: 92c568e9466ffd7346a4120c478c9bdea61c8756
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2018
ms.locfileid: "47029600"
---
# <a name="execution-charset-set-execution-character-set"></a>/Execution-charset (definir execução de conjunto de caracteres)

Permite que você especifique o caractere de execução definida para o executável.

## <a name="syntax"></a>Sintaxe

```
/execution-charset:[IANA_name|.CPID]
```

## <a name="arguments"></a>Arguments

*IANA_name*<br/>
Nome do conjunto de caracteres de definido pelo IANA.

*CPID*<br/>
O identificador de página de código.

## <a name="remarks"></a>Comentários

Você pode usar o **/execution-charset** opção para especificar um conjunto de caracteres de execução. O conjunto de caracteres de execução é a codificação usada para o texto do programa que é a entrada para a fase de compilação depois que todas as etapas de pré-processamento. Esse conjunto de caracteres é usado para a representação interna de qualquer cadeia de caracteres ou literais de caracteres no código compilado. Defina essa opção para especificar o conjunto de caracteres estendido de execução para usar quando os arquivos de origem incluem caracteres que não representáveis no conjunto de caracteres de execução básico. Você pode usar qualquer um dos IANA ou nome do conjunto de caracteres ISO ou um ponto (.) seguido por um identificador de página de código decimal de 3 a 5 dígitos para especificar o conjunto de caracteres para usar. Para obter uma lista de identificadores de páginas de código de suporte e os nomes do conjunto de caracteres, consulte [identificadores de páginas de código](/windows/desktop/Intl/code-page-identifiers).

Por padrão, o Visual Studio detecta uma marca de ordem de byte para determinar se o arquivo de origem está em um formato codificado de Unicode, por exemplo, UTF-16 ou UTF-8. Se nenhuma marca de ordem de byte for encontrada, ele pressupõe que o arquivo de origem é codificado usando a página de código do usuário atual, a menos que você especificou um conjunto de caracteres nome ou páginas de código usando o **/source-charset** opção ou a **/utf-8** opção. Visual Studio permite que você salvar seu código-fonte C++, usando qualquer uma das várias codificações de caracteres. Para obter informações sobre conjuntos de caracteres de origem e de execução, consulte [conjuntos de caracteres](../../cpp/character-sets.md) na documentação do idioma.

Se você quiser definir o conjunto de caracteres de origem e o conjunto de caracteres de execução para UTF-8, você pode usar o **/utf-8** opção do compilador como um atalho. Ele equivale à especificação **/origem-charset:utf-/execution 8-charset:utf-8** na linha de comando. Além disso, qualquer uma dessas opções permite que o **/validate-charset** opção por padrão.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do compilador no ambiente de desenvolvimento do Visual Studio

1. Abra o projeto **páginas de propriedade** caixa de diálogo. Para obter mais informações, confira [Trabalhando com propriedades do projeto](../../ide/working-with-project-properties.md).

1. Expanda o **propriedades de configuração**, **C/C++**, **linha de comando** pasta.

1. Na **opções avançadas**, adicione o **/execution-charset** opção e especifique a codificação preferencial.

1. Escolher **Okey** para salvar suas alterações.

## <a name="see-also"></a>Consulte também

[Opções do Compilador](../../build/reference/compiler-options.md)<br/>
[Definindo opções do compilador](../../build/reference/setting-compiler-options.md)<br/>
[/source-charset (definir conjunto de caracteres de origem)](../../build/reference/source-charset-set-source-character-set.md)<br/>
[/utf-8 (definir conjuntos de caracteres de origem e executáveis como UTF-8)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)<br/>
[/validate-charset (validar quanto à presença de caracteres compatíveis)](../../build/reference/validate-charset-validate-for-compatible-characters.md)