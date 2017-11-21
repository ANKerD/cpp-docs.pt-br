---
title: Percorrendo um conjunto de linhas Simple | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data access [C++], rowsets
- rowsets [C++], accessing
- simple rowsets
- OLE DB consumers [C++], database attributes
- accessors [C++], rowsets
ms.assetid: b45acf16-4029-429d-ab8d-b7fba98b9740
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5f4204027d52a5dfd4d7968732fb4d08328f12ce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="traversing-a-simple-rowset"></a>Percorrendo um conjunto de linhas simples
O exemplo a seguir mostra um acesso de banco de dados rápida e fácil que não envolvem comandos. O seguinte código de cliente, em um projeto de ATL, recupera os registros de uma tabela chamada *artistas* no Microsoft Access de banco de dados usando o provedor Microsoft OLE DB para ODBC. O código cria um [CTable](../../data/oledb/ctable-class.md) objeto de tabela com um acessador com base na classe de registro de usuário `CArtists`. Abre uma conexão, abre uma sessão em que a conexão e abre a tabela na sessão.  
  
```  
#include <atldbcli.h>  
  
CDataSource connection;  
CSession session;  
CTable<CAccessor<CArtists> > artists;  
  
// Open the connection, session, and table, specifying authentication   
// using Windows NT integrated security. Hard-coding a password is a major  
// security weakness.  
connection.Open(CLSID_MSDASQL, "NWind", NULL, NULL,   
DBPROP_AUTH_INTEGRATED);  
session.Open(connection);  
artists.Open(session, "Artists");  
  
// Get data from the rowset  
while (artists.MoveNext() == S_OK)  
{  
   cout << artists.m_szFirstName;  
   cout << artists.m_szLastName;  
}  
```  
  
 O registro de usuário, `CArtists`, tem esta aparência:  
  
```  
class CArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_COLUMN_MAP(CArtists)  
   COLUMN_ENTRY(1, m_szFirstName)  
   COLUMN_ENTRY(2, m_szLastName)  
   COLUMN_ENTRY(3, m_nAge)  
END_COLUMN_MAP()  
```  
  
## <a name="see-also"></a>Consulte também  
 [Trabalhando com modelos de consumidor do OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)