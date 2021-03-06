---
title: 2.7 ambiente de dados | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 74e44b3c-e18c-4773-8e78-cd6c4413ae57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17c60c621defa15c034f57d0af8f14637db54f03
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378131"
---
# <a name="27-data-environment"></a>2.7 Ambiente de dados

Esta seção apresenta uma diretiva e várias cláusulas para controlar o ambiente de dados durante a execução de regiões em paralelo, da seguinte maneira:

- Um **threadprivate** diretiva (consulte a seção a seguir) é fornecida para tornar o escopo de arquivo, escopo de namespace ou variáveis estáticas de escopo de bloco local para um thread.

- As cláusulas que podem ser especificadas em que as diretivas para controlar os atributos de compartilhamento de variáveis para a duração das construções paralelas ou compartilhamento de trabalho são descritas em [seção 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) na página 25.