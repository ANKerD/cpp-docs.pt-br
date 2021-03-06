---
title: Classe wbuffer_convert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
dev_langs:
- C++
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56f7a4bffc557e473299b7f57266def87bf0cfc3
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235835"
---
# <a name="wbufferconvert-class"></a>Classe wbuffer_convert

Descreve um buffer de fluxo que controla a transmissão de elementos de/para um buffer de fluxo de bytes.

## <a name="syntax"></a>Sintaxe

```cpp
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
    : public std::basic_streambuf<Elem, Traits>
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------------|-----------------|
|*Codecvt*|A faceta de [locale](../standard-library/locale-class.md) que representa o objeto de conversão.|
|*Elem*|O tipo de elemento de caractere largo.|
|*Características*|As características associadas a *Elem*.|

## <a name="remarks"></a>Comentários

Essa classe de modelo descreve um buffer de fluxo que controla a transmissão de elementos do tipo `_Elem`, cujas características dos caracteres são descritas pela classe `Traits`, de/para um buffer de fluxo de bytes do tipo `std::streambuf`.

A conversão entre uma sequência de valores `Elem` e as sequências multibyte é executada por um objeto da classe `Codecvt<Elem, char, std::mbstate_t>`, que atende aos requisitos da faceta de conversão de código padrão `std::codecvt<Elem, char, std::mbstate_t>`.

Um objeto desta classe de modelo armazena:

- Um ponteiro para o buffer de fluxo de bytes subjacente

- Um ponteiro para o objeto de conversão alocado (que é liberado quando [wbuffer_convert](../standard-library/wbuffer-convert-class.md)
