---
title: '- (Negativo) (Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 2ceedd99221047ab73474ad5dc2478e527618b87
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="--negative-entity-sql"></a>- (Negativo) (Entity SQL)
Devuelve el valor negativo de una expresión numérica.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
- expression  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Expresión válida de cualquier tipo de datos numérico.  
  
## <a name="result-types"></a>Tipos de resultado  
 Tipo de datos de `expression`.  
  
## <a name="remarks"></a>Comentarios  
 Si `expression` es un tipo sin signo, el tipo del resultado será el tipo con signo que más se aproxime al tipo de `expression`. Por ejemplo, si `expression` es de tipo Byte, se devolverá un valor de tipo Int16.  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa el operador aritmético - para devolver el valor negativo de una expresión numérica. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
