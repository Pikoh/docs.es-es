---
title: "ICorDebugRemoteTarget::GetHostName (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemoteTarget.GetHostName
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2af5d75145b9fdd2d370b76f798c5e350d8bec50
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugremotetargetgethostname-method"></a>ICorDebugRemoteTarget::GetHostName (Método)
Devuelve el nombre de dominio completo o la dirección IPv4 del equipo de destino de depuración remota. IPV6 no se admite en este momento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cchHostName`  
 [in] Tamaño, en caracteres, del búfer de `szHostName`. Si este parámetros es 0 (cero), `szHostName` debe ser NULL.  
  
 `pcchHostName`  
 [out] Número de caracteres, incluido un terminador nulo, en el nombre de host o dirección IP. Este parámetro puede ser NULL.  
  
 `szHostName`  
 [out] Búfer que contiene el nombre de host o la dirección IP.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 El nombre de host o la dirección IP se devolvieron correctamente.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 No se puede devolver el nombre de host o la dirección IP.  
  
## <a name="remarks"></a>Comentarios  
 Este método lo implementa el programador del depurador. Debe seguir el paradigma de varias llamadas: en la primera llamada, el llamador pasa NULL a `cchHostName` y `szHostName`, y `pcchHostName` devuelve el tamaño del búfer requerido. En la segunda llamada, el tamaño devuelto previamente se pasa en `cchHostName`, y un búfer del tamaño adecuado se pasa en `szHostName`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** 3.5 SP1  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugRemoteTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)