---
title: "CorGenericParamAttr (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e40613d790baed5bd89bee1e1f5ca57043bfe76a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corgenericparamattr-enumeration"></a>CorGenericParamAttr (Enumeración)
Contiene valores que describen la <xref:System.Type> parámetros de tipos genéricos, como usan en las llamadas a [IMetaDataEmit2:: DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,   
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,   
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`gpVarianceMask`|La varianza de parámetros solo se aplica a parámetros genéricos para las interfaces y delegados.|  
|`gpNonVariant`|Indica la ausencia de varianza.|  
|`gpCovariant`|Indica la covarianza.|  
|`gpContravariant`|Indica la contravarianza.|  
|`gpSpecialConstraintMask`|Pueden aplicar las restricciones especiales a cualquier <xref:System.Type> parámetro.|  
|`gpNoSpecialConstraint`|Indica que se aplica ninguna restricción a la <xref:System.Type> parámetro.|  
|`gpReferenceTypeConstraint`|Indica que el <xref:System.Type> parámetro debe ser un tipo de referencia.|  
|`gpNotNullableValueTypeConstraint`|Indica que el <xref:System.Type> parámetro debe ser un tipo de valor no puede ser un valor null.|  
|`gpDefaultConstructorConstraint`|Indica que el <xref:System.Type> parámetro debe tener un constructor público predeterminado que no toma ningún parámetro.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
