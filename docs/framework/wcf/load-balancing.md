---
title: Equilibrio de carga
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
- load balancing [WCF]
ms.assetid: 148e0168-c08d-4886-8769-776d0953b80f
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fe13c4aee41cd7af188ccaea77b3c0af07603e2c
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="load-balancing"></a>Equilibrio de carga
Una manera de aumentar la capacidad de las aplicaciones de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] es escalarlas horizontalmente implementándolas en una granja de servidores con carga equilibrada. Las aplicaciones de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] pueden tener equilibrio de carga mediante técnicas estándar de equilibrio de carga, incluidos los equilibradores de carga de software como Equilibrio de carga de red de Windows junto con dispositivos de equilibrio de carga basados en hardware.  
  
 Las secciones siguientes tratan sobre las consideraciones para las aplicaciones [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] de equilibrio de carga compiladas con varios enlaces proporcionados por el sistema.  
  
## <a name="load-balancing-with-the-basic-http-binding"></a>Equilibrio de carga con el enlace HTTP básico  
 Desde la perspectiva del equilibrio de carga, las aplicaciones de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] que se comunican mediante <xref:System.ServiceModel.BasicHttpBinding> no son diferentes de otros tipos comunes de tráfico de red HTTP (contenido HTML estático, páginas ASP.NET o servicios web de ASMX). Los canales de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] que usan este enlace son sin estados de forma inherente y terminan sus conexiones cuando se cierra el canal. Como tal, <xref:System.ServiceModel.BasicHttpBinding> funciona bien con técnicas de equilibrio de carga de HTTP existentes.  
  
 De forma predeterminada, <xref:System.ServiceModel.BasicHttpBinding> envía un encabezado HTTP de conexión en mensajes con un valor `Keep-Alive`, que permite a los clientes establecer conexiones permanentes a los servicios que las admiten. Esta configuración proporciona un rendimiento mejorado ya que las conexiones previamente establecidas se pueden reutilizar para enviar los mensajes subsiguientes al mismo servidor. Sin embargo, la reutilización de la conexión puede hacer que los clientes se asocien con un servidor concreto dentro de la granja con la carga equilibrada, lo que reduce la eficacia del equilibrio de carga por turnos (round-robin). Si este comportamiento no es adecuado, `Keep-Alive` de HTTP puede estar deshabilitado en el servidor utilizando la propiedad <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> con <xref:System.ServiceModel.Channels.CustomBinding> o <xref:System.ServiceModel.Channels.Binding> definido por el usuario. En el ejemplo siguiente se muestra cómo hacerlo usando la configuración.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
 <system.serviceModel>  
  <services>  
   <service   
     name="Microsoft.ServiceModel.Samples.CalculatorService"  
     behaviorConfiguration="CalculatorServiceBehavior">  
     <host>  
      <baseAddresses>  
       <add baseAddress="http://localhost:8000/servicemodelsamples/service"/>  
      </baseAddresses>  
     </host>  
    <!-- configure http endpoint, use base address provided by host  
         And the customBinding -->  
     <endpoint address=""  
           binding="customBinding"  
           bindingConfiguration="HttpBinding"   
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
   </service>  
  </services>  
  
  <bindings>  
    <customBinding>  
  
    <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
      <binding name="HttpBinding" keepAliveEnabled="False"/>  
  
    </customBinding>  
  </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 Si se usa la configuración simplificada presentada en [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], se puede lograr el mismo comportamiento mediante la siguiente configuración simplificada.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
 <system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="customBinding" />  
    </protocolMapping>  
    <bindings>  
      <customBinding>  
  
      <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
        <binding keepAliveEnabled="False"/>  
  
      </customBinding>  
    </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 Para obtener más información acerca de los puntos de conexión de forma predeterminada, los enlaces y los comportamientos, consulte [configuración simplificada](../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="load-balancing-with-the-wshttp-binding-and-the-wsdualhttp-binding"></a>Equilibrio de carga con los enlaces WSHttp y WSDualHttp  
 <xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.WSDualHttpBinding> pueden tener la carga equilibrada gracias a las técnicas de equilibrio de carga de HTTP siempre que se hagan algunas modificaciones a la configuración de enlace predeterminada.  
  
-   Desactive el establecimiento del contexto de seguridad: puede lograrse definiendo la propiedad <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> de <xref:System.ServiceModel.WSHttpBinding> en `false`. O bien, si son necesarias las sesiones de seguridad, es posible utilizar las sesiones de seguridad con estado, como se describe en el [sesiones seguras](../../../docs/framework/wcf/feature-details/secure-sessions.md) tema. Las sesiones de seguridad con estado permiten al servicio seguir estando sin estado ya que se transmitirá todo el estado para la sesión de seguridad con cada solicitud como parte del token de seguridad de protección. Tenga en cuenta que para habilitar una sesión de seguridad con estado, es necesario utilizar <xref:System.ServiceModel.Channels.CustomBinding> o <xref:System.ServiceModel.Channels.Binding> definido por el usuario ya que no se exponen los valores de configuración necesarios en <xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.WSDualHttpBinding> que son proporcionados por el sistema.  
  
-   No utilice las sesiones confiables. Esta característica está desactivada de forma predeterminada.  
  
## <a name="load-balancing-the-nettcp-binding"></a>Equilibrio de carga del enlace Net.TCP  
 Puede equilibrarse la carga de <xref:System.ServiceModel.NetTcpBinding> mediante técnicas de equilibrio de carga de nivel IP. Sin embargo, <xref:System.ServiceModel.NetTcpBinding> agrupa de forma predeterminada las conexiones TCP para reducir la latencia de conexión. Ésta es una optimización que interfiere con el mecanismo básico del equilibrio de carga. El valor de configuración principal para optimizar <xref:System.ServiceModel.NetTcpBinding> es el tiempo de espera de la concesión, que forma parte de la configuración del grupo de conexiones. La agrupación de conexiones produce conexiones de cliente que se asociarán a servidores concretos dentro de la granja. Como la duración de esas conexiones aumenta (un factor controlado por el valor de tiempo de espera de la concesión), la distribución de carga en varios servidores de la granja pasa a estar sin equilibrar. Como resultado, aumentará el tiempo medio de la llamada. Así, al utilizar <xref:System.ServiceModel.NetTcpBinding> en escenarios con carga equilibrada, considere reducir el tiempo de espera de concesión predeterminado utilizado por el enlace. Un tiempo de espera de concesión de 30 segundos es un punto de inicio razonable para los escenarios con carga equilibrada, aunque el valor óptimo depende de la aplicación. Para obtener más información sobre el tiempo de espera de concesión de canal y otras cuotas de transporte, consulte [las cuotas de transporte](../../../docs/framework/wcf/feature-details/transport-quotas.md).  
  
 Para obtener el máximo rendimiento en escenarios con carga equilibrada, considere utilizar <xref:System.ServiceModel.NetTcpSecurity> (<xref:System.ServiceModel.SecurityMode.Transport> o <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>).  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos recomendados de hospedaje de Internet Information Services](../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
