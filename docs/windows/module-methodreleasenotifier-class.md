---
title: Classe methodreleasenotifier | Microsoft Docs
ms.custom: ''
ms.date: 09/17/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::MethodReleaseNotifier::method_
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::object_
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Module::MethodReleaseNotifier class
- Microsoft::WRL::Module::MethodReleaseNotifier::Invoke method
- Microsoft::WRL::Module::MethodReleaseNotifier::method_ data member
- Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier, constructor
- Microsoft::WRL::Module::MethodReleaseNotifier::object_ data member
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8e78542e016ab0ba8ef33a5655b72fcdff45ccc4
ms.sourcegitcommit: 338e1ddc2f3869d92ba4b73599d35374cf1d5b69
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2018
ms.locfileid: "46494446"
---
# <a name="modulemethodreleasenotifier-class"></a>Classe Module::MethodReleaseNotifier

Invoca um manipulador de eventos quando o último objeto no módulo atual é liberado. O manipulador de eventos é especificado por um objeto e seu membro de ponteiro ao método.

## <a name="syntax"></a>Sintaxe

```cpp
template<typename T>
class MethodReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Parâmetros

*T*<br/>
O tipo do objeto cuja função de membro é o manipulador de eventos.

## <a name="members"></a>Membros

### <a name="public-constructors"></a>Construtores Públicos

Nome                                                                                                 | Descrição
---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------
[Module::MethodReleaseNotifier::MethodReleaseNotifier](#methodreleasenotifier-methodreleasenotifier) | Inicializa uma nova instância da classe `Module::MethodReleaseNotifier`.

### <a name="public-methods"></a>Métodos públicos

Nome                                                                   | Descrição
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------
[Module:: methodreleasenotifier:: Invoke](#methodreleasenotifier-invoke) | Chama o manipulador de eventos associado ao atual `Module::MethodReleaseNotifier` objeto.

### <a name="protected-data-members"></a>Membros de dados protegidos

Nome                                                                    | Descrição
----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[Module::MethodReleaseNotifier::method_](#methodreleasenotifier-method) | Contém um ponteiro para o manipulador de eventos para o atual `Module::MethodReleaseNotifier` objeto.
[Module::MethodReleaseNotifier::object_](#methodreleasenotifier-object) | Contém um ponteiro para o objeto cuja função de membro é o manipulador de eventos para o atual `Module::MethodReleaseNotifier` objeto.

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`ReleaseNotifier`

`MethodReleaseNotifier`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** module.h

**Namespace:** Microsoft::WRL

## <a name="methodreleasenotifier-invoke"></a>Module:: methodreleasenotifier:: Invoke

Chama o manipulador de eventos associado ao atual `Module::MethodReleaseNotifier` objeto.

```cpp
void Invoke();
```

## <a name="methodreleasenotifier-method"></a>Module::MethodReleaseNotifier::method_

Contém um ponteiro para o manipulador de eventos para o atual `Module::MethodReleaseNotifier` objeto.

```cpp
void (T::* method_)();
```

## <a name="methodreleasenotifier-methodreleasenotifier"></a>Module::MethodReleaseNotifier::MethodReleaseNotifier

Inicializa uma nova instância da classe `Module::MethodReleaseNotifier`.

```cpp
MethodReleaseNotifier(
   _In_ T* object,
   _In_ void (T::* method)(),
   bool release) throw() :
            ReleaseNotifier(release), object_(object),
            method_(method);
```

### <a name="parameters"></a>Parâmetros

*object*  
Um objeto cuja função de membro é um manipulador de eventos.

*Método*  
A função de membro do parâmetro *objeto* que é o manipulador de eventos.

*release*  
Especificar `true` para habilitar a chamada subjacente [Module:: ReleaseNotifier::Release()](../windows/module-releasenotifier-class.md#releasenotifier-release) método; caso contrário, especifique `false`.

## <a name="methodreleasenotifier-object"></a>Module::MethodReleaseNotifier::object_

Contém um ponteiro para o objeto cuja função de membro é o manipulador de eventos para o atual `Module::MethodReleaseNotifier` objeto.

```cpp
T* object_;
```
