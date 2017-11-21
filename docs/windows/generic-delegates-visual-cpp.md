---
title: "Delegados genéricos (Visual C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- generic delegates
- delegates, generic [C++]
ms.assetid: 09d430b2-1aef-4fbc-87f9-9d7b8185d798
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7d09aa9d2ea4df90ad8a74b426942d21ea1d2f6e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="generic-delegates-visual-c"></a>Delegados genéricos (Visual C++)
Você pode usar parâmetros de tipo genérico com delegados. Para obter mais informações sobre delegados, consulte [delegado (extensões de componentes C++)](../windows/delegate-cpp-component-extensions.md).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
[attributes]   
generic < [class | typename] type-parameter-identifiers >  
[type-parameter-constraints-clauses]  
[accessibility-modifiers] delegate result-type identifier   
([formal-parameters]);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `attributes`(Opcional)  
 Informações adicionais de declarativas. Para obter mais informações sobre atributos e classes de atributos, consulte atributos.  
  
 *tipo-parâmetro-identificador (es)*  
 Lista separada por vírgulas de identificadores para os parâmetros de tipo.  
  
 `type-parameter-constraints-clauses`  
 Utiliza o formato especificado no [restrições em parâmetros de tipo genérico (C + + CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)  
  
 *modificadores de acessibilidade* (opcional)  
 Modificadores de acessibilidade (por exemplo, **pública**, `private`).  
  
 *tipo de resultado*  
 O tipo de retorno do delegado.  
  
 *identifier*  
 O nome do representante.  
  
 *parâmetros formais* (opcional)  
 A lista de parâmetros do delegado.  
  
## <a name="example"></a>Exemplo  
 Os parâmetros de tipo de delegado são especificados no ponto em que um objeto de representante é criado. O delegado e o método associado a ele devem ter a mesma assinatura. Este é um exemplo de uma declaração de delegado genérico.  
  
```  
// generics_generic_delegate1.cpp  
// compile with: /clr /c  
generic < class ItemType>  
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);  
```  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra que  
  
-   Você não pode usar o mesmo objeto de representante com diferentes tipos construídos. Crie objetos para diferentes tipos de delegado diferente.  
  
-   Um delegado genérico pode ser associado um método genérico.  
  
-   Quando um método genérico é chamado sem especificar argumentos de tipo, o compilador tenta inferir os argumentos de tipo para a chamada.  
  
```  
// generics_generic_delegate2.cpp  
// compile with: /clr  
generic < class ItemType>  
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);  
  
generic < class ItemType>  
ref struct MyGenClass {  
   ItemType MyMethod(ItemType i, ItemType % j) {  
      return ItemType();  
   }  
};  
  
ref struct MyClass {  
   generic < class ItemType>  
   static ItemType MyStaticMethod(ItemType i, ItemType % j) {  
      return ItemType();  
   }  
};  
  
int main() {  
   MyGenClass<int> ^ myObj1 = gcnew MyGenClass<int>();  
   MyGenClass<double> ^ myObj2 = gcnew MyGenClass<double>();  
   GenDelegate<int>^ myDelegate1 =  
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);  
  
   GenDelegate<double>^ myDelegate2 =   
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);  
  
   GenDelegate<int>^ myDelegate =  
      gcnew GenDelegate<int>(&MyClass::MyStaticMethod<int>);  
}  
```  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir declara um delegate genérico `GenDelegate<ItemType>`e instancia-o ao associá-la para o método `MyMethod` que usa o parâmetro de tipo `ItemType`. Duas instâncias do delegate (um número inteiro e um duplo) são criadas e invocadas.  
  
```  
// generics_generic_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
// declare generic delegate  
generic <typename ItemType>  
delegate ItemType GenDelegate (ItemType p1, ItemType% p2);  
  
// Declare a generic class:  
generic <typename ItemType>  
ref class MyGenClass {  
public:  
   ItemType MyMethod(ItemType p1, ItemType% p2) {  
      p2 = p1;  
      return p1;  
    }  
};  
  
int main() {  
   int i = 0, j = 0;   
   double m = 0.0, n = 0.0;  
  
   MyGenClass<int>^ myObj1 = gcnew MyGenClass<int>();  
   MyGenClass<double>^ myObj2 = gcnew MyGenClass<double>();   
  
   // Instantiate a delegate using int.  
   GenDelegate<int>^ MyDelegate1 =   
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);  
  
   // Invoke the integer delegate using MyMethod.  
   i = MyDelegate1(123, j);  
  
   Console::WriteLine(  
      "Invoking the integer delegate: i = {0}, j = {1}", i, j);  
  
   // Instantiate a delegate using double.  
   GenDelegate<double>^ MyDelegate2 =   
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);  
  
   // Invoke the integer delegate using MyMethod.  
   m = MyDelegate2(0.123, n);  
  
   Console::WriteLine(  
      "Invoking the double delegate: m = {0}, n = {1}", m, n);  
}  
```  
  
```Output  
Invoking the integer delegate: i = 123, j = 123  
Invoking the double delegate: m = 0.123, n = 0.123  
```  
  
## <a name="see-also"></a>Consulte também  
 [Genéricos](../windows/generics-cpp-component-extensions.md)