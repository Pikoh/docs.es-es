---
title: "Crear columnas de expresión"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 03c049ea3fb4b0f75418de4f9e8318512c198f41
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="creating-expression-columns"></a>Crear columnas de expresión
Se puede definir una expresión para una columna, a fin de que pueda contener un valor calculado a partir de los valores de otra columna de la misma fila o de los valores de columna de varias filas de la tabla. Para definir la expresión que se va a evaluar, utilice la propiedad <xref:System.Data.DataColumn.Expression%2A> de la columna de destino y la propiedad <xref:System.Data.DataColumn.ColumnName%2A> para hacer referencia a otras columnas en la expresión. El <xref:System.Data.DataColumn.DataType%2A> para la columna de expresión debe ser adecuado para el valor que dicha expresión devuelve.  
  
 En la tabla siguiente se enumeran varios usos posibles de las columnas de expresión de una tabla.  
  
|Tipo de expresión|Ejemplo|  
|---------------------|-------------|  
|Comparación|"Total >= 500"|  
|Cálculo|"UnitPrice * Quantity"|  
|Agregación|Sum(Precio)|  
  
 Puede establecer la **expresión** propiedad existente **DataColumn** objeto, o se puede incluir la propiedad como el tercer argumento pasado a la <xref:System.Data.DataColumn> constructor, tal como se muestra en el ejemplo siguiente.  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 Las expresiones pueden hacer referencia a otras columnas de expresión; sin embargo, una referencia circular, en la que dos expresiones se hacen referencia una a otra, generará una excepción. Para las reglas de escritura de expresiones, vea el <xref:System.Data.DataColumn.Expression%2A> propiedad de la **DataColumn** clase.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [Definición del esquema de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [Objetos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
