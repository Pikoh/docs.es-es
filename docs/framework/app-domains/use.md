---
title: "Utilizar dominios de aplicación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eade3728c8a51785214cf3d8de53d8a64a668f1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-application-domains"></a>Utilizar dominios de aplicación
Los dominios de aplicación proporcionan una unidad de aislamiento para Common Language Runtime. Se crean y se ejecutan dentro de un proceso. Los dominios de aplicación suele crearlos un host en tiempo de ejecución, que es una aplicación encargada de cargar el tiempo de ejecución en un proceso y ejecutar el código de usuario dentro de un dominio de aplicación. El host en tiempo de ejecución crea un proceso y un dominio de aplicación predeterminado y ejecuta el código administrado dentro de él. Entre los hosts en tiempo de ejecución se incluyen ASP.NET, Microsoft Internet Explorer y el shell de Windows.  
  
 En la mayoría de las aplicaciones, no es necesario que cree su propio dominio de aplicación, ya que el host en tiempo de ejecución crea automáticamente los dominios de aplicación necesarios. A pesar de ello, puede crear y configurar dominios de aplicación adicionales si su aplicación necesita aislar el código o usar y descargar archivos DLL.  
  
## <a name="in-this-section"></a>En esta sección  
 [Crear un dominio de aplicación](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 Describe cómo crear mediante programación un dominio de aplicación.  
  
 [Descargar un dominio de aplicación](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 Describe cómo descargar mediante programación un dominio de aplicación.  
  
 [Configurar un dominio de aplicación](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 Proporciona una introducción a la configuración de un dominio de aplicación.  
  
 [Recuperar información de instalación de un dominio de aplicación](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 Describe cómo recuperar información de instalación de un dominio de aplicación.  
  
 [Cómo: Cargar ensamblados en un dominio de aplicación](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 Describe cómo cargar un ensamblado en un dominio de aplicación.  
  
 [Obtener información sobre tipos y miembros desde un ensamblado](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 Describe cómo recuperar información sobre un ensamblado.  
  
 [Copias sombra de ensamblados](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 Describe la manera en que la creación de instantáneas permite actualizaciones en los ensamblados mientras están en uso y cómo se configura la creación de instantáneas.  
  
 [Recibir notificaciones de excepciones de primera oportunidad](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 Explica cómo se puede recibir una notificación de que se ha producido una excepción antes de que Common Language Runtime empiece a buscar controladores de excepciones.  
  
 [Resolver cargas de ensamblado](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 Proporciona instrucciones sobre cómo usar el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> para resolver errores en la carga de ensamblados.  
  
## <a name="reference"></a>Referencia  
 <xref:System.AppDomain>  
 Representa un dominio de aplicación. Proporciona métodos para crear y controlar dominios de aplicación.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Proporciona información general sobre las funciones que desempeñan los ensamblados.  
  
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 Describe cómo crear, firmar y establecer atributos en los ensamblados.  
  
 [Emitir métodos y ensamblados dinámicos](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 Describe la creación de ensamblados dinámicos.  
  
 [Dominios de aplicación](../../../docs/framework/app-domains/application-domains.md)  
 Proporciona una introducción general a los conceptos de los dominios de aplicación.  
  
 [Información general de la reflexión](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Describe cómo usar la clase **Reflection** para obtener información sobre un ensamblado.
