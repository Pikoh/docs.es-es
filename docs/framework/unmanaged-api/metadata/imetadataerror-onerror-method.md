---
title: "IMetaDataError::OnError (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataError.OnError
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7b8947f0bac8b51e704fbbb9085cf48740b3197d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="0357d-102">IMetaDataError::OnError (Método)</span><span class="sxs-lookup"><span data-stu-id="0357d-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="0357d-103">Proporciona una notificación de errores que se producen durante la combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="0357d-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0357d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0357d-104">Syntax</span></span>  
  
```  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0357d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0357d-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="0357d-106">[in] El valor de error HRESULT devuelto para el método de llamada.</span><span class="sxs-lookup"><span data-stu-id="0357d-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="0357d-107">[in] El token de metadatos del objeto de código que se estaba combinando cuando se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="0357d-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0357d-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0357d-108">Requirements</span></span>  
 <span data-ttu-id="0357d-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0357d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0357d-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0357d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0357d-111">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0357d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0357d-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0357d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0357d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0357d-113">See Also</span></span>  
 [<span data-ttu-id="0357d-114">IMetaDataError (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0357d-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)