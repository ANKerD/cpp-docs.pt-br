---
title: Instanciação do modelo de função | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- templates, instantiation
- function templates, instantiation
- instantiation, function templates
ms.assetid: f22a07c7-3ad1-465a-84f5-8737e274bd47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb94a54c4f99b79e3be742c5b1448151cff140c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116783"
---
# <a name="function-template-instantiation"></a>Instanciação do modelo de função

Quando um modelo da função é chamado primeiramente para cada tipo, o compilador cria uma instanciação. Cada instanciação é uma versão da função em modelo, especializada para o tipo. Essa instanciação será chamada sempre que a função for usada para o tipo. Se você tiver várias instanciações idênticas, mesmo em módulos diferentes, apenas uma cópia de instanciação terminará acima no arquivo executável.

A conversão de argumentos da função é permitida em modelos de função para qualquer par de argumento e de parâmetro, nos quais o parâmetro não depende de um argumento de modelo.

Os modelos da função podem ser instanciados explicitamente declarando o modelo com um tipo específico como um argumento. Por exemplo, o código a seguir é permitido:

```cpp
// function_template_instantiation.cpp
template<class T> void f(T) { }

// Instantiate f with the explicitly specified template.
// argument 'int'
//
template void f<int> (int);

// Instantiate f with the deduced template argument 'char'.
template void f(char);
int main()
{
}
```

## <a name="see-also"></a>Consulte também

[Modelos de função](../cpp/function-templates.md)