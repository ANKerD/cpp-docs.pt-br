---
title: Cadeia de caracteres e literais de caracteres (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- R
dev_langs:
- C++
helpviewer_keywords:
- L constant
- escape sequences
- Null strings, null-terminated strings
- literal strings, C++
- Null strings
- string literals, syntax
- string literals
- literal strings
- strings [C++], string literals
- NULL, character constant
- wide characters, strings
ms.assetid: 61de8f6f-2714-4e7b-86b6-a3f885d3b9df
caps.latest.revision: 36
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: c7254d4cc8dcbbaa0916a77ee6c52da05dc8ec9c
ms.contentlocale: pt-br
ms.lasthandoff: 09/25/2017

---
# <a name="string-and-character-literals--c"></a>Cadeia de caracteres e literais de caracteres (C++)
C++ dá suporte a vários tipos de cadeia de caracteres e caracteres e fornece modos para expressar valores literais de cada um desses tipos. No seu código-fonte, você expressar o conteúdo de seu literais de caracteres e cadeia de caracteres usando um conjunto de caracteres. Nomes de caractere universal e caracteres de escape permitem expressar qualquer cadeia de caracteres usando apenas o conjunto de caracteres de origem básico. Um literal de cadeia bruto permite que você evite usar caracteres de escape e pode ser usado para expressar todos os tipos de literais de cadeia de caracteres. Você também pode criar literais std::string sem ter que executar etapas de conversão ou construção extra.  
  
```cpp  
#include <string>  
using namespace std::string_literals; // enables s-suffix for std::string literals  
  
int main()  
{  
    // Character literals  
    auto c0 =   'A'; // char  
    auto c1 = u8'A'; // char  
    auto c2 =  L'A'; // wchar_t  
    auto c3 =  u'A'; // char16_t  
    auto c4 =  U'A'; // char32_t  
  
    // String literals  
    auto s0 =   "hello"; // const char*  
    auto s1 = u8"hello"; // const char*, encoded as UTF-8  
    auto s2 =  L"hello"; // const wchar_t*  
    auto s3 =  u"hello"; // const char16_t*, encoded as UTF-16  
    auto s4 =  U"hello"; // const char32_t*, encoded as UTF-32  
  
    // Raw string literals containing unescaped \ and "  
    auto R0 =   R"("Hello \ world")"; // const char*  
    auto R1 = u8R"("Hello \ world")"; // const char*, encoded as UTF-8  
    auto R2 =  LR"("Hello \ world")"; // const wchar_t*  
    auto R3 =  uR"("Hello \ world")"; // const char16_t*, encoded as UTF-16  
    auto R4 =  UR"("Hello \ world")"; // const char32_t*, encoded as UTF-32  
  
    // Combining string literals with standard s-suffix  
    auto S0 =   "hello"s; // std::string  
    auto S1 = u8"hello"s; // std::string  
    auto S2 =  L"hello"s; // std::wstring  
    auto S3 =  u"hello"s; // std::u16string  
    auto S4 =  U"hello"s; // std::u32string  
  
    // Combining raw string literals with standard s-suffix  
    auto S5 =   R"("Hello \ world")"s; // std::string from a raw const char*  
    auto S6 = u8R"("Hello \ world")"s; // std::string from a raw const char*, encoded as UTF-8  
    auto S7 =  LR"("Hello \ world")"s; // std::wstring from a raw const wchar_t*  
    auto S8 =  uR"("Hello \ world")"s; // std::u16string from a raw const char16_t*, encoded as UTF-16  
    auto S9 =  UR"("Hello \ world")"s; // std::u32string from a raw const char32_t*, encoded as UTF-32  
}  
```  
  
 Literais de cadeia de caracteres não podem ter nenhum prefixo, ou `u8`, `L`, `u`, e `U` prefixos para denotar restringir caractere (byte único ou vários byte), caracteres UTF-8, ampla (UCS-2 ou UTF-16), UTF-16 e UTF-32 codificações, respectivamente. Um literal de cadeia bruto pode ter `R`, `u8R`, `LR`, `uR` e `UR` prefixos para os equivalentes de versão bruto essas codificações.  Para criar valores std::string temporário ou estática, você pode usar literais de cadeia de caracteres ou literais de cadeia de caracteres com um `s` sufixo. Para obter mais informações, consulte a seção de literais de cadeia de caracteres abaixo. Para obter mais informações sobre o caractere de origem básico definir nomes de caractere universal e usar caracteres de páginas de código estendidas em seu código-fonte, consulte [conjuntos de caracteres](../cpp/character-sets2.md).  
  
## <a name="character-literals"></a>Literais de caracteres  
 Um *literal de caractere* é composto de um caractere de constante. Ele é representado pelo caractere entre aspas simples. Há cinco tipos de literais de caracteres:  
  
-   Literais de caracteres comum do tipo `char`, por exemplo`'a'`  
  
-   Literais de caracteres UTF-8 do tipo `char`, por exemplo`u8'a'`  
  
-   Literais de caractere largo do tipo `wchar_t`, por exemplo `L'a'`  
  
-   Literais de caracteres UTF-16 do tipo `char16_t`, por exemplo`u'a'`  
  
-   Literais de caracteres UTF-32 do tipo `char32_t`, por exemplo`U'a'`  
  
 O caractere usado para um literal de caractere pode ser qualquer caractere, exceto caracteres reservados uma barra invertida ('\\'), aspas simples (') ou nova linha. Caracteres reservados podem ser especificados usando uma sequência de escape. Caracteres podem ser especificados usando nomes de caractere universal, desde que o tipo é grande o suficiente para conter o caractere.  
  
### <a name="encoding"></a>Codificando  
 Literais de caracteres são codificados de forma diferente com base em seu prefixo.  
  
-   Um caractere literal sem um prefixo é um literal de caractere comum. Sequência de escape que contém um único caractere, o valor de um literal de caractere comum ou nome de caractere universal que pode ser representado no conjunto de caracteres de execução tem um valor igual ao valor numérico de sua codificação no conjunto de caracteres de execução. Um literal de caractere simples que contém mais de um caractere, a sequência de escape ou o nome do caractere universal é uma *literal de caractere múltiplo*. Múltiplos literal ou um literal de caractere comum que não pode ser representado no conjunto de caracteres de execução é condicionalmente com suporte, tem tipo int e seu valor é definido pela implementação.  
  
-   Um literal de caractere que começa com o prefixo L é um literal de caractere largo. O valor de um literal de caractere largo contendo um único caractere, a sequência de escape ou o nome do caractere universal tem um valor igual ao valor numérico de sua codificação em execução wide-conjunto de caracteres, a menos que o literal de caractere não tem representação do conjunto de caracteres de toda a execução, no caso, o valor é definido pela implementação. O valor de um literal de caractere largo que contém vários caracteres, sequências de escape ou nomes de caractere universal é definido pela implementação.  
  
-   Um literal de caractere que começa com o prefixo u8 é um literal de caractere UTF-8. Sequência de escape que contém um único caractere, o valor de um literal de caractere UTF-8 ou o nome do caractere universal tem um valor igual a seu valor de ponto de código ISO 10646 se ele pode ser representado por uma única unidade de código UTF-8 (correspondente aos controles C0 e Latim básico Bloco de Unicode). Se o valor não pode ser representado por uma única unidade de código UTF-8, o programa está mal formado. Um literal que contém mais de um caractere, sequência de escape ou nome de caractere universal de caracteres UTF-8 está mal formado.  
  
-   Um literal de caractere que começa com o prefixo de u é um literal de caractere UTF-16. Sequência de escape que contém um único caractere, o valor de um literal de caractere UTF-16 ou o nome do caractere universal tem um valor igual a seu valor de ponto de código ISO 10646 se ele pode ser representado por uma única unidade de código UTF-16 (correspondente do plano multilíngue básico ). Se o valor não pode ser representado por uma única unidade de código UTF-16, o programa está mal formado. Um literal que contém mais de um caractere, sequência de escape ou nome de caractere universal de caractere UTF-16 está mal formado.  
  
-   Um literal de caractere que começa com o prefixo de U é um literal de caractere UTF-32. Sequência de escape que contém um único caractere, o valor de um literal de caractere UTF-32 ou nome de caractere universal tem um valor igual a seu valor de ponto de código ISO 10646. Um literal que contém mais de um caractere, sequência de escape ou nome de caractere universal de caracteres UTF-8 está mal formado.  
  
###  <a name="bkmk_Escape"></a>Sequências de escape  
 Há três tipos de sequências de escape: simples, octa e hexadecimal. As sequências de escape podem ser qualquer uma das seguintes:  
  
|Valor|Sequência de escape|Valor|Sequência de escape|  
|-----------|---------------------|-----------|---------------------|  
|nova linha|\n|barra invertida|\\\|  
|tabulação horizontal|\t|ponto de interrogação|? ou \\?|  
|tabulação vertical|\v|aspas simples|\\'|  
|backspace|\b|aspas duplas|\\"|  
|retorno de carro|\r|o caractere nulo|\0|  
|avanço de página|\f|octal|\ooo|  
|alerta (sino)|\a|hexadecimal|\xhhh|  
  
 O código a seguir mostra alguns exemplos de caracteres de escape usando literais de caracteres comum. A mesma sintaxe de sequência de escape é válida para os outros tipos de literal de caractere.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main() {  
    char newline = '\n';  
    char tab = '\t';  
    char backspace = '\b';  
    char backslash = '\\';  
    char nullChar = '\0';  
  
    cout << "Newline character: " << newline << "ending" << endl; // Newline character:  
                                                                  //  ending  
    cout << "Tab character: " << tab << "ending" << endl; // Tab character : ending  
    cout << "Backspace character: " << backspace << "ending" << endl; // Backspace character : ending  
    cout << "Backslash character: " << backslash << "ending" << endl; // Backslash character : \ending  
    cout << "Null character: " << nullChar << "ending" << endl; //Null character:  ending  
}  
```  
  
 **Seção específica da Microsoft**  
  
 Para criar um valor de um literal de caractere comum (aqueles sem um prefixo), o compilador converte o caractere ou cadeia de caracteres entre aspas em valores de 8 bits em um inteiro de 32 bits. Vários caracteres no literal preenchem bytes correspondentes, conforme o necessário de ordem superior para inferior. Para criar um `char` valor, o compilador usa o byte de ordem inferior. Para criar um `wchar_t` ou `char16_t` valor, o compilador usa a palavra de ordem inferior. O compilador avisa que o resultado será truncado se qualquer bits são definidos acima do byte atribuído ou word.  
  
```cpp  
char c0    = 'abcd';    // C4305, C4309, truncates to 'd'  
wchar_t w0 = 'abcd';    // C4305, C4309, truncates to '\x6364'  
```  
  
 Uma sequência de escape octal é uma barra invertida seguida por uma sequência de até 3 dígitos octais. O comportamento de uma sequência de escape octal parece conter mais de três dígitos é tratado como uma sequência de 3 dígitos octal seguida os dígitos subsequentes como caracteres. Isso pode dar resultados surpreendentes. Por exemplo:  
  
```cpp  
char c1 = '\100';   // '@'  
char c2 = '\1000';  // C4305, C4309, truncates to '0'   
```  
  
 Sequências de escape que parecem conter caracteres não octais são avaliadas como uma cadeia de caracteres octal até o último caractere octal, seguido dos caracteres restantes. Por exemplo:  
  
```cpp  
char c3 = '\009';   // '9'  
char c4 = '\089';   // C4305, C4309, truncates to '9'  
char c5 = '\qrs';   // C4129, C4305, C4309, truncates to 's'  
```  
  
 Uma sequência de escape hexadecimal é uma barra invertida, seguida pelo caractere `x`, seguido por uma sequência de dígitos hexadecimais. Uma sequência de escape que contém os dígitos não hexadecimais faz com que o erro do compilador C2153: "literais hexadecimais devem ter pelo menos um dígito hexadecimal". Zeros à esquerda são ignorados. Uma sequência de escape que parece ter caracteres hexadecimal e não hexadecimal é avaliada como uma sequência de escape hexadecimal até o último caractere hexadecimal, seguido pelos caracteres não hexadecimal.   Um caractere comum ou prefixo u8 literal, o maior valor hexadecimal é 0xFF. Um prefixo L ou prefixo u literal de caractere largo, o maior valor hexadecimal é 0xFFFF. Em um prefixo U literal de caractere largo, o maior valor hexadecimal é 0xFFFFFFFF.  
  
```cpp  
char c6 = '\x0050'; // 'P'  
char c7 = '\x0pqr'; // C4305, C4309, truncates to 'r'  
```  
  
 Se um literal de caractere largo prefixado com `L` contém mais de um caractere, o valor é obtido a partir do primeiro caractere. Os caracteres subsequentes são ignorados, ao contrário do comportamento do literal de caractere comum equivalente.  
  
```cpp  
wchar_t w1 = L'\100';   // L'@'  
wchar_t w2 = L'\1000';  // C4066 L'@', 0 ignored   
wchar_t w3 = L'\009';   // C4066 L'\0', 9 ignored  
wchar_t w4 = L'\089';   // C4066 L'\0', 89 ignored  
wchar_t w5 = L'\qrs';   // C4129, C4066 L'q' escape, rs ignored  
wchar_t w6 = L'\x0050'; // L'P'  
wchar_t w7 = L'\x0pqr'; // C4066 L'\0', pqr ignored  
```  
  
 **Fim da seção específica da Microsoft**  
  
 O caractere de barra invertida (\\) é um caractere de continuação de linha quando ele é colocado no final de uma linha. Se desejar que um caractere de barra invertida seja exibido como uma literal de caractere, você deve digitar duas barras invertidas em uma linha (`\\`). Para obter mais informações sobre o caractere de continuação de linha, consulte [fases de tradução](../preprocessor/phases-of-translation.md).  
  
###  <a name="bkmk_UCN"></a>Nomes de caractere universais  
 Em literais de caracteres e literais de cadeia de caracteres nativo (não processados), qualquer caractere pode ser representado por um nome de caractere universal.  Nomes de caractere universal são formados por um prefixo que \u seguido por um ponto de código Unicode oito dígitos, ou por um \u prefixo seguido por um ponto de código Unicode de quatro dígitos. Todos os quatro ou oito dígitos, respectivamente, devem estar presentes para tornar um nome de caractere universal bem formado.  
  
```cpp  
char u1 = 'A';          // 'A'  
char u2 = '\101';       // octal, 'A'   
char u3 = '\x41';       // hexadecimal, 'A'  
char u4 = '\u0041';     // \u UCN 'A'  
char u5 = '\U00000041'; // \U UCN 'A'  
```  
  
 **Pares substitutos**  
  
 Nomes de caractere universal não é possível codificar valores no intervalo de ponto de código substituto DFFF D800. Para pares substitutos de Unicode, especifique o nome de caractere universal usando `\UNNNNNNNN`, onde NNNNNNNN é o ponto de código de oito dígitos do caractere. O compilador gera um par alternativo, se necessário.  
  
 Em C + + 03, a linguagem somente permitido um subconjunto de caracteres a ser representado por seus nomes de caractere universal e permitidos alguns nomes de caractere universal que realmente não representam caracteres Unicode válidos. Isso foi corrigido no C++ 11 padrão. No C++ 11, identificadores e literais de caracteres e cadeia de caracteres podem usar nomes de caractere universal.  Para obter mais informações sobre nomes de caractere universal, consulte [conjuntos de caracteres](../cpp/character-sets2.md). Para obter mais informações sobre Unicode, consulte [Unicode](http://msdn.microsoft.com/library/dd374081\(v=vs.85\).aspx). Para obter mais informações sobre pares substitutos, consulte [pares substitutos e caracteres suplementares](http://msdn.microsoft.com/library/dd374069\(v=vs.85\).aspx).  
  
## <a name="string-literals"></a>Literais de cadeia de caracteres  
 Uma literal de cadeia de caracteres representa uma sequência de caracteres que, juntos, formam uma cadeia de caracteres terminada em nulo. Os caracteres devem ser incluídos entre aspas duplas. Existem os seguintes tipos de literais de cadeias de caracteres:  
  
### <a name="narrow-string-literals"></a>Literais de cadeia de caracteres estreita  
 Uma cadeia de caracteres estreita literal é uma matriz de delimitado com terminação nula, sem prefixo, aspas duplas de tipo `const char[n]`, onde n é o comprimento da matriz de bytes. Um literal de cadeia específica pode conter qualquer caractere gráfico, exceto as aspas duplas (`"`), barra invertida (`\`), ou caractere de nova linha. Uma cadeia de caracteres estreita literal também pode conter os nomes de caractere listados acima e universais de sequências de escape que cabem em um byte.  
  
```cpp  
const char *narrow = "abcd";  
  
// represents the string: yes\no  
const char *escaped = "yes\\no";  
```  
  
#### <a name="utf-8-encoded-strings"></a>Cadeias de caracteres codificados em UTF-8  
  
 Uma cadeia de caracteres codificada em UTF-8 é uma matriz de delimitado terminada em nulo, prefixado u8, aspas duplas de tipo `const char[n]`, onde n é o comprimento da matriz codificado em bytes. Um literal de cadeia prefixados u8 pode conter qualquer caractere gráfico, exceto as aspas duplas (`"`), barra invertida (`\`), ou caractere de nova linha. Um literal de cadeia u8 prefixo também pode conter o escape sequências listadas acima e qualquer nome de caractere universal.  
  
```cpp  
const char* str1 = u8"Hello World";  
const char* str2 = u8"\U0001F607 is O:-)";  
```  
  
### <a name="wide-string-literals"></a>Literais de cadeia de caracteres larga  
 Uma cadeia de caracteres larga literal é uma matriz com terminação nula de constante `wchar_t` que é prefixado por '`L`' e contém qualquer caractere gráfico, exceto as aspas duplas ("), barra invertida (\\), ou caractere de nova linha. Uma cadeia de caracteres larga literal pode conter o escape sequências listadas acima e qualquer nome de caractere universal.  
  
```cpp  
const wchar_t* wide = L"zyxw";  
const wchar_t* newline = L"hello\ngoodbye";  
```  
  
#### <a name="char16t-and-char32t-c11"></a>char16_t e char32_t (C++ 11)  
  
 C++ 11 apresenta o portátil `char16_t` (Unicode de 16 bits) e `char32_t` (Unicode de 32 bits) tipos de caracteres:  
  
```cpp  
auto s3 = u"hello"; // const char16_t*  
auto s4 = U"hello"; // const char32_t*  
```  
  
### <a name="raw-string-literals-c11"></a>Literais de cadeia de caracteres bruta (C++ 11)  
 Um literal de cadeia bruto é uma matriz de terminação nula — de qualquer tipo de caractere, que contém qualquer caractere gráfico, incluindo as aspas duplas ("), barra invertida (\\), ou caractere de nova linha. As literais de cadeias de caracteres brutas costumam ser usadas em expressões regulares que utilizam classes de caracteres, bem como em cadeias de caracteres HTML e XML. Para obter exemplos, consulte o seguinte artigo: [perguntas frequentes sobre de Bjarne Stroustrup em C++ 11](http://go.microsoft.com/fwlink/?LinkId=401172).  
  
```cpp  
// represents the string: An unescaped \ character  
const char* raw_narrow = R"(An unescaped \ character)";  
const wchar_t* raw_wide = LR"(An unescaped \ character)";  
const char*       raw_utf8  = u8R"(An unescaped \ character)";  
const char16_t* raw_utf16 = uR"(An unescaped \ character)";  
const char32_t* raw_utf32 = UR"(An unescaped \ character)";  
```  
  
 Um delimitador é uma sequência definida pelo usuário, com até 16 caracteres, que vem imediatamente antes do parêntese de abertura e imediatamente depois do parêntese de fechamento de uma literal de cadeia de caracteres bruta.  Por exemplo, em `R"abc(Hello"\()abc"` a sequência de delimitador é `abc` e o conteúdo de cadeia de caracteres é `Hello"\(`. Você pode usar um delimitador para resolver a ambiguidade brutas cadeias de caracteres que contêm aspas duplas e parênteses. Isso causa um erro do compilador:  
  
```cpp  
// meant to represent the string: )"  
const char* bad_parens = R"()")";  // error C2059  
```  
  
 Mas um delimitador resolve essa sintaxe:  
  
```cpp  
const char* good_parens = R"xyz()")xyz";  
```  
  
 Você pode construir uma literal de cadeia de caracteres bruta em que há uma nova linha (não o caractere de escape) na origem:  
  
```cpp  
// represents the string: hello  
//goodbye  
const wchar_t* newline = LR"(hello  
goodbye)";  
```  
  
### <a name="stdstring-literals-c14"></a>std::string literais (C + + 14)  
 std::string literais são as implementações de biblioteca padrão de definida pelo usuário literais (veja abaixo) que são representados como "xyx" s (com um `s` sufixo). Esse tipo de cadeia de caracteres literal produz um objeto temporário de tipo std::string, std:: wstring, std::u32string ou std::u16string dependendo o prefixo especificado. Quando nenhum prefixo é usado, como acima, uma std::string é produzida. L "xyz" s produz um std:: wstring. u "xyz" s produz um [std::u16string](../standard-library/string-typedefs.md#u16string)e "xyz" U s produz um [std::u32string](../standard-library/string-typedefs.md#u32string).  
  
```cpp  
//#include <string>  
//using namespace std::string_literals;  
string str{ "hello"s };  
string str2{ u8"Hello World" };  
wstring str3{ L"hello"s };  
u16string str4{ u"hello"s };  
u32string str5{ U"hello"s };  
```  
  
 O sufixo s também pode ser usado em literais de cadeia de caracteres bruta:  
  
```cpp  
u32string str6{ UR"(She said "hello.")"s };  
```  
  
 std::string literais são definidos no namespace `std::literals::string_literals` no \<cadeia de caracteres > arquivo de cabeçalho. Porque `std::literals::string_literals`, e `std::literals` são declaradas como [embutido namespaces](../cpp/namespaces-cpp.md), `std::literals::string_literals` automaticamente é tratado como se ele pertencia diretamente no namespace `std`.  
  
### <a name="size-of-string-literals"></a>Tamanho das literais de cadeias de caracteres  
 Para caractere ANSI\* cadeias de caracteres e outras codificações de byte único (não UTF-8), o tamanho (em bytes) de um literal de cadeia de caracteres é o número de caracteres mais 1 para o caractere null de terminação. Para todos os outros tipos de cadeia de caracteres, o tamanho não é estritamente relacionado ao número de caracteres. UTF-8 usa até quatro elementos de char para codificar alguns *código unidades*e char16_t ou wchar_t codificado como UTF-16 pode usar dois elementos (para um total de quatro bytes) para codificar um único *unidade de código*.   Este exemplo mostra o tamanho de uma cadeia de caracteres largo literal em bytes:  
  
```cpp  
const wchar_t* str = L"Hello!";  
const size_t byteSize = (wcslen(str) + 1) * sizeof(wchar_t);  
```  
  
 Observe que `strlen()` e `wcslen()` não incluem o tamanho do caractere null de terminação, cujo tamanho é igual ao tamanho do elemento do tipo cadeia de caracteres: um byte em uma cadeia de caracteres *, dois bytes em wchar_t\* ou char16_t\* cadeias de caracteres e quatro bytes em char32_t\* cadeias de caracteres.  
  
 O comprimento máximo de uma literal de cadeia de caracteres é de 65535 bytes. Esse limite se aplica às literais de cadeias de caracteres estreitas e largas.  
  
### <a name="modifying-string-literals"></a>Modificando literais de cadeias de caracteres  
 Como literais de cadeia de caracteres (não incluindo literais std:string) são constantes, tentar modificá-los — por exemplo, str [2] = 'A' — causará um erro do compilador.  
  
 **Seção específica da Microsoft**  
  
 No Visual C++, você pode usar uma literal de cadeia de caracteres para inicializar um ponteiro para a não constante `char` ou `wchar_t`. Isso é permitido no código de C99, mas está preterido no C + + 98 e removido do C++ 11. Uma tentativa de modificar a cadeia de caracteres causa uma violação de acesso, como neste exemplo:  
  
```cpp  
wchar_t* str = L"hello";  
str[2] = L'a'; // run-time error: access violation  
```  
  
 Você pode causar o compilador emite um erro quando uma literal de cadeia de caracteres é convertida em um ponteiro de caractere non_const quando você definir o [/ZC: strictstrings (desativar conversão de tipo literal de cadeia de caracteres)](../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) opção de compilador. É recomendável para código portátil compatível com os padrões. Também é uma prática recomendada usar o `auto` palavra-chave para declarar cadeia de caracteres literal inicializada ponteiros, porque ele resolve para o tipo correto (const). Por exemplo, este exemplo de código captura uma tentativa de gravar uma cadeia de caracteres literal em tempo de compilação:  
  
```cpp  
auto str = L"hello";  
str[2] = L'a'; // C3892: you cannot assign to a variable that is const.  
```  
  
 Em alguns casos, literais de cadeias de caracteres idênticas podem ser agrupadas para economizar espaço no arquivo executável. Em pools de literais de cadeias de caracteres, o compilador faz com que todas as referências a uma literal de cadeia de caracteres específica apontem para o mesmo local na memória, em vez de cada referência apontar para uma instância separada da literal. Para habilitar o pool de cadeia de caracteres, use o [/GF](../build/reference/gf-eliminate-duplicate-strings.md) opção de compilador.  
  
 **Fim da seção específica da Microsoft**  
  
### <a name="concatenating-adjacent-string-literals"></a>Concatenando literais de cadeias de caracteres adjacentes  
 Literais de cadeia de caracteres larga ou estreita adjacentes são concatenados. Esta declaração:  
  
```cpp  
char str[] = "12" "34";  
```  
  
 é idêntica a esta declaração:  
  
```cpp  
char atr[] = "1234";  
```  
  
 e a esta declaração:  
  
```cpp  
char atr[] =  "12\  
34";  
```  
  
 Usando códigos de escape hexadecimal inserido para especificar literais de cadeia de caracteres pode causar resultados inesperados. O exemplo a seguir visa criar uma literal de cadeia de caracteres que contenha o caractere ASCII 5, seguido pelos caracteres "f", "i", "v" e "e":  
  
```cpp  
"\x05five"  
```  
  
 O resultado real é um 5F hexadecimal, que é o código ASCII de um sublinhado, seguido pelos caracteres i, v e e. Para obter o resultado correto, você pode usar uma destas opções:  
  
```cpp  
"\005five"     // Use octal literal.  
"\x05" "five"  // Use string splicing.  
```  
  
 literais std::String, porque eles são tipos de std::string possam ser concatenados com o operador está definido para + [basic_string](../standard-library/basic-string-class.md) tipos. Eles também podem ser concatenados da mesma maneira como literais de cadeia de caracteres adjacentes. Em ambos os casos, a codificação de cadeia de caracteres e o sufixo devem corresponder:  
  
```cpp  
auto x1 = "hello" " " " world"; // OK  
auto x2 = U"hello" " " L"world"; // C2308: disagree on prefix  
auto x3 = u8"hello" " "s u8"world"s; // OK, agree on prefixes and suffixes  
auto x4 = u8"hello" " "s u8"world"z; // C3688, disagree on suffixes  
```  
  
### <a name="string-literals-with-universal-character-names"></a>Literais de cadeia de caracteres com nomes de caractere universal  
 Literais de cadeia de caracteres (não processados) nativo podem usar nomes de caractere universal para representar qualquer caractere, como o nome de caractere universal pode ser codificado como um ou mais caracteres no tipo de cadeia de caracteres.  Por exemplo, um nome de caractere universal que representa um caractere estendido não pode ser codificado em uma cadeia de caracteres específica usando a página de código ANSI, mas ele pode ser codificado em cadeias de caracteres específica em algumas páginas de código multibyte em cadeias de caracteres UTF-8 ou em uma cadeia de caracteres larga. No C++ 11, suporte a Unicode é estendido pela char16_t * e char32_t\* tipos de cadeia de caracteres:  
  
```cpp  
// ASCII smiling face  
const char*     s1 = ":-)";    
  
// UTF-16 (on Windows) encoded WINKING FACE (U+1F609)  
const wchar_t*  s2 = L"😉 = \U0001F609 is ;-)";    
  
// UTF-8  encoded SMILING FACE WITH HALO (U+1F607)  
const char*     s3 = u8"😇 = \U0001F607 is O:-)";  
  
// UTF-16 encoded SMILING FACE WITH OPEN MOUTH (U+1F603)  
const char16_t* s4 = u"😃 = \U0001F603 is :-D";  
  
// UTF-32 encoded SMILING FACE WITH SUNGLASSES (U+1F60E)  
const char32_t* s5 = U"😎 = \U0001F60E is B-)";  
```  
  
## <a name="see-also"></a>Consulte também  
 [Conjuntos de caracteres](../cpp/character-sets2.md)   
 [Numérico, booleano e literais de ponteiro](../cpp/numeric-boolean-and-pointer-literals-cpp.md)   
 [Literais definidos pelo usuário](../cpp/user-defined-literals-cpp.md)
