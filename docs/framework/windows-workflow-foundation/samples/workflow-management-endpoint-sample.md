---
title: Ejemplo de punto de conexión de administración de flujo de trabajo
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 558591cb645de9591fd0ac770061a5fb8825d21d
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="workflow-management-endpoint-sample"></a>Ejemplo de punto de conexión de administración de flujo de trabajo
En este ejemplo se muestra cómo un punto de conexión de control de flujo de trabajo se puede utilizar para crear y ejecutar flujos de trabajo de forma local y remota. En el ejemplo se muestra cómo hospedar un extremo de control y cómo escribir clientes que llamen al extremo de control para crear y ejecutar la instancia de un flujo de trabajo. El flujo de trabajo no es un servicio.  
  
 En el lado del servicio del ejemplo un flujo de trabajo se hospeda con WorkflowServiceHost y se agrega un WorkflowControlEndpoint de modo que los clientes puedan realizar operaciones de control (Suspend, Start, etc.). También se agrega un CreationEndpoint definido por el usuario para permitir la creación del flujo de trabajo. El servicio usará posteriormente estos extremos para iniciar el flujo de trabajo en un estado suspendido y después reanudar el flujo de trabajo. El cliente realiza las mismas operaciones pero desde el código de cliente. Para obtener más información acerca de estas interfaces, vea [extremo de Control de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) y [Cómo: hospedar un flujo de trabajo no pertenecientes al servicio en IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Ejecute [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con privilegios de administrador.  
  
2.  Abra la solución ManagementEndpoint.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Para compilar la solución, presione CTRL + MAYÚS + B o seleccione **generar solución** desde el **generar** menú.  
  
4.  Inicie la aplicación ManagementEndpoint.exe.  
  
5.  Inicie la aplicación Client.exe.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`