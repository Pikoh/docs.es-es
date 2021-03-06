---
title: Comunicación asincrónica
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9cf1cc88f2b9dda0b0f6e155a5d6a465552d6267
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="asynchronous-communication"></a>Comunicación asincrónica
Este ejemplo muestra cómo la comunicación entre dos servicios diferentes de Windows Workflow Foundation (WF) se realiza asincrónicamente de forma predeterminada.  
  
## <a name="demonstrates"></a>Demostraciones  
 Comunicación asincrónica entre servicios de [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  
  
## <a name="discussion"></a>Explicación  
 En este ejemplo se muestra cómo la comunicación entre aplicaciones de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] se realiza de forma asincrónica utilizando las actividades de mensajería proporcionadas por .NET Framework.  
  
 Este ejemplo consta de los tres proyectos siguientes.  
  
 CreditCheckService  
 Este servicio recibe la puntuación crediticia de una persona determinada o el valor del elemento que se va a adquirir y a continuación, decide si la persona recibe el crédito.  
  
 RentalApprovalService  
 Este servicio recibe una solicitud de una persona que necesita crédito. Este servicio se comunica de forma asincrónica con `CreditCheckService` para decidir si la solicitud de crédito es válida.  
  
 Cliente  
 El cliente se comunica sincrónicamente con `RentalApprovalService` para saber si se aprueba el crédito.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Haga clic en el **AsynchronousCommunication** solución y seleccione **propiedades**.  
  
2.  En **propiedades comunes**, seleccione **proyecto de inicio**y seleccione **proyectos de inicio múltiples**.  
  
3.  Mover **RentalApprovalService** a la primera posición en la lista, seguido por **CreditCheckService**, seguido de **cliente**. Establecer el **iniciar** acción en los tres proyectos.  
  
4.  Haga clic en **Aceptar**, y presione F5 para ejecutar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
