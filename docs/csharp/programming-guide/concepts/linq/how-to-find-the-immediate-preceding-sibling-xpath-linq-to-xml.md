---
title: "Cómo: Buscar el nodo del mismo nivel inmediatamente anterior (XPath-LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 74c06201-0b1b-4b5e-b3ac-0092980614e6
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 88a27b15fb46651d5a4c3a8e2ac8a357b600dec2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-c"></a>Cómo: Buscar el nodo del mismo nivel inmediatamente anterior (XPath-LINQ to XML) (C#)
Es posible que en alguna ocasión desee buscar el elemento del mismo nivel inmediatamente anterior a un nodo. Debido a las diferencias de semántica de los predicados posicionales para los ejes de los elementos del mismo nivel anteriores de XPath en comparación con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], ésta es una de las comparaciones más interesantes.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la consulta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] usa el operador <xref:System.Linq.Enumerable.Last%2A> para buscar el último nodo de la recopilación devuelto por <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>. Por el contrario, la expresión XPath usa un predicado con un valor de 1 para buscar el elemento inmediatamente anterior.  
  
```csharp  
XElement root = XElement.Parse(  
    @"<Root>  
    <Child1/>  
    <Child2/>  
    <Child3/>  
    <Child4/>  
</Root>");  
XElement child4 = root.Element("Child4");  
  
// LINQ to XML query  
XElement el1 =  
    child4  
    .ElementsBeforeSelf()  
    .Last();  
  
// XPath expression  
XElement el2 =  
    ((IEnumerable)child4  
                 .XPathEvaluate("preceding-sibling::*[1]"))  
                 .Cast<XElement>()  
                 .First();  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Results are identical  
<Child3 />  
```  
  
## <a name="see-also"></a>Vea también  
 [LINQ to XML para usuarios de XPath (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
