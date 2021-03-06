---
title: Publicación y recuperación de metadatos a través de un enlace personalizado
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f6226f01a284a9a24593c1be4fed2f96f3eae730
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="publishing-and-retrieving-metadata-over-a-custom-binding"></a>Publicación y recuperación de metadatos a través de un enlace personalizado
<xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> proporciona soporte para agregar el extremo de metadatos a un servicio. Estos extremos de metadatos pueden responder a solicitudes HTTP GET en una dirección URL que tenga un `?wsdl` querystring y a solicitudes WS-Transfer GET como se define en la especificación WS-MetadataExchange (MEX). Los extremos MEX implementan el contrato <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=nameWithType>.  
  
## <a name="publishing-metadata-over-a-custom-binding"></a>Publicar los metadatos a través de un enlace personalizado  
 Los extremos de metadatos HTTP GET y los extremos de metadatos de HTTPS GET se habilitan estableciendo <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=nameWithType> o las propiedades <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=nameWithType> en `true`. No se pueden configurar los enlaces para estos extremos.  
  
 Sin embargo, el contrato <xref:System.ServiceModel.Description.IMetadataExchange> se puede utilizar con cualquier extremo, incluyendo aquellos que utilizan enlaces personalizados, porque los extremos <xref:System.ServiceModel.Description.IMetadataExchange> son idénticos a cualquier otro extremo de servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Si sabe cómo modificar la configuración de un enlace proporcionado por el sistema, o sabe cómo configurar <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>, puede configurar un enlace para usarlo con un extremo <xref:System.ServiceModel.Description.IMetadataExchange>.  
  
## <a name="retrieving-metadata-over-a-custom-binding"></a>Recuperar los metadatos a través de un enlace personalizado  
 Los metadatos se pueden recuperar de los puntos de conexión de metadatos HTTP Get y HTTPS Get utilizando solicitudes estándares HTTP o HTTPS GET.  
  
 Para recuperar los metadatos de un extremo de metadatos MEX, generalmente puede utilizar uno de los enlaces MEX estándares soportados por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Para obtener más información, consulta <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>. El tipo <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> y la herramienta Svcutil.exe seleccionan automáticamente uno de estos enlaces MEX estándar basándose en la dirección del extremo de metadatos especificado.  
  
 Si un extremo de metadatos MEX utiliza un enlace diferente que uno de los enlaces MEX estándares, puede configurar el enlace utilizado por <xref:System.ServiceModel.Description.MetadataExchangeClient> utilizando código o proporcionando una configuración de extremo de cliente <xref:System.ServiceModel.Description.IMetadataExchange>. La herramienta Svcutil.exe automáticamente carga de su archivo de configuración una configuración de extremo de cliente <xref:System.ServiceModel.Description.IMetadataExchange> que tiene el mismo nombre que el esquema del URI para la dirección del extremo de metadatos.  
  
## <a name="security"></a>Seguridad  
 Al publicar los metadatos a través de un enlace personalizado, asegúrese de que el enlace proporcione el soporte de seguridad que sus metadatos requieren. Por ejemplo, para evitar la divulgación de información y asegurarse de que su cliente tenga el derecho a obtener los metadatos, puede hacer que sus metadatos y su aplicación sean más seguros configurando su extremo <xref:System.ServiceModel.Description.IMetadataExchange> para que requiera autenticación y cifrado. El ejemplo [personalizado extremo de metadatos seguros](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) muestra este escenario.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad de servicios](../../../../docs/framework/wcf/securing-services.md)  
 [Enlaces de WS-MetadataExchange](../../../../docs/framework/wcf/extending/ws-metadataexchange-bindings.md)  
 [Configuración de un enlace de WS-Metadata Exchange personalizado](../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [Recuperación de metadatos mediante un enlace que no sea MEX](../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
