---
title: Compilador (nível 4) do aviso C4512 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4512
dev_langs:
- C++
helpviewer_keywords:
- C4512
ms.assetid: afb68995-684a-4be5-a73a-38d7a16dc030
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9aee9e7f48430ddc9b2b9a6a7f055ac8b1e32b71
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029943"
---
# <a name="compiler-warning-level-4-c4512"></a>Compilador aviso (nível 4) C4512

"classe": não foi possível gerar um operador de atribuição

O compilador não pode gerar um operador de atribuição para uma determinada classe. Nenhum operador de atribuição foi criado.

O fato de um operador de atribuição para a classe de base não estar acessível pela classe derivada, pode fazer causar esse aviso.

Para evitar esse aviso, especifique um operador de atribuição definido pelo usuário para a classe.

O compilador também gerará uma função de operador de atribuição para uma classe que não define uma. Este operador de atribuição é uma cópia de reconhecimento de membro dos membros de dados de um objeto. Como os itens de dados `const` não podem ser modificados após a inicialização, se a classe tiver um item `const`, o operador de atribuição padrão não funcionará. Outra causa do aviso C4512 é uma declaração de um membro de dados não estático do tipo de referência. Se a intenção é criar um tipo não copiado, você também deve evitar a criação de um construtor de cópia padrão.

Você pode resolver o aviso C4512 para o código de uma destas três maneiras:

- Defina explicitamente um operador de atribuição para a classe.

- Remova **const** ou o operador de referência do item de dados na classe.

- Use o #pragma [aviso](../../preprocessor/warning.md) instrução para suprimir o aviso.

## <a name="example"></a>Exemplo

O seguinte exemplo gera C4512.

```
// C4512.cpp
// compile with: /EHsc /W4
// processor: x86

class Base {
private:
   const int a;

public:
   Base(int val = 0) : a(val) {}
   int get_a() { return a; }
};   // C4512 warning

class Base2 {
private:
   const int a;

public:
   Base2(int val = 0) : a(val) {}
   Base2 & operator=( const Base2 & ) { return *this; }
   int get_a() { return a; }
};

// Type designer intends this to be non-copyable because it has a
// reference member
class Base3
{
private:
   char& cr;

public:
   Base3(char& r) : cr(r) {}
   // Uncomment the following line to explicitly disable copying:
   // Base3(const Base3&) = delete;
};   // C4512 warning

int main() {
   Base first;
   Base second;

   // OK
   Base2 first2;
   Base2 second2;

   char c = 'x';
   Base3 first3(c);
   Base3 second3 = first3; // C2280 if no default copy ctor
}
```