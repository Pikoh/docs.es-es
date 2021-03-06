---
title: '#Region: directiva'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83ceac7d73eff23e16c5f6efb1c4eb8a2210ee2c
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="region-directive"></a>#Region (Directiva)
Contrae y oculta secciones de código en archivos de Visual Basic.  
  
## <a name="syntax"></a>Sintaxis  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`identifier_string`|Requerido. Cadena que actúa como título de una región cuando esta se contrae. Las regiones están contraídas de forma predeterminada.|  
|`#End Region`|Finaliza el bloque `#Region`.|  
  
## <a name="remarks"></a>Comentarios  
 La directiva `#Region` permite especificar un bloque de código que se puede expandir o contraer cuando se usa la característica de esquematización del Editor de código de Visual Studio. Puede colocar, o *anidar*, las regiones dentro de otras regiones de agrupar regiones similares.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la directiva `#Region`.  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Esquematización](/visualstudio/ide/outlining)  
 [Contraer y ocultar secciones de código](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
