---
title: Classes de referência de modelo (C + + c++ /CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd720c2bdcc9bd0baab2606e473858450508feff
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107166"
---
# <a name="template-ref-classes-ccx"></a>Classes de referência de modelo (C++/CX)

Os modelos do C++ não são publicados em metadados e, portanto, não podem ter acessibilidade pública ou protegida no seu programa. Naturalmente, você pode usar modelos padrão do C++ internamente em seu programa. Além disso, você pode definir uma classe ref privada como um modelo e pode declarar explicitamente uma classe ref de modelo especializado como um membro privado em uma classe ref pública.

## <a name="authoring-ref-class-templates"></a>Criando modelos de classe ref

O exemplo a seguir mostra como declarar uma classe ref privada como um modelo, como declarar um modelo padrão do C++ e como declará-los como membros em uma classe ref pública. Observe que o modelo padrão do C++ pode ser especializado por um tipo de tempo de execução do Windows, neste caso um Platform:: String ^.

[!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]

## <a name="see-also"></a>Consulte também

[Sistema de tipos (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Referência de linguagem do Visual C++](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Referência de namespaces](../cppcx/namespaces-reference-c-cx.md)