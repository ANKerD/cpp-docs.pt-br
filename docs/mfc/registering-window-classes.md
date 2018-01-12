---
title: Registrando Classes de janela | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: WndProc
dev_langs: C++
helpviewer_keywords:
- window classes [MFC], registering
- registry [MFC], registering classes
- AfxRegisterWndClass method [MFC]
- MFC, windows
- WinMain method [MFC], and registering window classes
- WndProc method [MFC]
- classes [MFC], registering window classes
- WinMain method [MFC]
- registering window classes [MFC]
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 92f5673aac014abdd4fd19425d9ae849f64284ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="registering-window-classes"></a>Registrando classes de janela
"Classes de janela" em programação tradicional do Windows definem as características de uma classe"" (não uma classe C++) de que qualquer número do windows pode ser criado. Esse tipo de classe é um modelo ou um modelo para a criação do windows.  
  
## <a name="window-class-registration-in-traditional-programs-for-windows"></a>Registro de classe de janela em programas tradicionais para Windows  
 Em um programa tradicional para o Windows sem MFC, processar todas as mensagens para uma janela em seu procedimento de janela"" ou "**WndProc**." Um **WndProc** está associado uma janela por meio de um processo de "registro da classe window". A janela principal é registrada no `WinMain` função, mas outras classes do windows podem ser registrados em qualquer lugar no aplicativo. Registro depende de uma estrutura que contém um ponteiro para o **WndProc** função junto com as especificações para o cursor, o pincel do plano de fundo e assim por diante. A estrutura é passada como um parâmetro, junto com o nome de cadeia de caracteres da classe em uma chamada anterior para o **RegisterClass** função. Portanto, uma classe de registro pode ser compartilhada por várias janelas.  
  
## <a name="window-class-registration-in-mfc-programs"></a>Registro de classe de janela nos programas do MFC  
 Por outro lado, a maioria das atividades de registro de classe de janela é feito automaticamente em um programa do framework do MFC. Se você estiver usando MFC, você normalmente derivar uma classe de janela C++ de uma classe de biblioteca existente usando a sintaxe de C++ normal de herança de classe. A estrutura ainda usa tradicional "classes de registro" e fornece vários as padrão, registradas para você quando necessário. Você pode registrar as classes de registro adicionais chamando o [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) função global e, em seguida, passando a classe registrada para o **criar** função de membro `CWnd`. Conforme descrito aqui, o tradicional "classe de registro" no Windows não é deve ser confundido com uma classe do C++.  
  
 Para obter mais informações, consulte [técnico Observação 1](../mfc/tn001-window-class-registration.md).  
  
## <a name="see-also"></a>Consulte também  
 [Criando janelas](../mfc/creating-windows.md)
