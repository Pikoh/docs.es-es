---
title: Ciclo de vida de programación básica
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: 36
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ff735a8caf1fbaff636f94eee366b20c33d8f331
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="basic-programming-lifecycle"></a>Ciclo de vida de programación básica
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] permite a las aplicaciones comunicar si están en el mismo equipo, en Internet o en diferentes plataformas de aplicación. En este tema se describen las tareas necesarias para crear una aplicación de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Para una aplicación de ejemplo de trabajo, consulte [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
## <a name="the-basic-tasks"></a>Las tareas básicas  
 Las tareas básicas que se van a realizar son, en orden:  
  
1.  Definir el contrato de servicios. Un contrato de servicio especifica la firma de un servicio, los datos que intercambia y el resto de los datos necesarios contractualmente. Para obtener más información, consulte [diseñar contratos de servicio](../../../docs/framework/wcf/designing-service-contracts.md).  
  
2.  Implementar el contrato. Para implementar un contrato de servicio, cree una clase que implemente el contrato y especifique comportamientos personalizados que deba tener el tiempo de ejecución. Para obtener más información, consulte [implementar contratos de servicio](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
3.  Configurar el servicio especificando los puntos de conexión y el resto de la información de comportamiento. Para obtener más información, consulte [configurar Services](../../../docs/framework/wcf/configuring-services.md).  
  
4.  Hospedar el servicio. Para obtener más información, consulte [servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md).  
  
5.  Compilar una aplicación cliente. Para obtener más información, consulte [creación de clientes](../../../docs/framework/wcf/building-clients.md).  
  
 Aunque los temas de esta sección sigan este orden, algunos escenarios no se inician al principio. Por ejemplo, si desea crear un cliente para un servicio existente, ha de comenzar en el paso 5. O si está creando un servicio que usarán otros, puede omitir el paso 5.  
  
 Una vez que esté familiarizado con el desarrollo de contratos de servicio, también se puede leer [Introducción a la extensibilidad](../../../docs/framework/wcf/introduction-to-extensibility.md). Si tiene problemas con el servicio, consulte [inicio rápido de solución de problemas de WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) para ver si otros usuarios tienen los problemas de iguales o similares.  
  
## <a name="see-also"></a>Vea también  
 [Implementación de contratos de servicio](../../../docs/framework/wcf/implementing-service-contracts.md)
