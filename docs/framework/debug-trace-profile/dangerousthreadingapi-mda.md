---
title: MDA de dangerousThreadingAPI
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- suspending threads
- DangerousThreadingAPI MDA
- managed debugging assistants (MDAs), dangerous threading operations
- threading [.NET Framework], suspending
- MDAs (managed debugging assistants), dangerous threading operations
- Suspend method
- threading [.NET Framework], managed debugging assistants
ms.assetid: 3e5efbc5-92e4-4229-b31f-ce368a1adb96
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4b7c4e7f5612cb6a46f16b6e42327e8430d548e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="dangerousthreadingapi-mda"></a>MDA de dangerousThreadingAPI
El Asistente para la depuración administrada (MDA) de `dangerousThreadingAPI` se activa cuando se llama al método <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> en un subproceso diferente al subproceso actual.  
  
## <a name="symptoms"></a>Síntomas  
 Una aplicación no responde o se bloquea continuamente. Los datos de la aplicación o el sistema pueden permanecer en un estado imprevisible temporalmente o incluso después de que una aplicación se haya cerrado. Algunas operaciones no se completan según lo esperado.  
  
 Los síntomas pueden variar enormemente debido a la aleatoriedad inherente al problema.  
  
## <a name="cause"></a>Motivo  
 Un subproceso está suspendido de manera asincrónica mediante otro subproceso que usa el método <xref:System.Threading.Thread.Suspend%2A>. No existe ninguna manera de determinar cuándo es seguro suspender otro subproceso que puede encontrarse en el proceso de una operación. La suspensión del subproceso puede provocar daños en los datos o la interrupción de invariantes. Si un subproceso se coloca en un estado suspendido y nunca se reanuda con el método <xref:System.Threading.Thread.Resume%2A>, la aplicación puede bloquearse de manera indefinida y posiblemente dañe los datos de la aplicación. Estos métodos se han marcado como obsoletos.  
  
 Si los tipos primitivos de sincronización se incluyen en el subproceso de destino, permanecen así durante la suspensión. Esto puede provocar interbloqueos si otro subproceso, por ejemplo el subproceso que realiza <xref:System.Threading.Thread.Suspend%2A>, intenta adquirir un bloqueo en el tipo primitivo. En esta situación, el problema se manifiesta como un interbloqueo.  
  
## <a name="resolution"></a>Resolución  
 Evite diseños que necesiten el uso de <xref:System.Threading.Thread.Suspend%2A> y <xref:System.Threading.Thread.Resume%2A>. Para obtener una cooperación entre subprocesos, use los tipos primitivos de sincronización como <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex> o la instrucción `lock` de C#. Si debe usar estos métodos, reduzca el período de tiempo y minimice la cantidad de código que ejecuta mientras el subproceso está en un estado suspendido.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR. Solo notifica datos sobre operaciones de subproceso peligrosas.  
  
## <a name="output"></a>Salida  
 El MDA identifica el método de subproceso peligroso que ha provocado que se active.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra una llamada al método <xref:System.Threading.Thread.Suspend%2A> que provoca la activación de `dangerousThreadingAPI`.  
  
```  
using System.Threading;  
void FireMda()  
{  
Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Suspend();   
    t.Resume();  
    t.Join();  
}  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Thread>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [lock (instrucción)](~/docs/csharp/language-reference/keywords/lock-statement.md)
