---
title: "ICorDebugObjectValue::GetFieldValue (Método)"
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
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9fcf53610cf96ef1ab62b4768521e8a2fb7ee6c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>ICorDebugObjectValue::GetFieldValue (Método)
Obtiene el valor del campo especificado de la clase especificada para este valor de objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pClass`  
 [in] Un puntero a un objeto de "ICorDebugClass" que representa la clase para la que se va a obtener el valor del campo.  
  
 `fieldDef`  
 [in] Un `mdFieldDef` símbolo (token) que hace referencia a los metadatos que describen el campo.  
  
 `ppValue`  
 [out] Un puntero a un objeto de "ICorDebugValue" que representa el valor del campo especificado.  
  
## <a name="remarks"></a>Comentarios  
 La clase, especificada en el `pClass` parámetro, debe estar en la jerarquía de clase del valor de objeto, y el campo debe ser un campo de esa clase.  
  
 El `GetFieldValue` método todavía tendrá éxito para objetos genéricos y clases genéricas. Por ejemplo, si MyDictionary\<V > hereda de Dictionary\<string, V >, y el valor del objeto es de tipo MyDictionary\<int32 >, pasando el `ICorDebugClass` objeto de diccionario\<K, V > le Obtenga correctamente un campo del diccionario\<string, int32 >.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
    
 
