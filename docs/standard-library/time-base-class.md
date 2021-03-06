---
title: Classe time_base | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- locale/std::time_base
dev_langs:
- C++
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e4e371bd242dff337450fd87527455b50556afc
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235770"
---
# <a name="timebase-class"></a>Classe time_base

A classe serve como uma classe base para facetas de modelo classe time_get, definindo apenas o tipo enumerado `dateorder` e várias constantes desse tipo.

## <a name="syntax"></a>Sintaxe

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {
        no_order,
        dmy,
        mdy,
        ymd,
        ydm
    };
    time_base(size_t _Refs = 0)
    ~time_base();
};
```

## <a name="remarks"></a>Comentários

Cada constante caracteriza uma maneira diferente de ordenar os componentes de uma data. As constantes são:

- `no_order` não especifica nenhuma ordem específica.

- `dmy` Especifica a ordem dia, mês e ano, como em 2 de dezembro de 1979.

- `mdy` Especifica o mês do pedido, dia e ano, como em 2 de dezembro de 1979.

- `ymd` Especifica a ordem ano, mês e dia, como em 1979/12/2.

- `ydm` Especifica a ordem ano, dia e mês, como em 1979:2 de dezembro.

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Consulte também

[Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
