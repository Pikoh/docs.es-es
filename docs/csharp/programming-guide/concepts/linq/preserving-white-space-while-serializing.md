---
title: Mantener un espacio en blanco al serializar
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: df0ee9bedd4123ac47c06d1c64f305fcf0b0825a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="preserving-white-space-while-serializing"></a>Mantener un espacio en blanco al serializar
En este tema se describe cómo controlar los espacios en blanco a la hora de serializar un árbol XML.  
  
 Un caso muy común es aquel en el que se leen datos XML con sangría, se crea un árbol XML en memoria sin ningún nodo de texto con espacios en blanco (es decir, sin preservar los espacios en blanco), se realizan ciertas operaciones sobre el XML y éste se guarda con sangría. Si se serializa el XML con formato, solo se preservan en el XML aquellos espacios en blanco más significativos. Éste es el comportamiento predeterminado en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Otro escenario muy común es aquel en el que se lee y se modifica código XML en el que se ha aplicado sangría de forma intencionada. Es posible que no desee modificar esta sangría de ninguna forma. Para hacerlo en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], puede preservar los espacios en blanco a la hora de cargar o analizar el XML y si deshabilita el formato cuando serialice el XML.  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a>Tratamiento de los espacios en blanco en los métodos que serializan árboles XML  
 Los siguientes métodos de las clases <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XDocument> serializan un árbol XML. Es posible serializar un árbol XML en un archivo, un <xref:System.IO.TextReader> o un <xref:System.Xml.XmlReader>. El método `ToString` serializa en una cadena.  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=nameWithType>  
  
 Si el método no recibe un <xref:System.Xml.Linq.SaveOptions> como argumento, entonces el método realizará un formato (sangría) del XML serializado. En ese caso, se descartarán todos los espacios en blanco del árbol XML que no sean significativos.  
  
 Si el método toma <xref:System.Xml.Linq.SaveOptions> como argumento, se puede especificar que el método no dé formato (sangría) al XML serializado. En ese caso, se preservarán todos los espacios en blanco del árbol XML.  
  
## <a name="see-also"></a>Vea también  
 [Serializar árboles XML (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
