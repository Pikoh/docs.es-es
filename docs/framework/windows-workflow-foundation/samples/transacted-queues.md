---
title: Colas de transacción
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1b011dd-5e0b-482c-9bb0-9d8727038f14
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 628e91589ad32a2646316401c7b2ddb31b13eace
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="transacted-queues"></a>Colas de transacción
Este ejemplo muestra cómo integrar colas y transacciones en Windows Workflow Foundation (WF) para crear servicios escalables y fiables. A <!--zz <xref:System.Activities.TransactionScope>--> `System.Activities.TransactionScope` se utiliza en el flujo de trabajo de cliente para enviar mensajes a una cola en una transacción mediante el <xref:System.ServiceModel.NetMsmqBinding>. <xref:System.ServiceModel.Activities.TransactedReceiveScope> se utiliza en el servidor para recibir mensajes de la cola y actualizar el estado del flujo de trabajo en la misma transacción.  
  
## <a name="demonstrates"></a>Demostraciones  
 <xref:System.Activities.Statements.TransactionScope>, <xref:System.ServiceModel.Activities.TransactedReceiveScope>, <xref:System.ServiceModel.NetMsmqBinding>, <xref:System.ServiceModel.Activities.Receive> y correlación basada en contenidos.  
  
## <a name="discussion"></a>Explicación  
 Para mostrar las características incluidas en este ejemplo, se crea un servicio de flujo de trabajo `RewardsPoints` que realiza un seguimiento de los puntos ganados y se utiliza para una cuenta determinada. El cliente utiliza <xref:System.Activities.WorkflowInvoker> para simular el envío de varias solicitudes a la cola. Para mandar por correo un mensaje a la cola en una transacción, la actividad <xref:System.ServiceModel.Activities.Send> se puede colocar dentro de la propiedad <xref:System.Activities.Statements.TransactionScope.Body%2A> de un objeto <xref:System.Activities.Statements.TransactionScope>. En este ejemplo, el cliente se ejecuta primero, seguido del servidor, para mostrar cómo los mensajes en cola pueden desacoplar las aplicaciones servidor y cliente.  
  
 Cuando el cliente se completa, el servicio se configura y se hospeda. En cuanto se abre, comienza el proceso de los mensajes que ya se han colocado en la cola. Cada mensaje se recibe y se procesa bajo la misma transacción del servidor. En este ejemplo, el primer mensaje recibido es una solicitud `CreateAccount` que crea la instancia e inicializa la correlación de contenidos en función del nombre de cuenta pasado como parte del mensaje de solicitud. Para modelar el tipo de servicio que se podría esperar en el mundo real, estas dos actividades <xref:System.ServiceModel.Activities.TransactedReceiveScope> que procesan los mensajes `AddPoints` y `UsePoints` se colocan en bifurcaciones paralelas dentro de un bucle `while` para que puedan procesar repetidamente estos mensajes en cualquier orden.  
  
 Tanto el objeto <xref:System.Activities.Statements.TransactionScope> como <xref:System.ServiceModel.Activities.TransactedReceiveScope> tienen un punto de persistencia implícito al final de sus ámbitos, por lo que el uso de estas actividades en [!INCLUDE[wf1](../../../../includes/wf1-md.md)] combinadas con colas es una manera fiable de mover el flujo de trabajo desde un estado coherente al siguiente y asegurarse al mismo tiempo de que nunca se pierdan los mensajes.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Instale y configure MSMQ. Vea [instalar Message Queue Server](http://go.microsoft.com/fwlink/?LinkId=178526) para obtener más información.  
  
2.  Ejecute el comando siguiente en una línea de comandos para asegurarse de que MSDTC se está ejecutando. `net start msdtc`  
  
3.  Compile el proyecto y abra la aplicación ejecutable o el proyecto en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y seleccione una opción de inicio en el menú de depuración. Primero, se crea la cola; a continuación, el cliente se ejecuta y envía mensajes a la cola y, finalmente, el servicio se inicia y se procesan los mensajes. Para salir del programa, presione Entrar.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedQueues`
