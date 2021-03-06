---
title: Classe regex_traits&lt;wchar_t&gt; | Microsoft Docs
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- regex/std::regex_traits<wchar_t>
dev_langs:
- C++
helpviewer_keywords:
- regex_traits<wchar_t> class
ms.assetid: 288d6fdb-fb8e-4a4d-904a-53916be7f95b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff84c0d8b3da721c5d5830be798e2ff03947a16a
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691634"
---
# <a name="regextraitsltwchartgt-class"></a>Classe regex_traits&lt;wchar_t&gt;

Especialização de `regex_traits` para **wchar_t**.

## <a name="syntax"></a>Sintaxe

```cpp
template <>
class regex_traits<wchar_t>
```

## <a name="remarks"></a>Comentários

A classe é uma especialização explícita da classe de modelo [regex_traits](../standard-library/regex-traits-class.md) para elementos do tipo **wchar_t** (de modo que ele pode tirar proveito das funções de biblioteca que manipulam objetos desse tipo).

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<regex>

**Namespace:** std

## <a name="see-also"></a>Consulte também

[\<regex>](../standard-library/regex.md)<br/>
[Classe regex_constants](../standard-library/regex-constants-class.md)<br/>
[Classe regex_error](../standard-library/regex-error-class.md)<br/>
[\<Funções regex>](../standard-library/regex-functions.md)<br/>
[Classe regex_iterator](../standard-library/regex-iterator-class.md)<br/>
[\<Operadores regex>](../standard-library/regex-operators.md)<br/>
[Classe regex_token_iterator](../standard-library/regex-token-iterator-class.md)<br/>
[Classe regex_traits](../standard-library/regex-traits-class.md)<br/>
[\<Typedef regex>](../standard-library/regex-typedefs.md)<br/>
