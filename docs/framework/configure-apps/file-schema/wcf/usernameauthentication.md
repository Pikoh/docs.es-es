---
title: '&lt;userNameAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cea18a2c8c2244f384b87b48f195b77da4eb5dfd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltusernameauthenticationgt"></a>&lt;userNameAuthentication&gt;
Especifica las credenciales de un servicio basadas en el nombre de usuario y contraseña.  
  
 \<sistema. ServiceModel >  
\<comportamientos >  
\<serviceBehaviors >  
\<comportamiento >  
\<serviceCredentials >  
\<userNameAuthentication >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<userNameAuthentication  
   cacheLogonTokenLifetime="TimeSpan"  
   cacheLogonTokens="Boolean"   
   customUserNamePasswordValidatorType="String"  
   includeWindowsGroups="Boolean"   
   maxCacheLogonTokens="Integer"  
   membershipProviderName="String"  
   userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<xref:System.TimeSpan> que especifica la duración máxima que un token está almacenado en la memoria caché. El valor predeterminado es 00:15:00.|  
|`cacheLogonTokens`|Un valor booleano que especifica si los tokens de inicio de sesión están almacenados en memoria caché. De manera predeterminada, es `false`.|  
|`customUserNamePasswordValidatorType`|Una cadena que especifica el tipo de validador de contraseña de nombre de usuario personalizado que se va a utilizar. El valor predeterminado es una cadena vacía.|  
|`includeWindowsGroups`|Un valor booleano que especifica si los grupos de Windows están incluidos en el contexto de seguridad. De manera predeterminada, es `true`.<br /><br /> Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa. Establezca esta propiedad en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.|  
|`maxCacheLogonTokens`|Un entero que especifica el número máximo de tokens de inicio de sesión para almacenar en memoria caché. Este valor debería ser mayor que cero. El valor predeterminado es 128.|  
|`membershipProviderName`|Cuando el atributo `clientCredentialType` de un enlace está establecido en `username`, el nombre de usuario está asignado a las cuentas de Windows. Puede invalidar este comportamiento mediante este atributo, que es una cadena que contiene el nombre del valor <xref:System.Web.Security.MembershipProvider> que proporciona el mecanismo de validación de contraseña pertinente.|  
|`userNamePasswordValidationMode`|Especifica la manera en la que se valida la contraseña del nombre de usuario. Los valores válidos son:<br /><br /> -Windows<br />-MembershipProvider<br />-Custom<br /><br /> El valor predeterminado es Windows. Este atributo es del tipo <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.|  
  
## <a name="remarks"></a>Comentarios  
 Si ninguno de los enlaces utilizados por un servicio se configura para la autenticación mediante el nombre de usuario/contraseña, se omiten los atributos para este elemento. Entre estos se incluyen los eventos `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` y `userNamePasswordValidationMode`.  
  
 Si ninguno de los enlaces utilizados por un servicio configurado para utilizar la autenticación de Windows para el nombre de usuario/contraseña, se omite la configuración relacionada con almacenar en memoria caché los tokens de inicio de sesión. Éstos incluyen `cacheLogonTokenLifetime`, `cacheLogonTokens` y `maxCacheLogonTokens`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.UserNameServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
