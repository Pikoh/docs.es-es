---
title: "Cómo: Autenticar con un nombre de usuario y contraseña"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 194a84ef7c2af3bfce6af3625eabf07d4d0b06fb
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a>Cómo: Autenticar con un nombre de usuario y contraseña

Este tema muestra cómo permitir a un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] autenticar un cliente con un nombre de usuario y una contraseña de un dominio de Windows. Se supone que tiene un servicio WCF autohospedado que funciona. Para obtener un ejemplo de creación de un vea servicio hospedado por sí mismo básico de WCF, [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md). En este tema se supone que el servicio se configura en código. Si le gustaría ver un ejemplo de cómo configurar un servicio similar mediante un archivo de configuración vea [nombre de usuario de seguridad de mensaje](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
  
 Para configurar un servicio para autenticar a sus clientes mediante nombre de usuario y contraseñas de dominio Windows, use <xref:System.ServiceModel.WSHttpBinding> y establezca su propiedad `Security.Mode` en `Message`. Además debe especificar un certificado X509 que se usará para cifrar el nombre de usuario y la contraseña que se envían del cliente al servicio.  
  
 En el cliente, debe pedir al usuario el nombre de usuario y la contraseña y especificar las credenciales del usuario en el proxy de cliente de WCF.  
  
## <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a>Para configurar un servicio WCF para la autenticación mediante contraseña y nombre de usuario de dominio de Windows
  
1.  Cree una instancia de <xref:System.ServiceModel.WSHttpBinding>, establezca el modo de seguridad del enlace en `SecurityMode.Message`, establezca el `ClientCredentialType` del enlace en `MessageCredentialType.UserName` y agregue un extremo de servicio usando el enlace configurado al host del servicio tal y como se muestra en el código siguiente:  
  
    ```  
    // ...  
    WSHttpBinding userNameBinding = new WSHttpBinding();  
    userNameBinding.Security.Mode = SecurityMode.Message;  
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;  
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");  
    // ...  
    ```  
  
2.  Especifique el certificado de servidor usado para cifrar la información de nombre de usuario y contraseña enviada a través de la conexión. Este código debe seguir inmediatamente al código anterior. En el ejemplo siguiente se utiliza el certificado que se creó el archivo setup.bat desde la [nombre de usuario de seguridad de mensaje](../../../../docs/framework/wcf/samples/message-security-user-name.md) ejemplo:  
  
    ```  
    // ...  
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");  
    // ...  
    ```  
  
     Puede usar su propio certificado; simplemente modifique el código para hacer referencia al certificado. Para obtener más información sobre la creación y uso de certificados, consulte [trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md). Asegúrese de que el certificado está en el almacén de certificados Personas de confianza del equipo local. Puede hacerlo ejecutando mmc.exe y seleccionando la **archivo**, **agregar o quitar complemento...**  elemento de menú. En el **agregar o quitar complementos** cuadro de diálogo, seleccione la **complemento certificados** y haga clic en **agregar**. En el cuadro de diálogo complemento de certificados seleccione **cuenta de equipo**. De forma predeterminada el certificado generado por el ejemplo de Nombre de usuario de seguridad de mensaje se encuentra en la carpeta Personal/Certificados.  Se enumerarán como "localhost" en la columna emitido para en la ventana de MMC. Arrastre y coloque el certificado en el **personas de confianza** carpeta. Esto permitirá a WCF tratar el certificado como certificado de confianza al realizar la autenticación.  
  
## <a name="to-call-the-service-passing-username-and-password"></a>Para llamar al servicio pasando el nombre de usuario y la contraseña  
  
1.  La aplicación cliente debe pedir al usuario su nombre de usuario y contraseña. El siguiente código pide al usuario el nombre de usuario y la contraseña.  
  
    > [!WARNING]
    >  Este código no se debe usar en producción porque se muestra la contraseña mientras se está escribiendo.  
  
    ```  
    public static void GetPassword(out string username, out string password)  
            {  
                Console.WriteLine("Provide a valid machine or domain account. [domain\\user]");  
                Console.WriteLine("   Enter username:");  
                username = Console.ReadLine();  
                Console.WriteLine("   Enter password:");  
                password = Console.ReadLine();             
                return;  
            }  
    ```  
  
2.  Cree una instancia del proxy de cliente que especifique las credenciales del cliente tal y como se muestra en el código siguiente:  
  
    ```  
    string username;  
    string password;  
  
    // Instantiate the proxy  
    Service1Client proxy = new Service1Client();  
  
    // Prompt the user for username & password  
    GetPassword(out username, out password);  
  
    // Set the user’s credentials on the proxy  
    proxy.ClientCredentials.UserName.UserName = username;  
    proxy.ClientCredentials.UserName.Password = password;  
  
    // Treat the test certificate as trusted  
    proxy.ClientCredentials.ServiceCertificate.Authentication.CertificateValidationMode = System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust;  
    // Call the service operation using the proxy  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.WSHttpBinding>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.SecurityMode>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>  
 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>  
 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>  
 [Seguridad del transporte con la autenticación básica](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 [Seguridad distribuida de aplicaciones](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
