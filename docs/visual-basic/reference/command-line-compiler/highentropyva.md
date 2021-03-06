---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12d40e5acda73786ee88d16bacd9bc5f69400be8
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)
Indica si un archivo ejecutable de 64 bits o un archivo ejecutable que está marcado con el [/Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) opción del compilador admite selección aleatoria de diseño del espacio de direcciones (ASLR) de alta entropía.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Opcional. La opción está desactivada de forma predeterminada o si especifica `-highentropyva-`. La opción está activada si especifica `-highentropyva` o `-highentropyva+`.  
  
## <a name="remarks"></a>Comentarios  
 Si especifica esta opción, las versiones compatibles del núcleo de Windows pueden usar niveles superiores de entropía cuando el kernel Aleatoriza el diseño del espacio de direcciones de un proceso como parte de ASLR. Si el núcleo utiliza grados de entropía más altos, se puede asignar un mayor número de direcciones a las regiones de memoria como pilas y montones. Como resultado, la ubicación de un área de memoria específica es más difícil de adivinar.  
  
 Cuando la opción está activada, el archivo ejecutable de destino y los módulos en que, en función de debe ser capaz de controlar los valores de puntero que son mayores de 4 gigabytes (GB) cuando dichos módulos se ejecutan como procesos de 64 bits.  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
