---
title: "Validación de cliente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0c1f805-1a81-4d0d-a112-bf5e2e87a631
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bd9c698962bbca04ac05473265d95fc00517b039
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="client-validation"></a>Validación de cliente
Los servicios publican frecuentemente los metadatos para habilitar la generación automática y la configuración de tipos de proxy de cliente. Cuando no se confía en el servicio, las aplicaciones cliente deberían comprobar y validar que los metadatos cumplen con la directiva de la aplicación cliente con respecto a la seguridad, transacciones, el tipo de contrato de servicios etc. El siguiente ejemplo muestra cómo escribir un comportamiento de extremo de cliente que valide el extremo de servicio para asegurarse de que el extremo de servicio puede utilizarse con seguridad.  
  
 El servicio expone cuatro extremos de servicio. El primer extremo utiliza WSDualHttpBinding, el segundo extremo utiliza la autenticación NTLM, el tercer extremo habilita el flujo de la transacción y el cuarto extremo utiliza la autenticación basada en certificados.  
  
 El cliente utiliza la clase <xref:System.ServiceModel.Description.MetadataResolver> para recuperar los metadatos para el servicio. El cliente exige una directiva que prohíba los enlaces dúplex, la autenticación NTLM y el flujo de la transacción mediante un comportamiento que se encargue de validar. Por cada instancia <xref:System.ServiceModel.Description.ServiceEndpoint> importada de los metadatos del servicio, la aplicación cliente agrega una instancia del comportamiento de extremo `InternetClientValidatorBehavior` a <xref:System.ServiceModel.Description.ServiceEndpoint> antes de intentar utilizar un cliente [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para conectarse al extremo. El método `Validate` de comportamiento se ejecuta antes de llamar cualquier operación en el servicio y exige la directiva del cliente iniciando `InvalidOperationExceptions`.  
  
### <a name="to-build-the-sample"></a>Para compilar el ejemplo  
  
1.  Para compilar la solución, siga las instrucciones que aparecen en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>Para ejecutar el ejemplo en el mismo equipo  
  
1.  Abra un símbolo del sistema de Visual Studio con privilegios de administrador y ejecute Setup.bat desde la carpeta de instalación del ejemplo. De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.  
  
2.  Ejecute la aplicación de servicio desde \service\ Debug.  
  
3.  Ejecute la aplicación cliente desde \client\ Debug. La actividad del cliente se muestra en la aplicación de consola del cliente.  
  
4.  Si el cliente y el servicio no se pueden comunicar, consulte [sugerencias de solución de problemas de](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
5.  Quite los certificados ejecutando Cleanup.bat cuando haya finalizado con el ejemplo. Otros ejemplos de seguridad usan los mismos certificados.  
  
### <a name="to-run-the-sample-across-computers"></a>Para ejecutar el ejemplo en varios equipos  
  
1.  En el servidor, en un símbolo del sistema de Visual Studio ejecuta con privilegios elevados, escriba `setup.bat service`. Ejecuta `setup.bat` con el `service` argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service.cer.  
  
2.  En el servidor, edite App.config para reflejar el nuevo nombre del certificado. Es decir, cambiar la `findValue` de atributo en el [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) elemento en el nombre de dominio completo del equipo.  
  
3.  Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.  
  
4.  En el cliente, abra un símbolo del sistema de Visual Studio con privilegios de administrador y escriba `setup.bat client`. Ejecuta `setup.bat` con el `client` argumento crea un certificado de cliente denominado Client.com y exporta el certificado de cliente a un archivo denominado Client.cer.  
  
5.  En el archivo de client.cs cambie el valor de dirección del extremo MEX y `findValue` para establecer el certificado de servidor predeterminado para que coincida con la nueva dirección de su servicio. Para hacerlo, reemplace el host local con el nombre de dominio completo del servidor. Recompile.  
  
6.  Copie el archivo Client.cer del directorio del cliente en el directorio del servicio en el servidor.  
  
7.  En el cliente, ejecute ImportServiceCert.bat en un símbolo del sistema de Visual Studio abierto con privilegios de administrador. Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.  
  
8.  En el servidor, ejecute ImportClientCert.bat en un símbolo del sistema de Visual Studio abierto con privilegios de administrador. De esta forma se importa el certificado del cliente desde el archivo Client.cer al almacén LocalMachine - TrustedPeople.  
  
9. En el equipo del servicio, compile el proyecto de servicio en Visual Studio y ejecute service.exe.  
  
10. En el equipo cliente, ejecute client.exe.  
  
    1.  Si el cliente y el servicio no se pueden comunicar, consulte [sugerencias de solución de problemas de](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo  
  
-   Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.  
  
    > [!NOTE]
    >  Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos. Si ha ejecutado ejemplos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que usan certificados en varios equipos, asegúrese de borrar los certificados del servicio que se hayan instalado en el almacén CurrentUser - TrustedPeople. Para ello, utilice el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>. For example: certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## <a name="see-also"></a>Vea también  
 [Utilización de los metadatos](../../../../docs/framework/wcf/feature-details/using-metadata.md)
