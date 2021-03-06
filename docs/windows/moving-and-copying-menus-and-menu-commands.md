---
title: Movendo e copiando Menus e comandos de Menu (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- commands [C++], copying on menus
- menu items, moving
- commands [C++], moving on menus
- menu items, copying
ms.assetid: 1d8df535-9922-4579-a9c2-37aeac1856eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b12d9d09cd2e4b35c458c2acbefa48eee8c4b0a9
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44312751"
---
# <a name="moving-and-copying-menus-and-menu-commands"></a>Movendo e copiando menus e comandos de menu

Você pode mover ou copiar os menus e comandos de menu usando o método de arrastar e soltar ou usando comandos no menu de atalho (menu de atalho).

### <a name="to-move-or-copy-menus-or-menu-commands-using-the-drag-and-drop-method"></a>Para mover ou copiar menus ou comandos de menu usando o método de arrastar e soltar

1. Arrastar ou copiar o item que você deseja mover para:

   - Um novo local no menu atual.

   - Um menu diferente. (Você pode navegar para outros menus, arrastando o ponteiro do mouse sobre eles.)

2. Cancelar o comando de menu quando o guia de inserção mostra a posição desejada.

### <a name="to-move-or-copy-menus-or-menu-commands-using-shortcut-menu-commands"></a>Para mover ou copiar menus ou comandos de menu usando comandos de menu de atalho

1. Um ou mais menus ou comandos de menu de atalho.

2. No menu de atalho, escolha **Recortar** (para mover) ou **cópia**.

3. Se você estiver movendo os itens ao menu de outro recurso ou o arquivo de script de recurso [abri-lo em outra janela](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

4. Selecione a posição do menu ou comando de menu que você deseja mover ou copiar para.

5. No menu de atalho, escolha **colar**. O item movido ou copiado é colocado antes do item selecionado.

   > [!NOTE]
   > Você também pode arrastar, copie e cole a outros menus em outras janelas do menu.

Para obter informações sobre como adicionar recursos a projetos gerenciados, consulte [recursos em aplicativos de área de trabalho](/dotnet/framework/resources/index) na *guia do desenvolvedor do .NET Framework*. Para obter informações sobre como adicionar manualmente os arquivos de recurso a projetos gerenciados, acessar recursos, exibir recursos estáticos e atribuir recursos cadeias de caracteres de propriedades.

## <a name="requirements"></a>Requisitos

Win32

## <a name="see-also"></a>Consulte também

[Editor de Menu](../windows/menu-editor.md)