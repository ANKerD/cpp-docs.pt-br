---
title: Gerenciamento de memória com CStringT | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringT
- ATL::CStringT
- ATL.CStringT
dev_langs:
- C++
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8676626c47471c2d1702d49df3069b618cc3ff4f
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752200"
---
# <a name="memory-management-with-cstringt"></a>Gerenciamento de memória com CStringT

Classe [CStringT](../atl-mfc-shared/reference/cstringt-class.md) é uma classe de modelo usada para manipular cadeias de caracteres de comprimento variável. A memória para manter essas cadeias de caracteres é alocada e liberada por meio de um objeto do Gerenciador de cadeia de caracteres, associado a cada instância de `CStringT`. MFC e ATL fornecem instanciações de padrão de `CStringT`, chamado `CString`, `CStringA`, e `CStringW`, que manipulam cadeias de caracteres de diferentes tipos de caracteres. Esses tipos de caractere são do tipo TCHAR, **char**, e `wchar_t`, respectivamente. Esses tipos de cadeia de caracteres padrão usam um Gerenciador de cadeia de caracteres que aloca memória do heap de processo (em ATL) ou o heap de CRT (em MFC). Para aplicativos típicos, esse esquema de alocação de memória é suficiente. No entanto, para fazer com uso intensivo de código use cadeias de caracteres (ou um código multithread) os gerenciadores de memória padrão não podem executar de forma ideal. Este tópico descreve como substituir o comportamento de gerenciamento de memória padrão do `CStringT`, criar alocadores especificamente otimizada para a tarefa em questão.

- [Implementação de um gerenciador de cadeia de caracteres personalizada (método básico)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)

- [Evitar contenção de heap](../atl-mfc-shared/avoidance-of-heap-contention.md)

- [Implementação de um gerenciador de cadeia de caracteres personalizada (método avançado)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)

- [CFixedStringT: Exemplo de um Gerenciador de cadeia de caracteres personalizada](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)

## <a name="see-also"></a>Consulte também

[Exemplo de CustomString](../visual-cpp-samples.md)

