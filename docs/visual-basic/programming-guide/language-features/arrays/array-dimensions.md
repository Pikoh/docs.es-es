---
title: Dimensiones de matrices en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21e170ca5942862a26e05428fffaea7d1e875e19
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="array-dimensions-in-visual-basic"></a>Dimensiones de matrices en Visual Basic
A *dimensión* es una dirección en la que puede variar la especificación de elementos de la matriz. Una matriz que contiene las ventas totales para cada día del mes tiene una dimensión (el día del mes). Una matriz que contiene las ventas totales por departamento para cada día del mes tiene dos dimensiones (el número de departamento y el día del mes). El número de dimensiones tiene una matriz se denomina su *rango*.  
  
> [!NOTE]
>  Puede usar el <xref:System.Array.Rank%2A> propiedad para determinar el número de dimensiones de una matriz tiene.  
  
## <a name="working-with-dimensions"></a>Trabajar con dimensiones  
 Especifica un elemento de una matriz al proporcionar una *índice* o *subíndice* para cada una de sus dimensiones. Los elementos son contiguos en cada dimensión, desde el índice 0 hasta el índice más alto para esa dimensión.  
  
 Las ilustraciones siguientes muestran la estructura conceptual de matrices con rangos diferentes. Cada elemento de las ilustraciones muestra los valores de índice que tienen acceso a él. Por ejemplo, puede tener acceso el primer elemento de la segunda fila de la matriz bidimensional especificando los índices `(1, 0)`.  
  
 ![Diagrama gráfico de una ventana de &#45; matriz dimensional](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")  
Matriz unidimensional  
  
 ![Diagrama gráfico de dos &#45; matriz dimensional](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")  
matriz bidimensional  
  
 ![Diagrama gráfico de tres &#45; matriz dimensional](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")  
matriz tridimensional  
  
### <a name="one-dimension"></a>Una dimensión  
 Muchas matrices tienen sólo una dimensión, como el número de personas de cada edad. El único requisito para especificar un elemento es la edad para los que ese elemento contiene el recuento. Por lo tanto, este tipo de matriz utiliza sólo un índice. En el ejemplo siguiente se declara una variable que contenga una *matriz unidimensional* de edad recuentos de edades de 0 a 120.  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a>Dos dimensiones  
 Algunas matrices tienen dos dimensiones, como el número de oficinas de cada planta de todos los edificios de un campus. La especificación de un elemento requiere el número de edificio y el límite inferior, y cada elemento contiene el recuento para esa combinación de edificio y piso. Por lo tanto, este tipo de matriz utiliza dos índices. En el ejemplo siguiente se declara una variable que contenga una *matriz bidimensional* de recuentos de office, de 0 a 40 edificios y 0 a 5 plantas.  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 Una matriz bidimensional también se denomina un *matriz rectangular*.  
  
### <a name="three-dimensions"></a>Tres dimensiones  
 Algunas matrices tienen tres dimensiones, como los valores en un espacio tridimensional. Este tipo de matriz utiliza tres índices, que en este caso, representan el x, y y coordenadas z de espacio físico. En el ejemplo siguiente se declara una variable que contenga una *matriz tridimensional* de temperatura del aire en diversos puntos en un volumen tridimensional.  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a>Más de tres dimensiones  
 Aunque una matriz puede tener como máximo 32 dimensiones, es raro que tenga más de tres.  
  
> [!NOTE]
>  Cuando se agregan dimensiones a una matriz, el espacio total necesario para la matriz aumenta considerablemente, por lo que utilice las matrices multidimensionales con cuidado.  
  
## <a name="using-different-dimensions"></a>El uso de dimensiones diferentes  
 Suponga que desea realizar un seguimiento de los importes de ventas para todos los días del mes actual. Puede declarar una matriz unidimensional con 31 elementos, uno para cada día del mes, como en el ejemplo siguiente se muestra.  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 Ahora suponga que desea realizar un seguimiento de la misma información no sólo para todos los días del mes sino también para todos los meses del año. Puede declarar una matriz bidimensional con 12 filas (para los meses) y 31 columnas (para los días), como se muestra en el ejemplo siguiente.  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 Ahora suponga que decide que la matriz contienen información durante más de un año. Si desea realizar un seguimiento de los importes de ventas durante 5 años, podría declarar una matriz tridimensional con 5 capas, 12 filas y 31 columnas, como se muestra en el ejemplo siguiente.  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 Tenga en cuenta que, dado que cada índice varía entre 0 en su valor máximo, cada dimensión de `salesAmounts` se declara como uno menos que la longitud necesaria para esa dimensión. Tenga en cuenta también que el tamaño de la matriz aumenta con cada nueva dimensión. Los tres tamaños en los ejemplos anteriores son 31, 372 y 1.860 elementos respectivamente.  
  
> [!NOTE]
>  Puede crear una matriz sin utilizar la `Dim` instrucción o `New` cláusula. Por ejemplo, puede llamar a la <xref:System.Array.CreateInstance%2A> método u otro componente puede pasar el código de una matriz creada de esta manera. Este tipo de matriz puede tener un límite inferior distinto de 0. Siempre puede probar el límite inferior de una dimensión mediante la <xref:System.Array.GetLowerBound%2A> método o la `LBound` función.  
  
## <a name="see-also"></a>Vea también  
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Solución de problemas de matrices](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
