---
title: _WAIT_CHILD, _WAIT_GRANDCHILD | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
dev_langs:
- C++
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7dd7b3fab51c382413c507831572afedd824c3f7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018334"
---
# <a name="waitchild-waitgrandchild"></a>_WAIT_CHILD, _WAIT_GRANDCHILD

## <a name="syntax"></a>Sintaxe

```

#include <process.h>

```

## <a name="remarks"></a>Comentários

A função `_cwait` pode ser usada por qualquer processo para aguardar algum outro processo (se a ID do processo for conhecida). O argumento de ação pode ser um dos seguintes valores:

|Constante|Significado|
|--------------|-------------|
|`_WAIT_CHILD`|O processo de chamada aguarda até que o novo processo especificado seja encerrado.|
|`_WAIT_GRANDCHILD`|O processo de chamada aguarda até que o novo processo especificado e todos os processos criados pelo novo processo sejam encerrados.|

## <a name="see-also"></a>Consulte também

[_cwait](../c-runtime-library/reference/cwait.md)<br/>
[Constantes globais](../c-runtime-library/global-constants.md)