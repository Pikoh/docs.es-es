---
title: TransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 062b45eb5d627903142ca1a5fd4db6df0855384b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="transportbindingelement"></a>TransportBindingElement
TransportBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase TransportBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase TransportBindingElement tiene las propiedades siguientes:  
  
### <a name="manualaddressing"></a>ManualAddressing  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor booleano que especifica si el usuario toma el control del direccionamiento de mensajes.  
  
### <a name="maxbufferpoolsize"></a>MaxBufferPoolSize  
 Tipo de datos: sint64  
  
 Tipo de acceso: solo lectura  
  
 El tamaño máximo del grupo de búferes para el enlace.  
  
### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize  
 Tipo de datos: sint64  
  
 Tipo de acceso: solo lectura  
  
 El tamaño máximo para un mensaje que es procesado por este enlace.  
  
### <a name="scheme"></a>Scheme  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El esquema URI para el transporte.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.TransportBindingElement>
