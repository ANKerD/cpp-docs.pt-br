---
title: Testando o provedor somente leitura | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, calling
- OLE DB providers, testing
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: aa56a62fa898f7ebe6c171af6f7246106b8e5ac7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038719"
---
# <a name="testing-the-read-only-provider"></a>Testando o provedor somente leitura simples

Para testar um provedor, você precisa de um consumidor. Isso será útil se o consumidor pode corresponder com o provedor. Os modelos de consumidor do OLE DB são um wrapper fino em torno do OLE DB e coincidirem com os objetos COM de provedor. Como a fonte é fornecida com os modelos de consumidor, é fácil de depurar um provedor com eles. Os modelos de consumidor também são uma maneira muito pequeno e rápida para desenvolver aplicativos de consumidor.  
  
O exemplo neste tópico cria um aplicativo do Assistente de aplicativo MFC padrão para um consumidor de teste. O aplicativo de teste é uma caixa de diálogo simple com o código de modelo de consumidor OLE DB adicionado.  
  
### <a name="to-create-the-test-application"></a>Para criar o aplicativo de teste  
  
1. No menu **Arquivo**, clique em **Novo** e clique em **Projeto**.  
  
1. No painel Tipos de Projeto, selecione a pasta **Projetos do Visual C++**. No painel modelos, selecione **aplicativo do MFC**.  
  
1. Para o nome do projeto, insira **TestProv**e, em seguida, clique em **Okey**.  
  
     O Assistente de aplicativo do MFC é exibida.  
  
1. Sobre o **tipo de aplicativo** página, selecione **caixa de diálogo com base em**.  
  
1. Sobre o **recursos avançados** página, selecione **automação**e, em seguida, clique em **concluir**.  
  
> [!NOTE]
>  O aplicativo não exija o suporte de automação se você adicionar **CoInitialize** na **CTestProvApp::InitInstance**.  
  
Você pode exibir e editar a caixa de diálogo TestProv (IDD_TESTPROV_DIALOG), selecionando-o no modo de exibição de recursos. Coloque as duas caixas de listagem, uma para cada cadeia de caracteres no conjunto de linhas, na caixa de diálogo. Desativar a propriedade de classificação para as duas caixas de listagem, pressionando ALT + Enter quando uma caixa de listagem é selecionada, clicar na **estilos** guia e desmarcando o **classificação** caixa de seleção. Além disso, coloque um **executar** botão na caixa de diálogo para buscar o arquivo. A caixa de diálogo TestProv concluída deve ter duas caixas de listagem rotulada como "Cadeia de caracteres 1" e "Cadeia de caracteres 2", respectivamente; Ele também tem **Okey**, **Cancelar**, e **execute** botões.  
  
Abra o arquivo de cabeçalho para a classe de caixa de diálogo (no TestProvDlg.h neste caso). Adicione o seguinte código para o arquivo de cabeçalho (fora de qualquer declaração de classe):  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// TestProvDlg.h  
  
class CProvider   
{  
// Attributes  
public:  
   char   szField1[16];  
   char   szField2[16];  
  
   // Binding Maps  
BEGIN_COLUMN_MAP(CProvider)  
   COLUMN_ENTRY(1, szField1)  
   COLUMN_ENTRY(2, szField2)  
END_COLUMN_MAP()  
};  
```  
  
O código representa um registro de usuário que define quais colunas serão no conjunto de linhas. Quando o cliente chama `IAccessor::CreateAccessor`, ele usa essas entradas para especificar quais colunas você deseja associar. Os modelos de consumidor do OLE DB também permitem que você associar colunas dinamicamente. As macros COLUMN_ENTRY são a versão do lado do cliente das macros PROVIDER_COLUMN_ENTRY. As duas macros COLUMN_ENTRY especifiquem o ordinal, o membro de dados, comprimento e tipo para duas cadeias de caracteres.  
  
Adicionar uma função de manipulador para o **executados** botão pressionando CTRL e clicando duas vezes o **executar** botão. Coloque o seguinte código na função:  
  
```cpp
///////////////////////////////////////////////////////////////////////  
// TestProvDlg.cpp  
  
void CtestProvDlg::OnRun()  
{  
   CCommand<CAccessor<CProvider>> table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
      return;  
  
   if (session.Open(source) != S_OK)  
      return;  
  
   if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
      return;  
  
   while (table.MoveNext() == S_OK)  
   {  
      m_ctlString1.AddString(table.szField1);  
      m_ctlString2.AddString(table.szField2);  
   }  
}  
```  
  
O `CCommand`, `CDataSource`, e `CSession` classes todas pertencem aos modelos de consumidor OLE DB. Cada classe imita um objeto COM no provedor. O `CCommand` objeto leva o `CProvider` classe, declarada no arquivo de cabeçalho, como um parâmetro de modelo. O `CProvider` parâmetro representa as associações que você usa para acessar os dados do provedor. Aqui está o `Open` código para a fonte de dados, sessão e comando:  
  
```cpp  
if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
   return;  
  
if (session.Open(source) != S_OK)  
   return;  
  
if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
   return;  
```  
  
As linhas para abrir cada uma das classes criam cada objeto COM no provedor. Para localizar o provedor, use o ProgID do provedor. Você pode obter o ProgID do registro do sistema ou examinando o arquivo MyProvider.rgs (abrir diretório e a pesquisa para a chave ProgID do provedor).  
  
O arquivo txt está incluído com o exemplo MyProv. Para criar um arquivo de sua preferência, use um editor e digite um número par de cadeias de caracteres, pressionando ENTER entre cada cadeia de caracteres. Se você mover o arquivo, altere o nome do caminho.  
  
Passe a cadeia de caracteres "c:\\\samples\\\myprov\\\MyData.txt" no `table.Open` linha. Se você entrar na `Open` chamada, você ver que essa cadeia de caracteres é transmitida para o `SetCommandText` método no provedor. Observe que o `ICommandText::Execute` método usou essa cadeia de caracteres.  
  
Para buscar os dados, chame `MoveNext` na tabela. `MoveNext` chamadas a `IRowset::GetNextRows`, `GetRowCount`, e `GetData` funções. Quando não existem mais linhas (ou seja, a posição atual no conjunto de linhas é maior que `GetRowCount`), o loop é encerrado:  
  
```cpp  
while (table.MoveNext() == S_OK)  
{  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
Observe que, quando não existem mais linhas, provedores retornam DB_S_ENDOFROWSET. O valor DB_S_ENDOFROWSET não é um erro. Você sempre deve verificar em relação a S_OK para cancelar um loop de busca de dados e não usar a macro SUCCEEDED.  
  
Agora você deve ser capaz de compilar e testar o programa.  
  
## <a name="see-also"></a>Consulte também  

[Aprimorando o provedor somente leitura simples](../../data/oledb/enhancing-the-simple-read-only-provider.md)