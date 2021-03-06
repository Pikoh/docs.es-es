---
title: "ICorProfilerInfo::SetEnterLeaveFunctionHooks (Método)"
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
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e41fdf02f299d118fce025e2a5a3314feb134971
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a>ICorProfilerInfo::SetEnterLeaveFunctionHooks (Método)
Especifica las funciones implementadas por el generador de perfiles que se llame en "escriba", "leave" y "tailcall" enlaces de funciones administradas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pFuncEnter`  
 [in] Un puntero a la implementación que se usará como el [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) devolución de llamada.  
  
 `pFuncLeave`  
 [in] Un puntero a la implementación que se usará como el [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) devolución de llamada.  
  
 `pFuncTailcall`  
 [in] Un puntero a la implementación que se usará como el [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) devolución de llamada.  
  
## <a name="remarks"></a>Comentarios  
 En la versión 1.0 de .NET Framework, cada puntero de función puede ser null para deshabilitar esa devolución de llamada correspondiente.  
  
 Solo un conjunto de devoluciones de llamada puede ser activo a la vez. Por lo tanto, si llama a un generador de perfiles las `SetEnterLeaveFunctionHooks` y [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), a continuación, `SetEnterLeaveFunctionHooks2` tiene prioridad.  
  
 El `SetEnterLeaveFunctionHooks` método se puede llamar solo desde el generador de perfiles [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) devolución de llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
