---
title: Constantes de permissão de arquivo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _S_IWRITE
- _S_IREAD
dev_langs:
- C++
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ae2e7d669edda1ab3069cf3cdb30b79482047e5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026628"
---
# <a name="file-permission-constants"></a>Constantes de permissão de arquivo

## <a name="syntax"></a>Sintaxe

```

#include <sys/stat.h>

```

## <a name="remarks"></a>Comentários

Uma dessas constantes é necessária quando `_O_CREAT` (`_open`, `_sopen`) for especificado.

O argumento `pmode` especifica configurações de permissão do arquivo da seguinte maneira.

|Constante|Significado|
|--------------|-------------|
|`_S_IREAD`|Leitura permitida|
|`_S_IWRITE`|Gravação permitida|
|`_S_IREAD` &#124; `_S_IWRITE`|Leitura e gravação permitidas|

Quando usado como o argumento `pmode` para `_umask`, a constante de manifesto define a configuração de permissão, da seguinte maneira.

|Constante|Significado|
|--------------|-------------|
|`_S_IREAD`|Gravação não permitida (o arquivo é somente leitura)|
|`_S_IWRITE`|Leitura não permitida (o arquivo é somente gravação)|
|`_S_IREAD` &#124; `_S_IWRITE`|Leitura ou gravação não são permitidas|

## <a name="see-also"></a>Consulte também

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_umask](../c-runtime-library/reference/umask.md)<br/>
[Tipos padrão](../c-runtime-library/standard-types.md)<br/>
[Constantes globais](../c-runtime-library/global-constants.md)