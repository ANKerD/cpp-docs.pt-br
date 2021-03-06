---
title: Especificando o nome do caminho | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 636326e5af577b4e26c61a2094fe73dd4a680f2d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402467"
---
# <a name="specifying-the-pathname"></a>Especificando o nome de demarcador

Cada opção de arquivo de saída aceita uma *pathname* argumento que pode especificar um local e um nome para o arquivo de saída. O argumento pode incluir um nome da unidade, o diretório e o nome do arquivo. Nenhum espaço é permitido entre a opção e argumento.

Se *pathname* inclui um nome de arquivo sem uma extensão, o compilador fornece a saída uma extensão padrão. Se *pathname* inclui um diretório, mas nenhum nome de arquivo, o compilador cria um arquivo com um nome padrão no diretório especificado. O nome padrão é baseado no nome base do arquivo de origem e uma extensão padrão com base no tipo de arquivo de saída. Se você deixar de fora *pathname* totalmente, o compilador cria um arquivo com um nome padrão em um diretório padrão.

Como alternativa, o *pathname* argumento pode ser um nome de dispositivo (AUX, CON, PRN ou NUL) em vez de um nome de arquivo. Não use um espaço entre a opção e o nome do dispositivo ou dois-pontos como parte do nome do dispositivo.

|Nome do dispositivo|Representa|
|-----------------|----------------|
|AUX|Dispositivo auxiliar|
|CON|Console|
|PRN|Impressora|
|NUL|Dispositivo nulo (nenhum arquivo criado)|

## <a name="example"></a>Exemplo

A linha de comando a seguir envia um arquivo de mapa para a impressora:

```
CL /FmPRN HELLO.CPP
```

## <a name="see-also"></a>Consulte também

[Opções do arquivo de saída (/F)](../../build/reference/output-file-f-options.md)<br/>
[Opções do Compilador](../../build/reference/compiler-options.md)<br/>
[Definindo opções do compilador](../../build/reference/setting-compiler-options.md)