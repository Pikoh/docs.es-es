---
title: "ICorDebugManagedCallback::EvalException (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.EvalException
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ed64c7b28d60e966e836ac75e6dd7c0848304a38
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="bc385-102">ICorDebugManagedCallback::EvalException (Método)</span><span class="sxs-lookup"><span data-stu-id="bc385-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="bc385-103">Notifica al depurador que una evaluación ha finalizado con una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="bc385-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc385-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc385-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc385-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc385-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="bc385-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que ha finalizado la evaluación.</span><span class="sxs-lookup"><span data-stu-id="bc385-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="bc385-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que ha finalizado la evaluación.</span><span class="sxs-lookup"><span data-stu-id="bc385-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="bc385-108">[in] Un puntero a un objeto ICorDebugEval que representa el código que realiza la evaluación.</span><span class="sxs-lookup"><span data-stu-id="bc385-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc385-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc385-109">Requirements</span></span>  
 <span data-ttu-id="bc385-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc385-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc385-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc385-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc385-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc385-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc385-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc385-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc385-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc385-114">See Also</span></span>  
 [<span data-ttu-id="bc385-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc385-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)