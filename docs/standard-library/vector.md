---
title: '&lt;vector&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <vector>
dev_langs: C++
helpviewer_keywords: vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e2c1f1b0d9c3b7c5949166b0018bf1e6e6fcbd14
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="ltvectorgt"></a>&lt;vector&gt;
Define o vetor da classe de modelo de contêiner e diversos modelos de suporte.  
  
 O `vector` é um contêiner que organiza os elementos de um determinado tipo em uma sequência linear. Ele permite acesso aleatório rápido a qualquer elemento, bem como adições e remoções dinâmicas em relação à sequência. O `vector` é o contêiner preferencial para uma sequência quando o desempenho de acesso aleatório é reduzido.  
  
 Para obter mais informações sobre a classe `vector`, consulte [Classe vector](../standard-library/vector-class.md). Para obter informações sobre a especialização `vector<bool>`, consulte [Classe vector\<bool>](../standard-library/vector-bool-class.md).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
namespace std {  
template <class Type, class Allocator>  
class vector;  
template <class Allocator>  
class vector<bool>;  
 
template <class Allocator>  
struct hash<vector<bool, Allocator>>;  
 // TEMPLATE FUNCTIONS  
template <class Type, class Allocator>  
bool operator== (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator!= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator<(
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator> (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator<= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator>= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
void swap (
    vector<Type, Allocator>& left,  
    vector<Type, Allocator>& right);

}  // namespace std  
```  
  
#### <a name="parameters"></a>Parâmetros  
 Tipo  
 O parâmetro de modelo do tipo de dados armazenados no vetor.  
  
 Allocator  
 O parâmetro de modelo do objeto allocator armazenado responsável pela alocação e desalocação de memória.  
  
 `left`  
 O primeiro vetor (à esquerda) em uma operação de comparação  
  
 `right`  
 O segundo vetor (à direita) em uma operação de comparação.  
  
### <a name="operators"></a>Operadores  
  
|||  
|-|-|  
|[operator! =](../standard-library/vector-operators.md#op_neq)|Testa se o objeto vector do lado esquerdo do operador não é igual ao objeto vector do lado direito.|  
|[operator<](../standard-library/vector-operators.md#op_lt)|Testa se o objeto vector do lado esquerdo do operador é menor que o objeto vector do lado direito.|  
|[operator\<=](../standard-library/vector-operators.md#op_gt_eq)|Testa se o objeto vector do lado esquerdo do operador é menor ou igual ao objeto vector do lado direito.|  
|[operator==](../standard-library/vector-operators.md#op_eq_eq)|Testa se o objeto vector do lado esquerdo do operador é igual ao objeto vector do lado direito.|  
|[operator>](../standard-library/vector-operators.md#op_gt)|Testa se o objeto vector do lado esquerdo do operador é maior que o objeto vector do lado direito.|  
|[operator>=](../standard-library/vector-operators.md#op_gt_eq)|Testa se o objeto vector do lado esquerdo do operador é maior ou igual ao objeto vector do lado direito.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[Classe vector](../standard-library/vector-class.md)|Uma classe de modelo de contêineres de sequências que organiza os elementos de um determinado tipo de maneira linear e permite o acesso aleatório rápido a qualquer elemento.|  
  
### <a name="specializations"></a>Especializações  
  
|||  
|-|-|  
|[Classe vector\<bool>](../standard-library/vector-bool-class.md)|Uma especialização completa do vetor de classe de modelo dos elementos do tipo `bool` com um alocador para o tipo subjacente usado pela especialização.|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<vector>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Consulte também  
 [Referência de Arquivos de Cabeçalho](../standard-library/cpp-standard-library-header-files.md)   
 [Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Referência da biblioteca padrão C++](../standard-library/cpp-standard-library-reference.md)
