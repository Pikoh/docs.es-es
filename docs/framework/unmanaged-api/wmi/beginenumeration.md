---
title: "Función de BeginEnumeration (referencia de API no administrada)"
description: "La función BeginEnumeration restablece el enumerador al principio de la enumeración"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 90c3e8448a61145290ea4a75b1d38f7ae010cb9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="beginenumeration-function"></a>BeginEnumeration (función)
Restablece el enumerador hasta el principio de la enumeración.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro no se utiliza.

`ptr`[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.

`lEnumFlags`  
[in] Una combinación bit a bit de los indicadores o valores que se describen en la [comentarios](#remarks) sección que controla las propiedades incluidas en la enumeración.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | La combinación de los indicadores de `lEnumFlags` no es válido o no válido se especificó el argumento. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Una segunda llamada a `BeginEnumeration` se realizó sin una llamada intermedia a [ `EndEnumeration` ](endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para iniciar una nueva enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) método.

Las marcas que se pueden pasar como el `lEnumFlags` argumento se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código.  Puede combinar una marca de todos los grupos con cualquier marca de ningún otro grupo. Sin embargo, las marcas del mismo grupo son mutuamente excluyentes. 

**Grupo 1**

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0 x 4 | Incluyen propiedades que constituyen la clave solo. |
|`WBEM_FLAG_REFS_ONLY` | 0 x 8 | Incluyen propiedades que son las referencias de objeto. |

**Grupo 2**

Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0 x 30 | Limitar la enumeración de propiedades del sistema solo. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0 x 40 | Incluir propiedades locales y propagadas pero excluir propiedades del sistema de la enumeración. |

Para las clases:

Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0 x 100 | Limitar la enumeración de propiedades que se reemplaza en la definición de clase. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0 x 100 | Limitar la enumeración de propiedades que se reemplaza en la definición de clase actual y a nuevas propiedades definidas en la clase. |
| `WBEM_MASK_CLASS_CONDITION` | 0 x 300 | Una máscara (en lugar de una marca) se aplican a un `lEnumFlags` valor para comprobar si el valor `WBEM_FLAG_CLASS_OVERRIDES_ONLY` o `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` se establece. |
| `WBEM_FLAG_LOCAL_ONLY` | 0 x 10 | Limitar la enumeración de propiedades que define o modifica en la propia clase. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0 x 20 | Limitar la enumeración de propiedades que se heredan de clases base. |

Para instancias:

Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0 x 10 | Limitar la enumeración de propiedades que define o modifica en la propia clase. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0 x 20 | Limitar la enumeración de propiedades que se heredan de clases base. |


## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
