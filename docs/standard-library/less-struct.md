---
title: Struct less | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xfunctional/std::less
dev_langs: C++
helpviewer_keywords:
- less struct
- less function
ms.assetid: 39349da3-11cd-4774-b2cc-b46af5aae5d7
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 723881fd2f46addf6b7e68a9672d5a7c546ca7d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="less-struct"></a>Struct less
Um predicado binário que executa a operação "menor que" ( `operator<`) em seus argumentos.  
  
## <a name="syntax"></a>Sintaxe  
  
```
template <class Type = void>
struct less : public binary_function <Type, Type, bool>  
{
    bool operator()(const Type& Left, const Type& Right) const;
 };

// specialized transparent functor for operator<
template <>
struct less<void>  
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) <std::forward<U>(Right));
 };
```  
  
#### <a name="parameters"></a>Parâmetros  
 `Type`, `T`, `U`  
 Qualquer tipo que dê suporte a um `operator<` que usa operandos dos tipos especificados ou inferidos.  
  
 `Left`  
 O operando esquerdo da operação "menor que". O modelo não especializado usa um argumento de referência lvalue do tipo `Type`. O modelo especializado realiza o encaminhamento perfeito dos argumentos de referência lvalue e rvalue do tipo inferido `T`.  
  
 `Right`  
 O operando direito da operação "menor que". O modelo não especializado usa um argumento de referência lvalue do tipo `Type`. O modelo especializado realiza o encaminhamento perfeito dos argumentos de referência lvalue e rvalue do tipo inferido `U`.  
  
## <a name="return-value"></a>Valor de retorno  
 O resultado de `Left < Right`. O modelo especializado realiza o encaminhamento perfeito do resultado, que tem o tipo retornado por `operator<`.  
  
## <a name="remarks"></a>Comentários  
 O predicado binário `less`< `Type`> fornece uma ordenação fraca estrita de um conjunto de valores de elemento do tipo `Type` em classes de equivalência, se e somente se esse tipo atender aos requisitos matemáticos padrão para ser ordenado dessa forma. As especializações de qualquer tipo de ponteiro produzem uma ordenação total dos elementos, pois todos os elementos de valores distintos são ordenados em relação uns aos outros.  
  
## <a name="example"></a>Exemplo  
  
```cpp  
// functional_less.cpp  
// compile with: /EHsc  
#include <vector>  
#include <algorithm>  
#include <functional>  
#include <iostream>  
  
struct MyStruct {  
   MyStruct(int i) : m_i(i){}  
  
   bool operator < (const MyStruct & rhs) const {  
      return m_i < rhs.m_i;  
   }     
  
   int m_i;  
};  
  
int main() {  
   using namespace std;  
   vector <MyStruct> v1;  
   vector <MyStruct>::iterator Iter1;  
   vector <MyStruct>::reverse_iterator rIter1;  
  
   int i;  
   for ( i = 0 ; i < 7 ; i++ )       
       v1.push_back( MyStruct(rand()));  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin() ; Iter1 != v1.end() ; Iter1++ )   
cout << Iter1->m_i << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   sort( v1.begin( ), v1.end( ), less<MyStruct>());  
  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin() ; Iter1 != v1.end() ; Iter1++ )   
cout << Iter1->m_i << " ";  
   cout << ")" << endl;  
 }  
```  
  
## <a name="output"></a>Saída  
  
```
Original vector v1 = (41 18467 6334 26500 19169 15724 11478)
Sorted vector v1 = (41 6334 11478 15724 18467 19169 26500)
```  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<functional>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Consulte também  
 [Referência da biblioteca padrão C++](../standard-library/cpp-standard-library-reference.md)


