---
title: Classe CWinThread | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinThread
- AFXWIN/CWinThread
- AFXWIN/CWinThread::CWinThread
- AFXWIN/CWinThread::CreateThread
- AFXWIN/CWinThread::ExitInstance
- AFXWIN/CWinThread::GetMainWnd
- AFXWIN/CWinThread::GetThreadPriority
- AFXWIN/CWinThread::InitInstance
- AFXWIN/CWinThread::IsIdleMessage
- AFXWIN/CWinThread::OnIdle
- AFXWIN/CWinThread::PostThreadMessage
- AFXWIN/CWinThread::PreTranslateMessage
- AFXWIN/CWinThread::ProcessMessageFilter
- AFXWIN/CWinThread::ProcessWndProcException
- AFXWIN/CWinThread::PumpMessage
- AFXWIN/CWinThread::ResumeThread
- AFXWIN/CWinThread::Run
- AFXWIN/CWinThread::SetThreadPriority
- AFXWIN/CWinThread::SuspendThread
- AFXWIN/CWinThread::m_bAutoDelete
- AFXWIN/CWinThread::m_hThread
- AFXWIN/CWinThread::m_nThreadID
- AFXWIN/CWinThread::m_pActiveWnd
- AFXWIN/CWinThread::m_pMainWnd
dev_langs: C++
helpviewer_keywords:
- CWinThread [MFC], CWinThread
- CWinThread [MFC], CreateThread
- CWinThread [MFC], ExitInstance
- CWinThread [MFC], GetMainWnd
- CWinThread [MFC], GetThreadPriority
- CWinThread [MFC], InitInstance
- CWinThread [MFC], IsIdleMessage
- CWinThread [MFC], OnIdle
- CWinThread [MFC], PostThreadMessage
- CWinThread [MFC], PreTranslateMessage
- CWinThread [MFC], ProcessMessageFilter
- CWinThread [MFC], ProcessWndProcException
- CWinThread [MFC], PumpMessage
- CWinThread [MFC], ResumeThread
- CWinThread [MFC], Run
- CWinThread [MFC], SetThreadPriority
- CWinThread [MFC], SuspendThread
- CWinThread [MFC], m_bAutoDelete
- CWinThread [MFC], m_hThread
- CWinThread [MFC], m_nThreadID
- CWinThread [MFC], m_pActiveWnd
- CWinThread [MFC], m_pMainWnd
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 406fc12869d6fe02188de6e469af17b3809df9b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="cwinthread-class"></a>Classe CWinThread
Representa um segmento de execução dentro de um aplicativo.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CWinThread : public CCmdTarget  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CWinThread::CWinThread](#cwinthread)|Constrói um objeto `CWinThread`.|  
  
### <a name="public-methods"></a>Métodos Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CWinThread::CreateThread](#createthread)|Inicia a execução de um `CWinThread` objeto.|  
|[CWinThread::ExitInstance](#exitinstance)|Substituição para a limpeza quando o thread será encerrado.|  
|[CWinThread::GetMainWnd](#getmainwnd)|Recupera um ponteiro para a janela principal para o thread.|  
|[CWinThread::GetThreadPriority](#getthreadpriority)|Obtém a prioridade do thread atual.|  
|[CWinThread::InitInstance](#initinstance)|Substituição para executar a inicialização de instância de thread.|  
|[CWinThread::IsIdleMessage](#isidlemessage)|Verifica se há mensagens especiais.|  
|[CWinThread::OnIdle](#onidle)|Substituição para executar o processamento de tempo ocioso do thread específico.|  
|[CWinThread::PostThreadMessage](#postthreadmessage)|Envia uma mensagem para outro `CWinThread` objeto.|  
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Filtra as mensagens antes de serem distribuídos para as funções do Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) e [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|Interceptar determinadas mensagens antes que elas atinjam o aplicativo.|  
|[CWinThread::ProcessWndProcException](#processwndprocexception)|Intercepta todas as exceções sem tratamento lançadas por manipuladores de comando e de mensagem do thread.|  
|[CWinThread::PumpMessage](#pumpmessage)|Contém um loop de mensagem do thread.|  
|[CWinThread::ResumeThread](#resumethread)|Decrementa uma do thread suspende a contagem.|  
|[CWinThread::Run](#run)|Controlando a função de threads com uma bomba de mensagem. Substitua para personalizar o loop de mensagem padrão.|  
|[CWinThread::SetThreadPriority](#setthreadpriority)|Define a prioridade do thread atual.|  
|[CWinThread::SuspendThread](#suspendthread)|Incrementos de um de thread suspender a contagem.|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[Identificador de CWinThread::operator](#operator_handle)|Recupera o identificador do `CWinThread` objeto.|  
  
### <a name="public-data-members"></a>Membros de Dados Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CWinThread::m_bAutoDelete](#m_bautodelete)|Especifica se deseja destruir o objeto no encerramento do thread.|  
|[CWinThread::m_hThread](#m_hthread)|Identificador para o thread atual.|  
|[CWinThread::m_nThreadID](#m_nthreadid)|ID do thread atual.|  
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|Ponteiro para a janela principal do aplicativo recipiente quando um servidor OLE está ativo no local.|  
|[CWinThread::m_pMainWnd](#m_pmainwnd)|Contém um ponteiro para a janela principal do aplicativo.|  
  
## <a name="remarks"></a>Comentários  
 O thread principal de execução geralmente é fornecido por um objeto derivado de `CWinApp`; `CWinApp` é derivado de `CWinThread`. Adicionais `CWinThread` objetos permitem que vários threads dentro de um determinado aplicativo.  
  
 Há dois tipos gerais de threads que `CWinThread` oferece suporte a: threads de trabalho e os threads de interface do usuário. Threads de trabalho não tem nenhum bombeador: por exemplo, um thread que executa cálculos de plano de fundo em um aplicativo de planilha. Threads de interface do usuário tem uma bomba de mensagem e processam as mensagens recebidas do sistema. [CWinApp](../../mfc/reference/cwinapp-class.md) e classes derivadas dele são exemplos de threads de interface do usuário. Outros threads de interface do usuário também podem ser derivados diretamente do `CWinThread`.  
  
 Objetos da classe `CWinThread` normalmente existe para a duração do thread. Se você deseja modificar esse comportamento, defina [m_bAutoDelete](#m_bautodelete) para **FALSE**.  
  
 O `CWinThread` classe é necessária tornar o seu código e o MFC totalmente thread-safe. Dados de local de thread usados pelo framework para manter informações específicas de thread são gerenciados pelo `CWinThread` objetos. Devido a essa dependência `CWinThread` para lidar com dados de local de thread, qualquer thread que usa MFC deve ser criada por MFC. Por exemplo, um thread criado pela função de tempo de execução [beginthread, beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) não é possível usar quaisquer APIs do MFC.  
  
 Para criar um thread, chame [AfxBeginThread](application-information-and-management.md#afxbeginthread). Há duas formas, dependendo se você deseja que um thread de trabalho ou a interface do usuário. Se você quiser que um thread de interface do usuário, passar para `AfxBeginThread` um ponteiro para o `CRuntimeClass` de seu `CWinThread`-classe derivada. Se você quiser criar um thread de trabalho, passe para `AfxBeginThread` um ponteiro para a função de controle e o parâmetro para a função de controle. Para threads de trabalho e os threads de interface do usuário, você pode especificar os parâmetros opcionais que modificar o tamanho da pilha, prioridade, sinalizadores de criação e atributos de segurança. `AfxBeginThread`Retorna um ponteiro para o novo `CWinThread` objeto.  
  
 Em vez de chamar `AfxBeginThread`, você pode construir um `CWinThread`-derivados do objeto e, em seguida, chamada `CreateThread`. Esse método de construção de dois estágios é útil se você quiser reutilizar o `CWinThread` objeto entre criação sucessiva e encerramentos de execuções de thread.  
  
 Para obter mais informações sobre `CWinThread`, consulte os artigos [Multithreading com C++ e MFC](../../parallel/multithreading-with-cpp-and-mfc.md), [Multithreading: Criando Threads de Interface do usuário](../../parallel/multithreading-creating-user-interface-threads.md), [Multithreading: criação de trabalho Threads](../../parallel/multithreading-creating-worker-threads.md), e [multithread: como usar as Classes de sincronização](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWinThread`  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxwin.h  
  
##  <a name="createthread"></a>CWinThread::CreateThread  
 Cria um segmento a ser executado no espaço de endereço do processo de chamada.  
  
```  
BOOL CreateThread(
    DWORD dwCreateFlags = 0,  
    UINT nStackSize = 0,  
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```  
  
### <a name="parameters"></a>Parâmetros  
 `dwCreateFlags`  
 Especifica um sinalizador adicional que controla a criação do thread. Este sinalizador pode conter um dos dois valores:  
  
- **CREATE_SUSPENDED** iniciar o thread com uma contagem de suspensão de um. Use **CREATE_SUSPENDED** se deseja inicializar todos os dados de membro de `CWinThread` objeto, como [m_bAutoDelete](#m_bautodelete) ou quaisquer membros de sua classe derivada, antes do thread é iniciado. Quando a inicialização for concluída, use o [CWinThread::ResumeThread](#resumethread) ao iniciar o thread em execução. O thread não será executado até `CWinThread::ResumeThread` é chamado.  
  
- **0** iniciar o thread imediatamente após a criação.  
  
 `nStackSize`  
 Especifica o tamanho em bytes da pilha para o novo thread. Se **0**, o tamanho da pilha padrão é o mesmo tamanho que o thread principal do processo.  
  
 `lpSecurityAttrs`  
 Aponta para um [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) estrutura que especifica os atributos de segurança para o thread.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se o thread é criado com êxito; Caso contrário, 0.  
  
### <a name="remarks"></a>Comentários  
 Use `AfxBeginThread` para criar um objeto de segmento e executá-lo em uma única etapa. Use `CreateThread` se quiser reutilizar o objeto de thread entre criação sucessiva e encerramento de execuções de thread.  
  
##  <a name="cwinthread"></a>CWinThread::CWinThread  
 Constrói um objeto `CWinThread`.  
  
```  
CWinThread();
```  
  
### <a name="remarks"></a>Comentários  
 Para começar a execução do thread, chame o [CreateThread](#createthread) função de membro. Você geralmente criará threads chamando [AfxBeginThread](application-information-and-management.md#afxbeginthread), que chamará este construtor e `CreateThread`.  
  
##  <a name="exitinstance"></a>CWinThread::ExitInstance  
 Chamado pelo framework de dentro de um raramente substituído [executar](#run) a função de membro para sair dessa instância do segmento, ou se uma chamada para [InitInstance](#initinstance) falhar.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Código de saída do thread; 0 não indica que nenhum erro, e os valores maiores que 0 indicam um erro. Esse valor pode ser recuperado chamando [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  
  
### <a name="remarks"></a>Comentários  
 Não chame a função de membro de qualquer lugar mas dentro do **executar** função de membro. Essa função de membro é usada somente em threads de interface do usuário.  
  
 A implementação padrão desta função exclui o `CWinThread` objeto se [m_bAutoDelete](#m_bautodelete) é **TRUE**. Substitua essa função se você deseja realizar limpeza adicional quando o thread é encerrado. A implementação de `ExitInstance` deve chamar a versão da classe base depois que seu código é executado.  
  
##  <a name="getmainwnd"></a>CWinThread::GetMainWnd  
 Se seu aplicativo for um servidor OLE, chamar essa função para recuperar um ponteiro para a janela principal ativa do aplicativo em vez de referir-se diretamente para o `m_pMainWnd` membro do objeto application.  
  
```  
virtual CWnd* GetMainWnd();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Essa função retorna um ponteiro para um dos dois tipos de janelas. Se o thread faz parte de um servidor OLE e tem um objeto que está ativo no local dentro de um contêiner de ativo, essa função retorna o [CWinApp::m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) membro de dados a `CWinThread` objeto.  
  
 Se não há nenhum objeto que está ativo no local dentro de um contêiner ou seu aplicativo não é um servidor OLE, essa função retorna o [m_pMainWnd](#m_pmainwnd) membro de dados de seu objeto de thread.  
  
### <a name="remarks"></a>Comentários  
 Para threads de interface do usuário, isso é equivalente a referindo-se diretamente para o `m_pActiveWnd` membro do seu objeto de aplicativo.  
  
 Se seu aplicativo não é um servidor OLE, chamar essa função é equivalente a referindo-se diretamente para o `m_pMainWnd` membro do seu objeto de aplicativo.  
  
 Substitua esta função para modificar o comportamento padrão.  
  
##  <a name="getthreadpriority"></a>CWinThread::GetThreadPriority  
 Obtém o nível de prioridade do thread atual deste thread.  
  
```  
int GetThreadPriority();
```  
  
### <a name="return-value"></a>Valor de retorno  
 O nível de prioridade de thread atual dentro de sua classe de prioridade. O valor retornado será um dos seguintes, listados da prioridade mais alta para a mais baixa:  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **THREAD_PRIORITY_LOWEST**  
  
- **THREAD_PRIORITY_IDLE**  
  
 Para obter mais informações sobre essas prioridades, consulte [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) no SDK do Windows.  
  
##  <a name="initinstance"></a>CWinThread::InitInstance  
 `InitInstance`deve ser substituído para inicializar cada nova instância de um thread de interface do usuário.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se a inicialização for bem-sucedida; Caso contrário, 0.  
  
### <a name="remarks"></a>Comentários  
 Normalmente, você substituir `InitInstance` para executar tarefas que devem ser concluídas quando um thread é criado pela primeira vez.  
  
 Essa função de membro é usada somente em threads de interface do usuário. Executar a inicialização de threads de trabalho na função de controle passada para [AfxBeginThread](application-information-and-management.md#afxbeginthread).  
  
##  <a name="isidlemessage"></a>CWinThread::IsIdleMessage  
 Substituir esta função para manter **OnIdle** de ser chamado depois de mensagens específicas são geradas.  
  
```  
virtual BOOL IsIdleMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pMsg`  
 Aponta para a mensagem atual que está sendo processada.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se `OnIdle` deve ser chamado após o processamento de mensagem; caso contrário, 0.  
  
### <a name="remarks"></a>Comentários  
 A implementação padrão não pode ser chamado **OnIdle** depois de mensagens de mouse redundantes e as mensagens geradas pelo piscando acentos circunflexos.  
  
 Se um aplicativo tiver criado um timer de curto **OnIdle** será chamada com frequência, causando problemas de desempenho. Para melhorar o desempenho de um aplicativo, substituir `IsIdleMessage` do aplicativo `CWinApp`-classe para verificar se há derivada `WM_TIMER` mensagens da seguinte maneira:  
  
 [!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]  
  
 Tratamento `WM_TIMER` dessa maneira melhorará o desempenho de aplicativos que usam temporizadores curtos.  
  
##  <a name="m_bautodelete"></a>CWinThread::m_bAutoDelete  
 Especifica se o `CWinThread` objeto deve ser excluído automaticamente no encerramento do thread.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Comentários  
 O `m_bAutoDelete` membro de dados é uma variável pública do tipo **BOOL**.  
  
 O valor de `m_bAutoDelete` não afeta como o identificador de thread subjacente é fechado. O identificador de thread sempre é fechado quando a `CWinThread` objeto é destruído.  
  
##  <a name="m_hthread"></a>CWinThread::m_hThread  
 Manipula o thread anexado a este `CWinThread`.  
  
```  
HANDLE m_hThread;  
```  
  
### <a name="remarks"></a>Comentários  
 O `m_hThread` membro de dados é uma variável pública do tipo `HANDLE`. Ele é válido somente se existir subjacente thread no momento.  
  
##  <a name="m_nthreadid"></a>CWinThread::m_nThreadID  
 ID do thread anexado a este `CWinThread`.  
  
```  
DWORD m_nThreadID;  
```  
  
### <a name="remarks"></a>Comentários  
 O **m_nThreadID** membro de dados é uma variável pública do tipo `DWORD`. Ele é válido somente se existir subjacente thread no momento.  
  
### <a name="example"></a>Exemplo  
  Consulte o exemplo para [AfxGetThread](application-information-and-management.md#afxgetthread).  
  
##  <a name="m_pactivewnd"></a>CWinThread::m_pActiveWnd  
 Use este membro de dados para armazenar um ponteiro para objeto de janela ativa do thread.  
  
```  
CWnd* m_pActiveWnd;  
```  
  
### <a name="remarks"></a>Comentários  
 A biblioteca Microsoft Foundation Class terminará o thread automaticamente quando a janela referenciado por `m_pActiveWnd` está fechado. Se esse thread for o thread principal de um aplicativo, o aplicativo também será encerrado. Se este membro de dados é **nulo**, a janela ativa para o aplicativo `CWinApp` objeto será herdado. `m_pActiveWnd`é uma variável pública do tipo **CWnd\***.  
  
 Normalmente, você definir essa variável de membro quando você substituir `InitInstance`. Em um thread de trabalho, o valor desse membro de dados é herdado do thread de seu pai.  
  
##  <a name="m_pmainwnd"></a>CWinThread::m_pMainWnd  
 Use este membro de dados para armazenar um ponteiro para objeto de janela principal do thread.  
  
```  
CWnd* m_pMainWnd;  
```  
  
### <a name="remarks"></a>Comentários  
 A biblioteca Microsoft Foundation Class terminará o thread automaticamente quando a janela referenciado por `m_pMainWnd` está fechado. Se esse thread for o thread principal de um aplicativo, o aplicativo também será encerrado. Se este membro de dados é **nulo**, a janela principal para o aplicativo `CWinApp` objeto será usado para determinar quando encerrar o thread. `m_pMainWnd`é uma variável pública do tipo **CWnd\***.  
  
 Normalmente, você definir essa variável de membro quando você substituir `InitInstance`. Em um thread de trabalho, o valor desse membro de dados é herdado do thread de seu pai.  
  
##  <a name="onidle"></a>CWinThread::OnIdle  
 Substitua essa função de membro para executar o processamento de tempo ocioso.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>Parâmetros  
 `lCount`  
 Um contador incrementado toda vez que `OnIdle` é chamado quando a fila de mensagens do thread está vazia. Esse contador é redefinido para 0, sempre que uma nova mensagem é processada. Você pode usar o `lCount` parâmetro para determinar o tamanho relativo de tempo que o thread ficar ocioso sem processar uma mensagem.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero para receber o tempo de processamento mais ocioso; 0 se não houver mais tempo de processamento ocioso é necessário.  
  
### <a name="remarks"></a>Comentários  
 `OnIdle`é chamado no loop de mensagem padrão quando a fila de mensagens do thread está vazia. Use sua substituição para chamar seu próprio plano de fundo tarefas manipulador ocioso.  
  
 `OnIdle`deve retornar 0 para indicar que nenhum tempo de processamento ocioso adicional é necessário. O `lCount` parâmetro é incrementado toda vez que `OnIdle` é chamado quando a fila de mensagens está vazia e é redefinida como 0, sempre que uma nova mensagem é processada. Você pode chamar suas rotinas ociosas diferentes com base nessa contagem.  
  
 A implementação padrão desta função de membro libera os objetos temporários e bibliotecas de vínculo dinâmico não usada da memória.  
  
 Essa função de membro é usada somente em threads de interface do usuário.  
  
 Como o aplicativo não pode processar mensagens até `OnIdle` retorna, não execute tarefas demoradas nesta função.  
  
##  <a name="operator_handle"></a>Identificador de CWinThread::operator  
 Recupera o identificador do `CWinThread` objeto.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, o identificador do objeto de thread; Caso contrário, **nulo**.  
  
### <a name="remarks"></a>Comentários  
 Use o identificador para chamar diretamente APIs do Windows.  
  
##  <a name="postthreadmessage"></a>CWinThread::PostThreadMessage  
 Chamado para postar uma mensagem definida pelo usuário para outro `CWinThread` objeto.  
  
```  
BOOL PostThreadMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parâmetros  
 `message`  
 ID da mensagem definida pelo usuário.  
  
 `wParam`  
 Primeiro parâmetro da mensagem.  
  
 `lParam`  
 Segundo parâmetro de mensagem.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se for bem-sucedida; Caso contrário, 0.  
  
### <a name="remarks"></a>Comentários  
 A mensagem postada é mapeada para o manipulador de mensagem apropriado pela macro de mapa de mensagem `ON_THREAD_MESSAGE`.  
  
> [!NOTE]
>  Ao chamar o Windows [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946) função em um aplicativo MFC, a mensagem MFC manipuladores não forem chamados. Para obter mais informações, consulte o artigo da Base de dados de Conhecimento, "PRB: MFC mensagem manipulador não chamado com PostThreadMessage()" (Q142415).  
  
##  <a name="pretranslatemessage"></a>CWinThread::PreTranslateMessage  
 Substituir esta função para filtrar mensagens de janela antes de serem distribuídos para as funções do Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) e [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pMsg`  
 Aponta para um [estrutura MSG](../../mfc/reference/msg-structure1.md) que contém a mensagem para processar.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se a mensagem foi totalmente processada em `PreTranslateMessage` e não devem ser processados adicional. Zero se a mensagem deve ser processada da maneira normal.  
  
### <a name="remarks"></a>Comentários  
 Essa função de membro é usada somente em threads de interface do usuário.  
  
##  <a name="processmessagefilter"></a>CWinThread::ProcessMessageFilter  
 Função de gancho do framework chama esta função de membro para filtrar e responder a determinadas mensagens do Windows.  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parâmetros  
 `code`  
 Especifica um código de interceptação. Essa função de membro usa o código para determinar como processar`lpMsg.`  
  
 `lpMsg`  
 Um ponteiro para um Windows [estrutura MSG](../../mfc/reference/msg-structure1.md).  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se a mensagem é processada; Caso contrário, 0.  
  
### <a name="remarks"></a>Comentários  
 Uma função de gancho processa eventos antes de serem enviados para a mensagem normal do aplicativo de processamento.  
  
 Se você substituir este recurso avançado, certifique-se de chamar a versão da classe base para manter a estrutura de gancho de processamento.  
  
##  <a name="processwndprocexception"></a>CWinThread::ProcessWndProcException  
 O framework chama esta função de membro sempre que o manipulador não capturar uma exceção gerada em uma mensagem do thread ou manipuladores de comandos.  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>Parâmetros  
 *e*  
 Aponta para uma exceção sem tratamento.  
  
 `pMsg`  
 Aponta para um [estrutura MSG](../../mfc/reference/msg-structure1.md) que contém informações sobre a mensagem do windows que causou a estrutura lançar uma exceção.  
  
### <a name="return-value"></a>Valor de retorno  
 -1 se um `WM_CREATE` será gerada uma exceção; caso contrário, 0.  
  
### <a name="remarks"></a>Comentários  
 Não chame diretamente essa função de membro.  
  
 A implementação padrão desta função de membro controla somente as exceções geradas das seguintes mensagens:  
  
|Comando|Ação|  
|-------------|------------|  
|`WM_CREATE`|Falhe.|  
|`WM_PAINT`|Validar a janela afetada, impedindo que outra `WM_PAINT` mensagem sendo gerada.|  
  
 Substitua essa função de membro para fornecer manipulação global de sua exceções. Chame a funcionalidade básica somente se você deseja exibir o comportamento padrão.  
  
 Essa função de membro é usada somente em threads que têm uma bomba de mensagem.  
  
##  <a name="pumpmessage"></a>CWinThread::PumpMessage  
 Contém um loop de mensagem do thread.  
  
```  
virtual BOOL PumpMessage();
```  
  
### <a name="remarks"></a>Comentários  
 `PumpMessage`contém um loop de mensagem do thread. **PumpMessage** é chamado pelo `CWinThread` a bomba de mensagens do thread. Você pode chamar `PumpMessage` diretamente para forçar as mensagens a serem processadas, ou você pode substituir `PumpMessage` para alterar o comportamento padrão.  
  
 Chamando `PumpMessage` diretamente e substituir o comportamento padrão é recomendada somente para usuários avançados.  
  
##  <a name="resumethread"></a>CWinThread::ResumeThread  
 Chamado para retomar a execução de um thread que foi suspenso pelo [SuspendThread](#suspendthread) função de membro, ou em um thread criado com o **CREATE_SUSPENDED** sinalizador.  
  
```  
DWORD ResumeThread();
```  
  
### <a name="return-value"></a>Valor de retorno  
 O thread do anterior suspender a contagem se bem-sucedido; `0xFFFFFFFF` caso contrário. Se o valor de retorno for zero, o thread atual não foi suspenso. Se o valor de retorno é um, o thread foi suspenso, mas agora é reiniciado. Qualquer valor de retorno maior do que o thread de uma maneira permanece suspenso.  
  
### <a name="remarks"></a>Comentários  
 A contagem de suspensão do thread atual é reduzida por um. Se a contagem de suspensão é reduzida a zero, o thread retoma a execução; Caso contrário, o thread permanece suspenso.  
  
##  <a name="run"></a>CWinThread::Run  
 Fornece um loop de mensagem padrão para threads de interface do usuário.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um `int` valor retornado pelo segmento. Esse valor pode ser recuperado chamando [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  
  
### <a name="remarks"></a>Comentários  
 **Executar** adquire e envia mensagens do Windows até que o aplicativo recebe um [WM_QUIT](http://msdn.microsoft.com/library/windows/desktop/ms632641) mensagem. Se a fila de mensagens do thread no momento não contenha mensagens, **executar** chamadas `OnIdle` para executar o processamento de tempo ocioso. Mensagens de entrada acessem o [PreTranslateMessage](#pretranslatemessage) função de membro para processamento especial e, em seguida, a função do Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) para conversão de teclado padrão. Por fim, o [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) é chamada de função do Windows.  
  
 **Executar** raramente é substituído, mas você pode substituí-lo para implementar o comportamento especial.  
  
 Essa função de membro é usada somente em threads de interface do usuário.  
  
##  <a name="setthreadpriority"></a>CWinThread::SetThreadPriority  
 Esta função define o nível de prioridade do thread atual dentro de sua classe de prioridade.  
  
```  
BOOL SetThreadPriority(int nPriority);
```  
  
### <a name="parameters"></a>Parâmetros  
 `nPriority`  
 Especifica o novo nível de prioridade de thread dentro de sua classe de prioridade. Esse parâmetro deve ser um dos valores a seguir, listados da prioridade mais alta para a mais baixa:  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **THREAD_PRIORITY_LOWEST**  
  
- **THREAD_PRIORITY_IDLE**  
  
 Para obter mais informações sobre essas prioridades, consulte [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) no SDK do Windows.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se a função foi bem-sucedida; Caso contrário, 0.  
  
### <a name="remarks"></a>Comentários  
 Ele só pode ser chamado após [CreateThread](#createthread) retorna com êxito.  
  
##  <a name="suspendthread"></a>CWinThread::SuspendThread  
 Incrementa atual thread suspender contagem.  
  
```  
DWORD SuspendThread();
```  
  
### <a name="return-value"></a>Valor de retorno  
 O thread do anterior suspender a contagem se bem-sucedido; `0xFFFFFFFF` caso contrário.  
  
### <a name="remarks"></a>Comentários  
 Se nenhum segmento tiver uma contagem de suspensão acima de zero, o thread não é executado. O thread pode ser retomado chamando o [ResumeThread](#resumethread) função de membro.  
  
## <a name="see-also"></a>Consulte também  
 [Classe CCmdTarget](../../mfc/reference/ccmdtarget-class.md)   
 [Gráfico de hierarquia](../../mfc/hierarchy-chart.md)   
 [Classe CWinApp](../../mfc/reference/cwinapp-class.md)   
 [Classe CCmdTarget](../../mfc/reference/ccmdtarget-class.md)