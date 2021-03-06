---
title: "CreateDebuggingInterfaceFromVersion (Función)"
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
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b3f269f5b1758481995d6064e7137e62bff4a868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="createdebugginginterfacefromversion-function"></a>CreateDebuggingInterfaceFromVersion (Función)
Crea un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) objeto basándose en la información de versión especificada.  
  
 Esta función está obsoleta en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. En su lugar, para obtener una interfaz de common language runtime (CLR) 2.0, use la [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) método y especifique el identificador de clase CLSID_CLRDebuggingLegacy y el identificador de interfaz IID_ICorDebug. Para obtener una interfaz CLR 4 o versiones posteriores, llame a la [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) función y especificar el identificador de clase CLSID_CLRDebugging y el identificador de interfaz IID_ICLRDebugging.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `iDebuggerVersion`  
 [in] La versión de `ICorDebug` que se espera que el depurador. Consulte la [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeración para los valores válidos.  
  
 `szDebuggeeVersion`  
 [in] En tiempo de ejecución versión de common language asociada a la aplicación o el proceso que desea depurar. Consulte la [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) o [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) método para obtener información sobre cómo recuperar este valor.  
  
 `ppCordb`  
 [out] La ubicación que recibe un puntero a la `ICorDebug` objeto.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los códigos de error COM estándar, tal como se define en el archivo WinError.h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`szDebuggeeVersion`o `ppCordb` es nulo o la versión de cadena no es correcta.|  
  
## <a name="remarks"></a>Comentarios  
 El `szDebuggeeVersion` parámetro se asigna a la correspondiente versión de MSCorDbi.dll.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
