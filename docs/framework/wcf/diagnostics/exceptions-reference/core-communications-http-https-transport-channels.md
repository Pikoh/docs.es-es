---
title: "Comunicaciones básicas: Canales de transporte HTTP-HTTPS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c0a23c9-a663-461c-bdab-58b4d3e23642
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d67bb810ced381749dca0dc698ca405bb59cfb0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="core-communications-httphttps-transport-channels"></a>Comunicaciones básicas: canales de transporte HTTP/HTTPS
Este tema enumera todas las excepciones generadas por los canales de transporte HTTP/HTTPS de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|DigestExplicitCredsImpersonationLevel|Se especificó el nivel de suplantación especificado. La autenticación implícita del HTTP solo admite el nivel de 'Suplantación' cuando se utiliza con una credencial explícita.|  
|FramingContentTypeMismatch|El tipo de contenido especificado no lo admitió el servicio especificado. Los enlaces de servicio y cliente puede que no coincidan.|  
|Hosting_SslSettingsMisconfigured|Los valores de Secure Sockets Layer para el servicio especificado no coinciden con los de Internet Information Services.|  
|HttpAuthSchemeAndClientCert|El generador de agentes de escucha de HTTPS se configuró para que requiera un certificado de cliente y el esquema de autenticación especificado. Sin embargo, solo se puede requerir una forma de autenticación de cliente al mismo tiempo.|  
|HttpReceiveFailure|Un error ocurrido al recibir la respuesta HTTP en lo especificado. El enlace del extremo de servicio puede que no use el protocolo HTTP. Otra posibilidad es que el servidor terminase un contexto de solicitud HTTP debido a un cierre del servicio. Vea los registros del servidor para obtener más detalles.|  
|HttpRegistrationAccessDenied|HTTP no puede registrar la Dirección URL especificada. Su proceso no tiene los derechos de acceso a este espacio de nombres (consulte http://msdn.microsoft.com/library/default.asp?url=/library/http/http/namespace_reservations_registrations_and_routing.asp para obtener información detallada).|  
|HttpRegistrationAlreadyExists|HTTP no puede registrar la Dirección URL especificada. Otra aplicación ya registró esta dirección URL con HTTP.SYS.|  
|HttpRegistrationPortInUse|HTTP no puede registrar la dirección URL especificada porque otra aplicación está utilizando el puerto TCP especificado.|  
|HttpSendFailure|Un error producido al realizar la solicitud HTTP a los especificados. Asegúrese de que la causa no es la no coincidencia de los enlaces de seguridad. Asegúrese también de que el servicio no se configura para Secure Sockets Layer.|  
|MessageXmlProtocolError|Un problema se produjo con el XML que se recibió de la red. Vea la excepción interna para obtener más detalles.|  
|MissingContentType|El receptor devolvió un error que indica que el tipo de contenido faltaba en la solicitud a los especificados. Consulte la excepción interna para obtener más información.|  
|ProxyAuthenticationLevelMismatch|La credencial de autenticación del proxy HTTP especificó un requisito de autenticación mutua que es más estricto que el requisito para la autenticación del servidor de destino.|  
|ProxyImpersonationLevelMismatch|La credencial de autenticación del proxy HTTP especificó una restricción del nivel de suplantación que es más estricta que la restricción para la autenticación del servidor de destino.|  
|SecureChannelFailure|Un canal seguro no se puede establecer para Secure Socket Layer/Transport Layer Security con la autoridad especificada.|  
|TrustFailure|No se puede establecer una relación de confianza para el canal seguro de Secure Socket Layer/Transport Layer Security con la autoridad especificada.|  
|UseDefaultWebProxyCantBeUsedWithExplicitProxyAddress|No puede especificar una dirección proxy explícita ni UseDefaultWebProxy=true en su elemento HttpTransportBinding.|
