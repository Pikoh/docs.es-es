---
title: UInteger (Tipo de datos)
ms.date: 01/31/2018
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea6d42a604e5a50fab62644034afc82e089792c7
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="uinteger-data-type"></a>UInteger (tipo de datos)

Contiene enteros de 32 bits sin signo (4 bytes) comprendidos entre valor comprendido entre 0 y 4.294.967.295.  
  
## <a name="remarks"></a>Comentarios

 El `UInteger` tipo de datos proporciona el mayor valor sin signo en el ancho de datos más eficaz.  
  
 El valor predeterminado de `UInteger` es 0.  
  
## <a name="literal-assignments"></a>Asignaciones de literales

Puede declarar e inicializar un `UInteger` variable asignarle un decimal literal, un literal hexadecimal, un literal octal, o (a partir de Visual Basic de 2017) un literal binario. Si el literal entero está fuera del intervalo de `UInteger` (es decir, si es inferior a <xref:System.UInt32.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 3 000 000 000 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `UInteger`.
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic de 2017, también puede utilizar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como en el ejemplo siguiente se muestra.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

A partir de Visual Basic 15,5, también puede utilizar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, octales o binarios. Por ejemplo:

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

También pueden incluir literales numéricos el `UI` o `ui` [escriba carácter](../../programming-guide\language-features\data-types/type-characters.md) para denotar el `UInteger` tipo de datos, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>Sugerencias de programación

 El `UInteger` y `Integer` tipos de datos proporcionan un rendimiento óptimo en un procesador de 32 bits, porque los tipos enteros más pequeños (`UShort`, `Short`, `Byte`, y `SByte`), aunque éstos utilicen menos bits, tardan más tiempo en cargar, almacenar y recuperar.  
  
-   **Números negativos.** Dado que `UInteger` es un tipo sin signo, no puede representar un número negativo. Si se utiliza el operador unario menos (`-`) operador en una expresión que se evalúa como tipo `UInteger`, Visual Basic convierte la expresión `Long` primero.  
  
-   **Conformidad con CLS.** El `UInteger` tipo de datos no es parte de la [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código conforme a CLS no puede utilizar un componente que lo utiliza.
  
-   **Consideraciones de interoperabilidad.** Si interactúa con componentes no se han escrito para .NET Framework, por ejemplo objetos de automatización o COM, tenga en cuenta que los tipos como `uint` puede tener un ancho de datos diferente (16 bits) en otros entornos. Al pasar un argumento de 16 bits a esos componentes, declárelo como `UShort` en lugar de `UInteger` en el código administrado de Visual Basic.  
  
-   **De ampliación.** El `UInteger` tipo de datos se amplía a `Long`, `ULong`, `Decimal`, `Single`, y `Double`. Esto significa que se puede convertir `UInteger` a cualquiera de estos tipos sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.  
  
-   **Caracteres de tipo.** Anexar los caracteres de tipo literal `UI` a un literal, se convierte a la `UInteger` tipo de datos. `UInteger`no tiene ningún carácter de tipo identificador.  
  
-   **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt32?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.UInt32>  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
