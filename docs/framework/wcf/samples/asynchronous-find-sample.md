---
title: Ejemplo de búsqueda asincrónica
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a713a25-c1f4-42e1-8c4a-93d64ca45a3b
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1545791eceae6d4651ca5299a84623466e8b4976
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="asynchronous-find-sample"></a>Ejemplo de búsqueda asincrónica
En este ejemplo se muestra cómo utilizar la operación de búsqueda asincrónica desde una aplicación cliente.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 La ventaja de seguir este patrón de diseño es que se notifica al cliente de forma asincrónica los extremos situados como resultado de la solicitud de búsqueda. Para ver cómo funciona, abra el archivo Client.cs. Observe que el objeto <xref:System.ServiceModel.Discovery.DiscoveryClient> tiene dos delegados adjuntados a sus controladores de eventos. Se llama a un delegado cuando se genera un evento <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> y a otro cada vez que se provoca un evento <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>. El ejemplo muestra cómo puede utilizar este patrón en su aplicación.  
  
> [!NOTE]
>  Este ejemplo utiliza los puntos de conexión HTTP y, para ejecutarlo, se deben agregar las ACL de dirección URL apropiadas. Para obtener más información, consulte [configurar HTTP y HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md). Al ejecutar el siguiente comando con privilegios elevados, se deberían agregar las ACL adecuadas. Puede que desee sustituir su dominio y nombre de usuario para los siguientes argumentos si el comando no funciona como debería. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra AsyncFind.sln.  
  
2.  Presione Ctrl+MAYÚS+B para compilar la solución.  
  
3.  Abra un símbolo del sistema de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], navegue hasta el directorio \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug o \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug, y ejecute Service.exe.  
  
4.  Una vez iniciado el servicio, navegue al directorio \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug o WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug, y ejecute Client.exe.  
  
5.  Observe que el cliente puede localizar y llamar al servicio.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\AsyncFind`  
  
## <a name="see-also"></a>Vea también
