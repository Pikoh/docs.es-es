---
title: Glosario de Windows Workflow Foundation para .NET Framework 4.5
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Workflow Foundation [WF], glossary
- WF [WF], glossary
ms.assetid: ab682b2f-3779-45ca-b831-b7c03d7dbb3a
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 54a0cc6d9a0c922e57bf00b649894f26b42a64f4
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2018
---
# <a name="windows-workflow-foundation-glossary-for-net-framework-45"></a>Glosario de Windows Workflow Foundation para .NET Framework 4.5
Los términos siguientes se usan en la documentación de Windows Workflow Foundation.  
  
## <a name="terms"></a>Términos  
  
|Término|Definición|  
|----------|----------------|  
|actividad|Unidad de comportamiento de programa de Windows Workflow Foundation. Las actividades individuales se pueden combinar en actividades más complejas.|  
|acción de actividad|Estructura de datos que se usa para exponer devoluciones de llamada para la ejecución de flujos de trabajo y actividades.|  
|argument|Define el flujo de datos de entrada y de salida de una actividad. Cada argumento tiene una dirección especificada: entrada, salida o entrada/salida. Representan los parámetros de entrada, salida y entrada/salida de la actividad.|  
|marcador|Punto en el que una actividad se puede pausar y esperar a ser reanudada.|  
|compensación|Grupo de acciones diseñado para deshacer o mitigar el efecto del trabajo completado anteriormente.|  
|correlación|Mecanismo para enrutar los mensajes a una instancia de servicio o de flujo de trabajo.|  
|expresión|Construcción que toma uno o varios argumentos, realiza una operación con ellos y devuelve un solo valor. Las expresiones pueden usarse en cualquier lugar en el que pueda usarse una actividad.|  
|diagrama de flujo|Paradigma de modelado conocido que representa los componentes de los programas como símbolos vinculados mediante flechas direccionales.  En .NET Framework 4.0, se pueden modelar flujos de trabajo como diagramas de flujo mediante la actividad Flowchart.|  
|proceso de ejecución prolongada|Unidad de ejecución de programa que no vuelve inmediatamente, y que puede abarcar varios reinicios del sistema.|  
|persistencia|Guardar el estado de un flujo de trabajo o servicio en un medio de almacenamiento duradero, para poder descargarlo de la memoria o recuperarlo después de un error del sistema.|  
|equipo de estado|Paradigma de modelado conocido que representa los componentes de los programas como estados individuales vinculados mediante transiciones de estados orientadas a eventos.  Los flujos de trabajo pueden modelarse como máquinas de estado mediante la actividad StateMachine.|  
|sustancia|Representa un grupo de marcadores relacionados bajo un identificador común y permite al motor de tiempo de ejecución tomar decisiones sobre si la reanudación de un marcador concreto es válida o puede llegar a serlo.|  
|convertidor de tipos|Un tipo CLR puede estar asociado a uno o varios tipos derivados de System.ComponentModel.TypeConverter que permiten convertir instancias del tipo CLR en instancias de otros tipos, y viceversa. Un convertidor de tipos se asocia a un tipo CLR utilizando el atributo System.ComponentModel.TypeConverterAttribute.  Un TypeConverterAttribute puede especificarse directamente en el tipo CLR o en una propiedad. Un convertidor de tipos especificado en una propiedad siempre tiene prioridad sobre un convertidor de tipos especificado en el tipo CLR de la propiedad.|  
|variable|Representa el almacenamiento de algunos datos que deben guardarse y usarse después.|  
|flujo de trabajo|Actividad individual o árbol de actividades que invoca un proceso de host.|  
|XAML|Lenguaje XAML|
