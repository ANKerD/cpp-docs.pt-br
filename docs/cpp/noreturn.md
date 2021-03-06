---
title: noreturn | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noreturn_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6133fc70c5c2b8bb8f794746c1d5ca11be97b817
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031035"
---
# <a name="noreturn"></a>noreturn

## <a name="microsoft-specific"></a>Específico da Microsoft

Isso **declspec** atributo diz ao compilador que uma função não retorna. Como consequência, o compilador sabe que o código que segue uma chamada para um **__declspec(noreturn)** função está inacessível.

Se o compilador encontra uma função com um caminho de controle que não retorna um valor, ele gera um aviso (C4715) ou uma mensagem de erro (C2202). Se o caminho de controle não pode ser acessado devido a uma função que nunca retorna, você pode usar **__declspec(noreturn)** para evitar esse aviso ou erro.

> [!NOTE]
>  Adicionando **__declspec(noreturn)** para uma função que deve retornar pode resultar em comportamento indefinido.

## <a name="example"></a>Exemplo

No exemplo a seguir, o **else** cláusula não contém uma instrução return.  Declarando `fatal` como **__declspec(noreturn)** evita uma mensagem de aviso ou erro.

```cpp
// noreturn2.cpp
__declspec(noreturn) extern void fatal () {}

int main() {
   if(1)
     return 1;
   else if(0)
     return 0;
   else
     fatal();
}
```

## <a name="see-also"></a>Consulte também

[__declspec](../cpp/declspec.md)<br/>
[Palavras-chave](../cpp/keywords-cpp.md)