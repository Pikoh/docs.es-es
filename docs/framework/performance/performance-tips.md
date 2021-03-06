---
title: Sugerencias para mejorar el rendimiento de .NET
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- C# language, performance
- performance [C#]
- Visual Basic, performance
- performance [Visual Basic]
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
caps.latest.revision: ''
author: BillWagner
ms.author: wiwagn
manager: wpickett
ms.workload:
- wiwagn
ms.openlocfilehash: ac1f5b9e0897650751320a7f5a9290c378d428b6
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="net-performance-tips"></a>Sugerencias para mejorar el rendimiento de .NET
El término *rendimiento* suele hacer referencia a la velocidad de ejecución de un programa. A veces se puede aumentar la velocidad de ejecución si se siguen algunas reglas básicas en el código fuente. En algunos programas, es importante examinar el código detenidamente y usar generadores de perfiles para asegurarse de que se está ejecutando lo más rápidamente posible. En otros programas, no es necesario realizar esta optimización, ya que el código se ejecuta con una velocidad aceptable mientras se escribe. En este artículo se enumeran algunas áreas donde el rendimiento puede verse afectado y sugerencias para mejorar, así como vínculos a temas de rendimiento adicionales. Para más información sobre cómo planear y medir el rendimiento, vea [Rendimiento](../../../docs/framework/performance/index.md)  
  
## <a name="boxing-and-unboxing"></a>Conversión boxing y conversión unboxing  
 Es mejor evitar el uso de tipos de valor en situaciones en las que se debe aplicar la conversión boxing un gran número de veces, por ejemplo, en las clases de colecciones no genéricas como <xref:System.Collections.ArrayList?displayProperty=nameWithType>. Puede evitar la conversión boxing de tipos de valor mediante el uso de colecciones genéricas como <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>. Las conversiones boxing y unboxing son procesos que consumen muchos recursos. Cuando se aplica la conversión boxing a un tipo de valor, se debe crear un objeto completamente nuevo. Esto puede tardar hasta 20 veces más que la asignación de una referencia simple. Cuando se aplica la conversión unboxing, el proceso de conversión puede tardar cuatro veces más que una asignación. Para obtener más información, vea [Conversión boxing y unboxing](~/docs/csharp/programming-guide/types/boxing-and-unboxing.md).  
  
## <a name="strings"></a>Cadenas  
 Al concatenar un gran número de variables de cadena, por ejemplo en un bucle compacto, use <xref:System.Text.StringBuilder?displayProperty=nameWithType> en lugar del [operador +](~/docs/csharp/language-reference/operators/addition-operator.md) de C# o los [operadores de concatenación](~/docs/visual-basic/language-reference/operators/concatenation-operators.md) de Visual Basic. Para más información, vea [Cómo: Concatenar varias cadenas](../../csharp/how-to/concatenate-multiple-strings.md) y [Operadores de concatenación en Visual Basic](~/docs/visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md).  
  
## <a name="destructors"></a>Destructores  
 No se deben utilizar destructores vacíos. Cuando una clase contiene un destructor, se crea una entrada en la cola Finalize. Cuando se llama al destructor, se invoca al recolector de elementos no utilizados para procesar la cola. Si el destructor está vacío, simplemente se produce una pérdida de rendimiento. Para más información, vea [Destructores](~/docs/csharp/programming-guide/classes-and-structs/destructors.md) y [Duración de los objetos: cómo se crean y destruyen](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
## <a name="other-resources"></a>Otros recursos  
  
-   [Writing Faster Managed Code: Know What Things Cost](http://go.microsoft.com/fwlink/?LinkId=99294) (Escribir código administrado con mayor rapidez: conocer el costo de las cosas)  
  
-   [Writing High-Performance Managed Applications: A Primer](http://go.microsoft.com/fwlink/?LinkId=99295) (Escribir aplicaciones administradas de alto rendimiento: introducción)  
  
-   [Garbage Collector Basics and Performance Hints](http://go.microsoft.com/fwlink/?LinkId=99296) (Conceptos básicos del recolector de elementos no utilizados y sugerencias de rendimiento)  
  
-   [Performance Tips and Tricks in .NET Applications](http://go.microsoft.com/fwlink/?LinkId=99297) (Sugerencias y trucos de rendimiento en aplicaciones .NET)  

-   [Rico Mariani's Performance Tidbits](http://go.microsoft.com/fwlink/?LinkId=115679) (Curiosidades sobre rendimiento de Rico Mariani)  

-   [Blog de Vance](https://blogs.msdn.microsoft.com/vancem/)
  
## <a name="see-also"></a>Vea también  
 [Rendimiento](../../../docs/framework/performance/index.md)  
 [Conceptos de programación](http://msdn.microsoft.com/library/65c12cca-af4f-4017-886e-2dbc00a189d6)  
 [Guía de programación en Visual Basic](../../visual-basic/programming-guide/index.md)  
 [Guía de programación de C#](http://msdn.microsoft.com/library/ac0f23a2-6bf3-4077-be99-538ae5fd3bc5)
