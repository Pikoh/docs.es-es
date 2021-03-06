---
title: "Mitigación: validación de esquemas XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9cd5e83da32e32b60f5d1584c7057e36a3851b8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-xml-schema-validation"></a>Mitigación: validación de esquemas XML
En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], la validación de esquemas XSD detecta una infracción de la restricción única si se usa una clave compuesta y una clave está vacía.  
  
## <a name="impact"></a>Impacto  
 El impacto de este cambio debe ser mínimo: según la especificación del esquema, se espera un error de validación de esquema si se infringe `xsd:unique` usando una clave compuesta con una clave vacía.  
  
## <a name="mitigation"></a>Mitigación  
 El hecho de que se detecte un error de validación de esquema si una clave compuesta tiene una clave vacía es una característica configurable:  
  
-   a partir de las aplicaciones que tiene como destino [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], la detección del error de validación de esquema está habilitada de forma predeterminada, aunque se puede optar por no incluirlo, de manera que no se detecte el error.  
  
-   En las aplicaciones que se ejecutan en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] pero que tienen como destino [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] y versiones anteriores, no se detecta ningún error de validación de esquema de forma predeterminada, aunque se puede optar por incluirlo, de manera que se detecte el error.  
  
 Este comportamiento se puede configurar mediante la clase <xref:System.AppContext> para definir el valor del conmutador `System.Xml.IgnoreEmptyKeySequences`. Dado que el valor predeterminado del modificador  es `false` (no se omiten las secuencias de claves vacías), las aplicaciones que tienen como destino [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] pueden optar por no incluir el comportamiento usando el siguiente código para establecer el valor del modificador en `true`:  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 Para las aplicaciones destinadas a [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] y a versiones anteriores, dado que el valor predeterminado del modificador es `true` (se omiten las secuencias de claves vacías), se puede garantizar que una clave compuesta con una clave vacía genera un error de validación de esquema mediante el siguiente código para establecer el valor del modificador en `false`.  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
