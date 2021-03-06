---
title: Classes de seções críticas (ATL) e modelos de Threading | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- vc.atl.threads.models
dev_langs:
- C++
helpviewer_keywords:
- ATL, critical sections
- ATL, multithreading
- threading [ATL], models
- critical sections
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b87fdac5220ede47f1acf19088e952fde408a413
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755951"
---
# <a name="threading-models-and-critical-sections-classes"></a>Classes de seções críticas e modelos de Threading

As seguintes classes definem um threading modelo e a seção crítica:

- [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) implementa um servidor COM em pool de thread, o modelo de apartment.

- [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) fornece métodos para implementação de um servidor COM em pool de thread, o modelo de apartment.

- [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) fornece métodos thread-safe para incrementar e diminuir uma variável. Fornece uma seção crítica.

- [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) fornece métodos thread-safe para incrementar e diminuir uma variável. Não oferece uma seção crítica.

- [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) fornece métodos para incrementar e diminuir uma variável. Não oferece uma seção crítica.

- [CComObjectThreadModel](../atl/reference/atl-typedefs.md#ccomobjectthreadmodel) determina a classe de modelo de threading apropriada para uma classe de objeto único.

- [CComGlobalsThreadModel](../atl/reference/atl-typedefs.md#ccomglobalsthreadmodel) determina a classe de modelo de threading apropriada para um objeto que está disponível globalmente.

- [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) contém métodos para obter e liberar uma seção crítica. A seção crítica é inicializada automaticamente.

- [CComCriticalSection](../atl/reference/ccomcriticalsection-class.md) contém métodos para obter e liberar uma seção crítica. A seção crítica deve ser inicializada explicitamente.

- [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) espelha os métodos no `CComCriticalSection` sem fornecer uma seção crítica. Os métodos em `CComFakeCriticalSection` não faça nada.

- [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) fornece a função de criação para um thread de CRT. Use essa classe se o thread usará as funções de CRT.

- [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) fornece a função de criação para um thread do Windows. Use essa classe se o thread não usará as funções de CRT.

## <a name="see-also"></a>Consulte também

[Visão geral da classe](../atl/atl-class-overview.md)

