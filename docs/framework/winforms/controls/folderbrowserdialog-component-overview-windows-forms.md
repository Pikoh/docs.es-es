---
title: "Información general del componente FolderBrowserDialog (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 26d2b6294a503edd25b499da2ab67739cdf87174
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>Información general del componente FolderBrowserDialog (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.FolderBrowserDialog> componente es un cuadro de diálogo modal que se utiliza para examinar y seleccionar carpetas. También se pueden crear nuevas carpetas desde el <xref:System.Windows.Forms.FolderBrowserDialog> componente.  
  
> [!NOTE]
>  Para seleccionar archivos, en lugar de las carpetas, use la [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) componente.  
  
 El <xref:System.Windows.Forms.FolderBrowserDialog> componente se muestra en tiempo de ejecución mediante el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método. Establecer el <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> propiedad para determinar la carpeta de nivel superior y todas las subcarpetas que aparecerán en la vista de árbol del cuadro de diálogo. Una vez que haya demostrado el cuadro de diálogo, puede usar el <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> propiedad que se va a obtener la ruta de acceso de la carpeta que se ha seleccionado.  
  
 Cuando se agrega a un formulario, el <xref:System.Windows.Forms.FolderBrowserDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [Elegir carpetas con el componente FolderBrowserDialog de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)  
 [FolderBrowserDialog (componente)](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
