---
title: Ferramentas de vinculador LNK2019 erro | Microsoft Docs
ms.custom: 
ms.date: 05/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2019
dev_langs:
- C++
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
ms.assetid: 4392be92-195c-4eb2-bd4d-49cfac3ca291
caps.latest.revision: 39
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4cb4413b8c0b53b407724dd16083027b89b91b37
ms.contentlocale: pt-br
ms.lasthandoff: 10/09/2017

---
# <a name="linker-tools-error-lnk2019"></a>Erro das Ferramentas de Vinculador LNK2019
símbolo externo não resolvido '*símbolo*'referenciado na função'*função*'  
  
O código compilado para *função* faz uma referência ou uma chamada para *símbolo*, mas esse símbolo não está definido em qualquer uma das bibliotecas ou arquivos de objeto especificados para o vinculador.  
  
Essa mensagem de erro é seguida por erro fatal [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md). Você deve corrigir todos os LNK2001 e LNK2019 erros para corrigir o erro LNK1120.  
  
## <a name="possible-causes"></a>Causas possíveis  
  
Há muitas maneiras de obter esse erro, mas todos eles envolvem uma referência a uma função ou variável que não é possível o vinculador *resolver*, ou localizar uma definição para. O compilador pode identificar quando um símbolo não é *declarado*, mas não quando ele não está *definido*, porque a definição pode estar em um arquivo de origem diferente ou na biblioteca. Se um símbolo é chamado, mas nunca é definido, o vinculador gerará um erro de símbolo externo não resolvido.  
  
Aqui estão alguns problemas comuns que causam LNK2019:  
  
-   **O arquivo de objeto ou a biblioteca que contém a definição do símbolo não está vinculada.** No Visual Studio, verifique se que o arquivo de origem que contém a definição é compilado e vinculado como parte do seu projeto. Na linha de comando, verifique se que o arquivo de origem que contém a definição é compilado, e que o arquivo de objeto resultante é incluído na lista de arquivos para vincular.  
  
-   **A declaração do símbolo não foi digitada o mesmo que a definição do símbolo.** Verificar a ortografia e a capitalização é usada na declaração e a definição, e sempre que o símbolo é usado ou chamado.  
  
-   **Uma função é usada, mas o tipo ou o número de parâmetros não correspondem a definição da função.** A declaração da função deve corresponder a definição. Verifique se a chamada de função corresponde a declaração e a declaração corresponde a definição. Código que chama as funções de modelo também deve ter declarações de função de modelo que incluem os mesmos parâmetros de modelo como a definição de correspondência. Para obter um exemplo de uma incompatibilidade da declaração de modelo, consulte o exemplo LNK2019e.cpp na seção de exemplos.  
  
-   **Uma função ou variável é declarada, mas não definido.** Isso geralmente significa que existe uma declaração em um arquivo de cabeçalho, mas nenhuma definição correspondente é implementada. Para funções de membro ou membros de dados estáticos, a implementação deve incluir o seletor de escopo de classe. Para obter um exemplo, consulte [corpo ausente da função ou variável](../../error-messages/tool-errors/missing-function-body-or-variable.md).  
  
-   **A convenção de chamada for diferente entre a declaração da função e a definição da função.** Convenções de chamada ([cdecl](../../cpp/cdecl.md), [stdcall](../../cpp/stdcall.md), [fastcall](../../cpp/fastcall.md), ou [vectorcall](../../cpp/vectorcall.md)) são codificados como parte do nome decorado. Verifique se a convenção de chamada é o mesmo.  
  
-   **Um símbolo é definido em um arquivo C, mas declarado sem usando extern "C" em um arquivo C++.** Símbolos definidos em um arquivo que é compilado como C tem diferentes nomes decorados de símbolos declarados em um arquivo C++, a menos que você use um [extern "C"](../../cpp/using-extern-to-specify-linkage.md) modificador. Verifique se a declaração corresponde a ligação de compilação para cada símbolo. Da mesma forma, se você definir um símbolo em um arquivo de C++ que será usado por um programa em C, use `extern "C"` na definição.  
  
-   **Um símbolo é definido como estático e posteriormente referenciado fora do arquivo.** No C++, ao contrário de C, [constantes globais](../../error-messages/tool-errors/global-constants-in-cpp.md) ter `static` vinculação. Para contornar essa limitação, você pode incluir o `const` inicializações em um cabeçalho de arquivo e incluem esse cabeçalho nos arquivos. cpp, ou você pode fazer a variável não constante e usar uma referência constante para acessá-lo.  
  
-   **Um membro estático de uma classe não está definido.** Um membro de classe estática deve ter uma definição exclusiva ou violar a regra de definição de um. Um membro de classe estática que não pode ser definido em linha deve ser definido em um arquivo de origem usando seu nome totalmente qualificado. Se ele não está definido em todos os, o vinculador gerará LNK2019.  
  
-   **Uma dependência de compilação é definida somente como uma dependência de projeto na solução.** Em versões anteriores do Visual Studio, esse nível de dependência foi suficiente. No entanto, começando com o Visual Studio 2010, o Visual Studio requer um [referência projeto a projeto](/visualstudio/ide/managing-references-in-a-project). Se seu projeto não tem uma referência de projeto a projeto, você receberá esse erro vinculador. Adicione uma referência de projeto a projeto para corrigi-lo.  
  
-   **Criar um aplicativo de console usando as configurações para um aplicativo do Windows**. Se a mensagem de erro é semelhante a **símbolo externo não resolvido WinMain referenciado na função**`function_name`, link usando **/SUBSYSTEM** em vez de **/Subsystem: Windows** . Para obter mais informações sobre essa configuração e para obter instruções sobre como definir essa propriedade no Visual Studio, consulte [/SUBSYSTEM (especificar subsistema)](../../build/reference/subsystem-specify-subsystem.md).  
  
-   **Você pode usar opções de compilador diferentes para a função inlining nos arquivos de origem diferente.** Usando funções embutidas definidas em arquivos. cpp e combinação de opções do compilador inlining função nos arquivos de origem diferentes pode causar LNK2019. Para obter mais informações, consulte [problemas de Inlining da função](../../error-messages/tool-errors/function-inlining-problems.md).  
  
-   **Você pode usar variáveis automáticas fora de seu escopo.** Variáveis automáticas (escopo da função) podem ser usados somente no escopo da função. Essas variáveis não podem ser declaradas `extern` e usado em outros arquivos de origem. Para obter um exemplo, consulte [variáveis de automáticas (escopo da função)](../../error-messages/tool-errors/automatic-function-scope-variables.md).  
  
-   **Chamar funções instrinsic ou passar tipos de argumento para funções intrínsecas que não têm suporte em sua arquitetura de destino.** Por exemplo, se você usar um AVX2 intrínseco, mas não especificar o [/arch: avx2](../../build/reference/arch-x86.md) opção de compilador, o compilador assumirá que o intrínseco é uma função externa. Em vez de gerar uma instrução embutido, o compilador gera uma chamada para um símbolo externo com o mesmo nome como intrínseca. Quando o vinculador tenta localizar a definição dessa função ausente, ele gera LNK2019. Verifique se que você use somente intrínsecos e tipos com suporte por sua arquitetura de destino.  
  
-   **Combinar o código que usa native wchar\_t com código não.** Trabalho de conformidade de linguagem C++ que foi feito no Visual C++ 2005 feitas `wchar_t` um tipo nativo por padrão. Você deve usar o [/Zc:wchar_t-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) opção de compilador ao gerar código compatível com os arquivos de biblioteca e objeto compilados usando versões anteriores do Visual C++. Se nem todos os arquivos foram compilados usando o mesmo **/Zc:wchar\_t** configurações, tipo de referências não podem ser resolvidos em tipos compatíveis. Verifique `wchar_t` tipos em todos os arquivos de biblioteca e objeto são compatíveis, atualizando os tipos que são usados ou usando consistente **/ZC:** configurações ao compilar.  
  
## <a name="diagnosis-tools"></a>Ferramentas de diagnóstico    
  
Pode ser difícil saber por que o vinculador não é possível encontrar uma definição de símbolo específico. Geralmente, o problema é que não incluir o código que contém a definição na criação ou criaram diferentes opções de compilação decorado nomes de símbolos externos. Há várias ferramentas e opções que podem ajudá-lo a diagnosticar um erro de LNK2019.  
  
-   O [/verbose](../../build/reference/verbose-print-progress-messages.md) opção de vinculador pode ajudá-lo a determinar quais arquivos as vinculador de referências. Isso pode ajudá-lo a verificar se o arquivo que contém a definição do símbolo está incluído em sua compilação.  
  
-   O [/EXPORTA](../../build/reference/dash-exports.md) e [/símbolos](../../build/reference/symbols.md) opções do utilitário DUMPBIN podem ajudá-lo a descobrir quais símbolos são definidos nos arquivos. dll e o objeto ou a biblioteca. Verifique se que o exportado decorado correspondência de nomes que de decorado nomeia o vinculador procura.  
  
-   O utilitário UNDNAME pode mostrar o símbolo externo não decorado equivalente para um nome decorado.  
## <a name="examples"></a>Exemplos  
  
Aqui estão alguns exemplos de código que causa um erro LNK2019, junto com informações sobre como corrigir o erro.  
  
### <a name="a-symbol-is-declared-but-not-defined"></a>Um símbolo é declarado mas não definido  
  
Neste exemplo, uma variável externa é declarada mas não definida:  
  
```cpp  
// LNK2019.cpp  
// Compile by using: cl /EHsc /W4 LNK2019.cpp  
// LNK2019 expected  
extern char B[100];   // B is not available to the linker  
int main() {  
   B[0] = ' ';   // LNK2019  
}  
```  
  
Aqui está outro exemplo onde uma variável e a função são declarados como `extern` , mas é fornecida nenhuma definição:  
  
```cpp  
// LNK2019c.cpp  
// Compile by using: cl /EHsc LNK2019c.cpp  
// LNK2019 expected  
extern int i;  
extern void g();  
void f() {  
   i++;  
   g();  
}  
int main() {}  
```  
  
A menos que `i` e `g` são definidos em um dos arquivos incluídos na compilação, o vinculador gere LNK2019. Você pode corrigir os erros, incluindo o arquivo de código fonte que contém as definições como parte da compilação. Como alternativa, você pode passar os arquivos. obj ou. lib que contêm as definições para o vinculador.  
  
### <a name="a-static-data-member-is-declared-but-not-defined"></a>Um membro de dados estático está declarado mas não definido  
  
LNK2019 também pode ocorrer quando um membro de dados estático está declarado mas não definido. O exemplo a seguir gera LNK2019 e mostra como corrigi-lo.  
  
```cpp  
// LNK2019b.cpp  
// Compile by using: cl /EHsc LNK2019b.cpp  
// LNK2019 expected  
struct C {  
   static int s;  
};  
  
// Uncomment the following line to fix the error.  
// int C::s;  
  
int main() {  
   C c;  
   C::s = 1;  
}  
```  
  
### <a name="declaration-parameters-do-not-match-definition"></a>Parâmetros de declaração não coincidem definição  
  
Código que chama as funções de modelo deve ter a correspondência de declarações de função do modelo. Declarações devem incluir os mesmos parâmetros de modelo como a definição. O exemplo a seguir gera LNK2019 em um operador definido pelo usuário e mostra como corrigi-lo.  
  
```cpp  
// LNK2019e.cpp  
// compile by using: cl /EHsc LNK2019e.cpp  
// LNK2019 expected  
#include <iostream>  
using namespace std;  
  
template<class T> class   
Test {  
   // The operator<< declaration does not match the definition below:  
   friend ostream& operator<<(ostream&, Test&);  
   // To fix, replace the line above with the following:  
   // template<typename T> friend ostream& operator<<(ostream&, Test<T>&);  
};  
  
template<typename T>  
ostream& operator<<(ostream& os, Test<T>& tt) {  
   return os;  
}  
  
int main() {  
   Test<int> t;  
   cout << "Test: " << t << endl;   // LNK2019 unresolved external  
}  
```  
  
### <a name="inconsistent-wchart-type-definitions"></a>Definições de tipo wchar_t inconsistente  
  
Este exemplo cria uma DLL que tenha uma exportação que usa `WCHAR`, que resolve para `wchar_t`.  
  
```cpp  
// LNK2019g.cpp  
// compile with: cl /EHsc /LD LNK2019g.cpp  
#include "windows.h"  
// WCHAR resolves to wchar_t  
__declspec(dllexport) void func(WCHAR*) {}  
```  
  
O próximo exemplo usa a DLL no exemplo anterior e gera LNK2019 porque os tipos não assinados curto * e WCHAR\* não são iguais.  
  
```cpp  
// LNK2019h.cpp  
// compile by using: cl /EHsc LNK2019h LNK2019g.lib  
// LNK2019 expected  
__declspec(dllimport) void func(unsigned short*);  
  
int main() {  
   func(0);  
}  
```  
  
 Para corrigir esse erro, altere `unsigned short` para `wchar_t` ou `WCHAR`, ou compile LNK2019g.cpp usando **/Zc:wchar_t-**.  
  
## <a name="additional-resources"></a>Recursos adicionais  
  
Para obter mais informações sobre possíveis causas e soluções LNK2001, consulte a pergunta de estouro de pilha [o que é um erro de símbolo externo indefinido referência/não resolvidos e como corrigi-lo?](http://stackoverflow.com/q/12573816/2002113).  

