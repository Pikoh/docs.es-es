---
title: Publicación de metadatos para un servicio mediante código
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 51407e6d-4d87-42d5-be7c-9887b8652006
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c3d2fd1222539ec8017846069e7eda9a2c503f22
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-publish-metadata-for-a-service-using-code"></a>Publicación de metadatos para un servicio mediante código
Este es uno de los dos temas de instrucciones para la publicación de metadatos para un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Hay dos maneras de especificar cómo debería publicar metadatos un servicio: mediante un archivo de configuración y mediante código. En este tema se muestra cómo publicar metadatos para un servicio mediante código.  
  
> [!CAUTION]
>  En este tema se muestra cómo publicar metadatos de forma no segura. Cualquier cliente puede recuperar los metadatos del servicio. Si el servicio necesita publicar los metadatos de forma segura. vea [extremo de metadatos seguros personalizado](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).  
  
 Para obtener más información acerca de la publicación de metadatos en un archivo de configuración, consulte [Cómo: Publicar metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md). La publicación de metadatos permite a los clientes recuperar los metadatos mediante una solicitud GET WS-Transfer o mediante una solicitud HTTP/GET usando la cadena de solicitud `?wsdl`. Para asegurarse de que el código funciona, debe crear un servicio básico de WCF. En el código siguiente, se proporciona un servicio autohospedado básico.  
  
 [!code-csharp[htPublishMetadataCode#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#0)]
 [!code-vb[htPublishMetadataCode#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#0)]  
  
### <a name="to-publish-metadata-in-code"></a>Publicación de metadatos mediante código  
  
1.  Dentro del método principal de una aplicación de consola, cree instancias de un objeto <xref:System.ServiceModel.ServiceHost> pasando el tipo de servicio y la dirección base.  
  
     [!code-csharp[htPublishMetadataCode#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#1)]
     [!code-vb[htPublishMetadataCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#1)]  
  
2.  Cree un bloque try justo debajo del código del paso 1, esto detecta cualquier excepción que se produzca mientras se está ejecutando el servicio.  
  
     [!code-csharp[htPublishMetadataCode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#2)]
     [!code-vb[htPublishMetadataCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#2)]  
  
     [!code-csharp[htPublishMetadataCode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#3)]
     [!code-vb[htPublishMetadataCode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#3)]  
  
3.  Compruebe si el host del servicio ya contiene un <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, si no, cree una nueva instancia de <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
     [!code-csharp[htPublishMetadataCode#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#4)]
     [!code-vb[htPublishMetadataCode#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#4)]  
  
4.  Establezca la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en `true.`.  
  
     [!code-csharp[htPublishMetadataCode#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#5)]
     [!code-vb[htPublishMetadataCode#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#5)]  
  
5.  El <xref:System.ServiceModel.Description.ServiceMetadataBehavior> contiene una propiedad <xref:System.ServiceModel.Description.MetadataExporter>. El <xref:System.ServiceModel.Description.MetadataExporter> contiene una propiedad <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>. Establezca el valor de la propiedad <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> en <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>. La propiedad <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> también se puede establecer en <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>. Cuando se establece en <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> el exportador de metadatos genera información de la directiva con los metadatos que "se ajusta a WS-Policy 1.5. Cuando se establece en <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>, el exportador de metadatos genera información de directivas conforme a la especificación WS-Policy 1.2.  
  
     [!code-csharp[htPublishMetadataCode#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#6)]
     [!code-vb[htPublishMetadataCode#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#6)]  
  
6.  Agregue la instancia de <xref:System.ServiceModel.Description.ServiceMetadataBehavior> a la colección de comportamientos del host del servicio.  
  
     [!code-csharp[htPublishMetadataCode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#7)]
     [!code-vb[htPublishMetadataCode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#7)]  
  
7.  Agregue el punto de conexión de intercambio de metadatos al host de servicio.  
  
     [!code-csharp[htPublishMetadataCode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#8)]
     [!code-vb[htPublishMetadataCode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#8)]  
  
8.  Agregue un punto de conexión de la aplicación al host de servicio.  
  
     [!code-csharp[htPublishMetadataCode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#9)]
     [!code-vb[htPublishMetadataCode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#9)]  
  
    > [!NOTE]
    >  Si no agrega ningún punto de conexión al servicio, el tiempo de ejecución agregará los puntos de conexión predeterminados. En este ejemplo, dado que el servicio tiene un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> establecido en `true`, el servicio tiene habilitada la publicación de metadatos. Para obtener más información sobre puntos de conexión predeterminados, consulte [configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
9. Abra el host de servicio y espere las llamadas entrantes. Cuando el usuario presione Entrar, cierre el host de servicio.  
  
     [!code-csharp[htPublishMetadataCode#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#10)]
     [!code-vb[htPublishMetadataCode#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#10)]  
  
10. Compile y ejecute la aplicación de consola.  
  
11. Utilice Internet Explorer para ir a la dirección base del servicio (http://localhost:8001/MetadataSample en este ejemplo) y compruebe que la publicación de metadatos está activada. Debería ver una página web que dice "Servicio Simple" en la parte superior y, justo debajo, "Ha creado un servicio". Si no, un mensaje en la parte superior de la página resultante muestra: "La publicación de metadatos para este servicio está deshabilitad actualmente".  
  
## <a name="example"></a>Ejemplo  
 El siguiente código de ejemplo muestra la implementación de un servicio básico de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que publica metadatos para el servicio mediante código.  
  
 [!code-csharp[htPublishMetadataCode#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#11)]
 [!code-vb[htPublishMetadataCode#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#11)]  
  
## <a name="see-also"></a>Vea también  
 [Cómo hospedar un servicio WCF en una aplicación administrada](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)  
 [Probar internamente](../../../../docs/framework/wcf/samples/self-host.md)  
 [Información general de la arquitectura de metadatos](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)  
 [Utilización de los metadatos](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [Publicación de metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
