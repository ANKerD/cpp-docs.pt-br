---
title: E/S de arquivo de modo de texto e binário | Microsoft Docs
ms.custom: ''
ms.date: 04/11/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- files [C++], open functions
- I/O [CRT], text files
- functions [CRT], file access
- binary access, binary mode file I/O
- translation, modes
- I/O [CRT], binary
- text files, I/O
- I/O [CRT], translation modes
- translation modes (file I/O)
- binary access
ms.assetid: 3196e321-8b87-4609-b302-cd6f3c516051
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 133f62347998ad8238c3136c3de03b08ba41346d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116250"
---
# <a name="text-and-binary-mode-file-io"></a>E/S de texto e arquivo de modo binário

As operações de E/S de arquivo ocorrem em um de dois modos de translação, *texto* ou *binário*, dependendo do modo em que o arquivo foi aberto. Os arquivos de dados geralmente são processados em modo de texto. Para controlar o modo de translação de arquivo, é possível:

- Manter a configuração padrão atual e especificar o modo alternativo somente quando você abre arquivos selecionados.

- Usar a função [set_fmode](../c-runtime-library/reference/set-fmode.md) para alterar o modo padrão para arquivos abertos recentemente. Usar [get_fmode](../c-runtime-library/reference/get-fmode.md) para localizar o modo padrão atual. A configuração padrão inicial é o modo de texto (**_O_TEXT**).

- Altere o modo de translação padrão diretamente configurando a variável global [_fmode](../c-runtime-library/fmode.md) no seu programa. A função **_set_fmode** define o valor dessa variável, mas ele também pode ser definido diretamente.

Quando você chama uma função de abertura de arquivo, como [_open](../c-runtime-library/reference/open-wopen.md), [fopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md), [freopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md), [_fsopen](../c-runtime-library/reference/fsopen-wfsopen.md) ou [_sopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md), é possível substituir a configuração padrão atual de **_fmode** especificando o argumento apropriado para a função [_set_fmode](../c-runtime-library/reference/set-fmode.md). Os fluxos **stdin**, **stdout** e **stderr** sempre abrem no modo de texto por padrão. Você também pode substituir esse padrão ao abrir qualquer um desses arquivos. Utilize [_setmode](../c-runtime-library/reference/setmode.md) para alterar o modo de translação usando o descritor do arquivo depois que o arquivo está aberto.

## <a name="see-also"></a>Consulte também

[Entrada e saída](../c-runtime-library/input-and-output.md)<br/>
[Rotinas de tempo de execução C universais por categoria](../c-runtime-library/run-time-routines-by-category.md)<br/>
