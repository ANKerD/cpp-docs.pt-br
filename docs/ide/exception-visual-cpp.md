---
title: '&lt;exception&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- exception
- <exception>
dev_langs:
- C++
helpviewer_keywords:
- <exception> C++ XML tag
- exception C++ XML tag
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb7b5f4e153ca892cf10f8c5cbe6fe1bebbd20f2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419953"
---
# <a name="ltexceptiongt-visual-c"></a>&lt;exception&gt; (Visual C++)

A marca \<exception> permite que você especifique quais exceções podem ser lançadas. Essa marcação é aplicada a uma definição de método.

## <a name="syntax"></a>Sintaxe

```
<exception cref="member">description</exception>
```

#### <a name="parameters"></a>Parâmetros

*member*<br/>
Uma referência a uma exceção que está disponível no ambiente de compilação atual. Usando as regras da pesquisa de nome, o compilador verifica se a exceção fornecida existe e converte `member` no nome de elemento canônico no XML de saída.  O compilador emite um aviso se não encontra `member`.

Coloque o nome entre aspas simples ou duplas.

Para obter informações sobre como criar uma referência cref para um tipo genérico, consulte [ \<consulte>](../ide/see-visual-cpp.md).

*description*<br/>
Uma descrição.

## <a name="remarks"></a>Comentários

Compile com [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) para processar comentários de documentação em um arquivo.

O compilador do Visual C++ tentará resolver as referências cref em uma passagem pelos comentários da documentação.  Portanto, se você estiver usando as regras de pesquisa do C++ e um símbolo não for encontrado pelo compilador, a referência será marcada como não resolvida. Confira [\<seealso>](../ide/seealso-visual-cpp.md) para obter mais informações.

## <a name="example"></a>Exemplo

```
// xml_exception_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_exception_tag.dll
using namespace System;

/// Text for class EClass.
public ref class EClass : public Exception {
   // class definition ...
};

/// <exception cref="System.Exception">Thrown when... .</exception>
public ref class TestClass {
   void Test() {
      try {
      }
      catch(EClass^) {
      }
   }
};
```

## <a name="see-also"></a>Consulte também

[Documentação XML](../ide/xml-documentation-visual-cpp.md)