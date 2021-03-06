---
title: "Ejemplo de detección con ámbitos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a37a754-6b8c-4ebe-bdf2-d4f0520271d5
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa762df1dbfe92102f8cd719613099b23986ed0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="discovery-with-scopes-sample"></a>Ejemplo de detección con ámbitos
Este ejemplo muestra cómo utilizar los ámbitos para clasificar los extremos detectables además de cómo utilizar <xref:System.ServiceModel.Discovery.DiscoveryClient> para realizar una búsqueda asincrónica de los extremos. En el servicio, este ejemplo muestra cómo personalizar la detección de cada punto de conexión agregando un comportamiento de detección de punto de conexión y utilizándolo para agregar un ámbito al punto de conexión así como controlando la detectabilidad del punto de conexión. En el cliente, el ejemplo revisa el modo en que los clientes pueden crear un <xref:System.ServiceModel.Discovery.DiscoveryClient> y ajustar los parámetros de búsqueda para incluir ámbitos agregándolos a <xref:System.ServiceModel.Discovery.FindCriteria>. Este ejemplo también muestra el modo en que los clientes pueden restringir las respuestas agregando un criterio de terminación.  
  
## <a name="service-features"></a>Características de servicio  
 Este proyecto muestra dos extremos de servicio que se agregan a un <xref:System.ServiceModel.ServiceHost>. Cada extremo tiene un <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> asociado. Este comportamiento se utiliza para agregar los ámbitos del URI para ambos puntos de conexión. Los ámbitos se utilizan para distinguir cada uno de estos puntos de conexión para que los clientes puedan ajustar la búsqueda. Para el segundo extremo, la detectabilidad puede deshabilitarse estableciendo la propiedad <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Enabled%2A> en `false`. De este modo se asegura de que los metadatos de detección asociados a este punto de conexión no se envían como parte de ningún mensaje de detección.  
  
## <a name="client-features"></a>Características de cliente  
 El método `FindCalculatorServiceAddress()` muestra cómo utilizar <xref:System.ServiceModel.Discovery.DiscoveryClient> y pasarlo en un <xref:System.ServiceModel.Discovery.FindCriteria> con dos restricciones. Un ámbito se agrega a los criterios y la propiedad <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> se establece en 1. El ámbito limita los resultados solo a los servicios que publican el mismo ámbito. Al establecer <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> en 1, se limitan las respuestas que el <xref:System.ServiceModel.Discovery.DiscoveryClient> espera a un extremo, como máximo. La llamada a <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> es una operación sincrónica que bloquea el subproceso hasta que se alcance un tiempo de espera o se encuentre un extremo.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Este ejemplo utiliza los puntos de conexión HTTP y para ejecutarlo, se deben agregar las ACL de dirección URL apropiadas. Vea [configurar HTTP y HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) para obtener más información. Al ejecutar el siguiente comando con privilegios elevados, se deberían agregar las ACL adecuadas. Puede que desee sustituir su dominio y nombre de usuario para los siguientes argumentos si el comando no funciona como debería: `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2.  Compile la solución.  
  
3.  Ejecute el ejecutable de servicio desde el directorio de compilación.  
  
4.  Ejecute la aplicación cliente. Observe que el cliente puede localizar el servicio.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryWithScopes`  
  
## <a name="see-also"></a>Vea también
