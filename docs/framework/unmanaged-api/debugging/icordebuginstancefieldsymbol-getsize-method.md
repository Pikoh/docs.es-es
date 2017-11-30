---
title: "Método ICorDebugInstanceFieldSymbol::GetSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 364144dcef21e7e9c058cb0317970a273aa8ecac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="e2780-102">Método ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="e2780-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="e2780-103">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="e2780-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2780-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2780-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2780-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2780-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="e2780-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="e2780-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2780-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2780-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2780-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e2780-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2780-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2780-109">Requirements</span></span>  
 <span data-ttu-id="e2780-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2780-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2780-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2780-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2780-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2780-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2780-113">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2780-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2780-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2780-114">See Also</span></span>  
 [<span data-ttu-id="e2780-115">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="e2780-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="e2780-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e2780-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)