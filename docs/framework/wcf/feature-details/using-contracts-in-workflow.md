---
title: Utilizar contratos en flujo de trabajo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ff40241bd48a4355738ca93ef2c80ceec55db11
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-contracts-in-workflow"></a>Utilizar contratos en flujo de trabajo
Al implementar un servicio, defina varios contratos que describan el servicio y los datos que envía y recibe. Los datos se representan como contratos de datos y de mensajes; los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y de flujo de trabajo usan datos de contrato y definiciones de contrato de mensaje como parte de las descripciones del servicio. El servicio expone metadatos (en el formulario de WSDL) para describir las operaciones del servicio. En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], los contratos de servicios y los contratos de operación definen el servicio y las operaciones que admite. Sin embargo, en un servicio de flujo de trabajo, estos contratos forman parte del propio proceso de negocio; se exponen en metadatos mediante un proceso llamado inferencia del contrato.  
  
## <a name="contract-inference"></a>Inferencia del contrato  
 Cuando un servicio de flujo de trabajo se hospeda mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>, se examina la definición de flujo de trabajo y se genera un contrato en función del conjunto de actividades de mensajería presentes en el flujo de trabajo. En especial, se emplean las siguientes actividades y propiedades para generar el contrato:  
  
 Actividad <xref:System.ServiceModel.Activities.Receive>  
  
-   <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
-   <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
-   <xref:System.ServiceModel.Activities.Receive.Action%2A>   
 
 Actividad <xref:System.ServiceModel.Activities.SendReply>  
  
-   <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 Actividad <xref:System.ServiceModel.Activities.TransactedReceiveScope>  
  
 El resultado final de inferencia del contrato es una descripción del servicio mediante las mismas estructuras de datos que el servicio de WCF y los contratos de operación. A continuación, esta información se utiliza para exponer WSDL para el servicio de flujo de trabajo.  
  
## <a name="see-also"></a>Vea también  
 [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Actividades de mensajería](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 [Creación de un servicio de flujo de trabajo con actividades de mensajería](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 [Cómo crear un servicio de flujo de trabajo que consuma un contrato de servicio existente](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
