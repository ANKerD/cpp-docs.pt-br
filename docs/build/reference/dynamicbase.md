---
title: -DYNAMICBASE | Microsoft Docs
ms.custom: ''
ms.date: 06/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /dynamicbase
dev_langs:
- C++
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 255123157da3f802eafaf26206598d54fea02335
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223410"
---
# <a name="dynamicbase"></a>/DYNAMICBASE

Especifica se deve gerar uma imagem executável que possa ter REBASE aleatória no momento do carregamento usando o recurso de aleatoriedade (ASLR) de layout de espaço de endereço do Windows que foi disponibilizado inicialmente no Windows Vista.

## <a name="syntax"></a>Sintaxe

> **/DYNAMICBASE**[**: NENHUMA**]

## <a name="remarks"></a>Comentários

O **/DYNAMICBASE** opção modifica o cabeçalho de uma *imagem executável*, um arquivo. dll ou .exe, para indicar se o aplicativo deve ter REBASE aleatória no tempo de carregamento e permite que o endereço virtual randomização de alocação, o que afeta o local da memória virtual de heaps, pilhas e outras alocações de sistema operacional. O **/DYNAMICBASE** opção se aplica a imagens de 32 bits e 64 bits. ASLR tem suporte no Windows Vista e sistemas operacionais posteriores. A opção é ignorada por sistemas operacionais anteriores.

Por padrão, **/DYNAMICBASE** está habilitado. Para desabilitar essa opção, use **/DYNAMICBASE: no**. O **/DYNAMICBASE** opção é necessária para o [/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md) opção para ter efeito.

## <a name="see-also"></a>Consulte também

- [Opções de EDITBIN](../../build/reference/editbin-options.md)
- [Defesas de segurança de Software ISV do Windows](https://msdn.microsoft.com/library/bb430720.aspx)