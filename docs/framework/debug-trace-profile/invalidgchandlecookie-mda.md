---
title: MDA de invalidGCHandleCookie
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid cookies
- cookies, invalid
- managed debugging assistants (MDAs), invalid cookies
- InvalidGCHandleCookie MDA
- invalid cookies
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f4cb7655d8d70cf46926cf193d6594523316e81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="invalidgchandlecookie-mda"></a>MDA de invalidGCHandleCookie
El Asistente para la depuración administrada (MDA) `invalidGCHandleCookie` se activa cuando se intenta realizar la conversión de una cookie <xref:System.IntPtr> no válida a un <xref:System.Runtime.InteropServices.GCHandle>.  
  
## <a name="symptoms"></a>Síntomas  
 Comportamiento indefinido, como infracciones de acceso y daños en la memoria, al intentar usar o recuperar <xref:System.Runtime.InteropServices.GCHandle> desde <xref:System.IntPtr>.  
  
## <a name="cause"></a>Motivo  
 La cookie probablemente no es válida porque no se creó originalmente desde un <xref:System.Runtime.InteropServices.GCHandle>, representa un <xref:System.Runtime.InteropServices.GCHandle> que ya se ha liberado, es una cookie de un <xref:System.Runtime.InteropServices.GCHandle> en un dominio de aplicación diferente, o bien se serializó en código nativo como un <xref:System.Runtime.InteropServices.GCHandle> pero se volvió a pasar al CLR como un <xref:System.IntPtr>, donde se intentó una conversión.  
  
## <a name="resolution"></a>Resolución  
 Especifique una cookie de <xref:System.IntPtr> válida para el <xref:System.Runtime.InteropServices.GCHandle>.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Cuando se habilita este MDA, el depurador ya no es capaz de realizar un seguimiento de las raíces hasta sus objetos porque los valores de cookie que se pasan son diferentes a los que se devuelven cuando el MDA no está habilitado.  
  
## <a name="output"></a>Salida  
 Se notifica el valor de la cookie de <xref:System.IntPtr> no válida.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>  
 <xref:System.Runtime.InteropServices.GCHandle>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
