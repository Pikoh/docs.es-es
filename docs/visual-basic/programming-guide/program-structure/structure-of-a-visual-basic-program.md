---
title: Estructura de un programa de Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5def0de1e22af39eb16489a2d4d27bdbd1853f2b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="structure-of-a-visual-basic-program"></a>Estructura de un programa de Visual Basic
Un programa de Visual Basic se componen de bloques de creación estándar. A *solución* consta de uno o varios proyectos. A *proyecto* a su vez puede contener uno o más ensamblados. Cada *ensamblado* se compila a partir de uno o varios archivos de origen. A *archivo de código fuente* proporciona la definición e implementación de clases, estructuras, módulos y las interfaces, que en última instancia contienen todo el código.  
  
 Para obtener más información acerca de estos bloques de creación de un programa de Visual Basic, consulte [soluciones y proyectos](/visualstudio/ide/solutions-and-projects-in-visual-studio) y [ensamblados y la caché Global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
## <a name="file-level-programming-elements"></a>Elementos de programación de nivel de archivo  
 Cuando se inicia un proyecto o archivo y abre el editor de código, vea parte del código ya están en vigor y en el orden correcto. Cualquier código que escriba debe seguir la secuencia siguiente:  
  
1.  `Option` Instrucciones  
  
2.  `Imports` Instrucciones  
  
3.  `Namespace` instrucciones y los elementos de nivel de espacio de nombres  
  
 Si escribe instrucciones en un orden diferente, pueden dar lugar a errores de compilación.  
  
 Un programa también puede contener instrucciones de compilación condicional. Puede incluirse en el archivo de código fuente entre las instrucciones de la secuencia anterior.  
  
### <a name="option-statements"></a>Instrucciones de la opción  
 `Option` las instrucciones establecen reglas de base para el código subsiguiente, ayudando a evitar errores de sintaxis y la lógica. El [instrucción Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md) garantiza que todas las variables se declaran y ha escrito correctamente, lo que reduce el tiempo de depuración. El [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md) ayuda a minimizar la pérdida de datos y errores de lógica que puede producirse al trabajar entre variables de diferentes tipos de datos. El [instrucción Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) especifica que se comparan las cadenas de manera entre sí, en función de sus `Binary` o `Text` valores.  
  
### <a name="imports-statements"></a>Instrucciones Imports  
 Puede incluir un [Imports (instrucción Namespace de .NET y tipo)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para importar nombres definidos fuera del proyecto. Un `Imports` instrucción permite que el código hacer referencia a las clases y otros tipos definidos en el espacio de nombres importado, sin tener que calificarlos. Puede utilizar tantas `Imports` instrucciones según corresponda. Para obtener más información, consulte [referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).  
  
### <a name="namespace-statements"></a>Instrucciones Namespace  
 Espacios de nombres le ayudarán a organiza y clasificar los elementos de programación para facilitar la agrupación y el acceso. Usa el [instrucción Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md) para clasificar las instrucciones siguientes dentro de un espacio de nombres determinado. Para más información, consulte [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
### <a name="conditional-compilation-statements"></a>Instrucciones de compilación condicional  
 Instrucciones de compilación condicional pueden aparecer prácticamente en cualquier parte del archivo de origen. Hacer que partes del código que se incluirán o excluirán en tiempo de compilación según determinadas condiciones. También puede utilizarlas para depurar la aplicación, porque el código condicional se ejecuta en modo sólo de depuración. Para obtener más información, consulte [compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).  
  
## <a name="namespace-level-programming-elements"></a>Elementos de programación de nivel de Namespace  
 Clases, estructuras y módulos contienen todo el código en el archivo de origen. Únicamente son *nivel de espacio de nombres* elementos, que pueden aparecer dentro de un espacio de nombres o en el nivel de archivos de origen. Contienen las declaraciones de todos los demás elementos de programación. Las interfaces, que definen firmas de elemento pero no proporcionan ninguna implementación, también aparecen en el nivel de módulo. Para obtener más información sobre los elementos de nivel de módulo, vea lo siguiente:  
  
-   [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 Elementos de datos en el nivel de espacio de nombres son las enumeraciones y delegados.  
  
## <a name="module-level-programming-elements"></a>Elementos de programación de nivel de módulo  
 Procedimientos, operadores, propiedades y eventos son los únicos elementos de programación que pueden contener código ejecutable (instrucciones que realizan acciones en tiempo de ejecución). Únicamente son el *nivel de módulo* elementos del programa. Para obtener más información sobre los elementos de nivel de procedimiento, vea lo siguiente:  
  
-   [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 Elementos de datos en el nivel de módulo son las variables, constantes, enumeraciones y delegados.  
  
## <a name="procedure-level-programming-elements"></a>Elementos de programación de nivel de procedimiento  
 La mayoría del contenido de *nivel de procedimiento* elementos son las instrucciones ejecutables, que constituyen el código en tiempo de ejecución del programa. Todo el código ejecutable debe estar en algún procedimiento (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`). Para obtener más información, vea [Instrucciones (Guía de programación de C#)](../../../visual-basic/programming-guide/language-features/statements.md).  
  
 Elementos de datos en el nivel de procedimiento se limitan a las constantes y variables locales.  
  
## <a name="the-main-procedure"></a>El procedimiento principal  
 El `Main` procedimiento es el primer código que se ejecuta cuando se ha cargado su aplicación. `Main` actúa como punto de partida y control general de la aplicación. Hay cuatro variedades de `Main`:  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 La variedad más común de este procedimiento es `Sub Main()`. Para obtener más información, consulte [procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).  
  
## <a name="see-also"></a>Vea también  
 [Procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Limitaciones de Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)
