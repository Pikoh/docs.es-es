---
title: "_AxlGetIssuerPublicKeyHash (Función)"
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
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fee2b3e0e74ec13009a9b02d226c6a99b0e2f34b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="axlgetissuerpublickeyhash-function"></a>_AxlGetIssuerPublicKeyHash (Función)
Recupera el hash SHA-1 de la clave pública asociada con la clave privada que se usa para firmar el certificado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pChainContext`  
 [in] Blob de clave pública CSP. Consulte la [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) estructura.  
  
 `ppwszPublicKeyHash`  
 [out] Puntero a WCHAR * para recibir el token de clave pública de codificación hexadecimal.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.  
  
## <a name="see-also"></a>Vea también  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
