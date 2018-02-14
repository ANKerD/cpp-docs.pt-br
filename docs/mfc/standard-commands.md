---
title: "Comandos padrão | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- File menu
- identifiers [MFC], command IDs
- command IDs, standard commands
- OLE commands
- commands [MFC], standard
- standard command IDs
- Window menu commands
- standard commands
- View menu commands
- Edit menu standard commands
- Help [MFC], menus
- programmer-defined IDs [MFC]
ms.assetid: 88cf3ab4-79b3-4ac6-9365-8ac561036fbf
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bbdb763b2d7da04267a195e5d534da9528f2b74d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="standard-commands"></a>Comandos padrão
A estrutura define muitas mensagens de comando padrão. Normalmente, as IDs para esses comandos assumem a forma:  
  
 **ID _** *fonte*_*Item*  
  
 onde *fonte* geralmente é um nome de menu e *Item* é um item de menu. Por exemplo, a ID de comando para o novo comando no menu arquivo é `ID_FILE_NEW`. IDs de comando padrão são mostrados em negrito na documentação. IDs definidos pelo programador são mostrados em uma fonte diferente do texto ao redor.  
  
 A seguir está uma lista de alguns dos comandos mais importantes com suporte:  
  
 *Comandos do Menu arquivo*  
 Novo, abrir, fechar, salvar, salvar como, Configurar página, Configurar impressão, imprimir, visualizar impressão, sair e arquivos usados mais recentemente.  
  
 *Comandos do Menu Editar*  
 Claro, desmarque todos, copiar, recortar, localizar, colar, repetir, substituir, selecione todos, desfazer e refazer.  
  
 *Comandos do menu Exibir*  
 Barra de ferramentas e barra de Status.  
  
 *Comandos do menu Janela*  
 Novo, organizar, em cascata, bloco Horizontal, Vertical de bloco e dividir.  
  
 *Comandos do menu Ajuda*  
 Índice, usando a Ajuda e sobre.  
  
 *Comandos OLE (Menu Editar)*  
 Inserir objeto novo, Editar Links, Colar vínculo, Colar especial, e *typename* objeto (comandos de verbo).  
  
 O framework fornece vários níveis de suporte para esses comandos. Alguns comandos são suportados apenas como IDs de comando definido, enquanto outros são compatíveis com implementações completa. Por exemplo, a estrutura implementa o comando Abrir no menu Arquivo Criando um novo objeto de documento, exibindo uma caixa de diálogo Abrir e abrir e ler o arquivo. Por outro lado, você deve implementar comandos no menu Editar, desde que os comandos **ID_EDIT_COPY** dependerá da natureza dos dados que você está copiando.  
  
 Para obter mais informações sobre os comandos com suporte e o nível de implementação fornecido, consulte [22 de observação técnica](../mfc/tn022-standard-commands-implementation.md). Os comandos padrão são definidos no arquivo AFXRES. H.  
  
## <a name="see-also"></a>Consulte também  
 [Objetos da interface do usuário e IDs de comando](../mfc/user-interface-objects-and-command-ids.md)
