---
title: Compilador aviso (nível 3) C4278 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4278
dev_langs:
- C++
helpviewer_keywords:
- C4278
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f63337de2e14b1cb0f9d854df962ab2aa9c8014e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205775"
---
# <a name="compiler-warning-level-3-c4278"></a>Compilador aviso (nível 3) C4278

> '*identificador*': identificador em biblioteca de tipos '*tlb*' já é uma macro; use o qualificador 'rename'

Ao usar [#import](../../preprocessor/hash-import-directive-cpp.md), um identificador em typelib que está sendo importado está tentando declarar um identificador *identificador*. No entanto, isso já é um símbolo válido.

Use o `#import` **Renomear** atributo para atribuir um alias para o símbolo na biblioteca de tipos.