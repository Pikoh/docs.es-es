---
title: "Cómo: Crear teclas de acceso para controles de Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81aa68a65d09b073b117f4d96dfc06e614d68aea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>Cómo: Crear teclas de acceso para controles de Windows Forms
Un *clave de acceso* es un carácter subrayado en el texto de un menú, elemento de menú o la etiqueta de un control como un botón. Con una clave de acceso, el usuario puede "haga clic en" un botón presionando la tecla ALT en combinación con la clave de acceso predefinidas. Por ejemplo, si un botón ejecuta un procedimiento para imprimir un formulario y por tanto su `Text` propiedad se establece en "Print","Agregar una y comercial antes de la letra"P"hace que la letra"P"aparecerá subrayada en el texto del botón en tiempo de ejecución. El usuario puede ejecutar el comando asociado con el botón presionando ALT + P. No puede tener una tecla de acceso para un control que no se puede recibir el foco.  
  
### <a name="to-create-an-access-key-for-a-control"></a>Para crear una clave de acceso para un control  
  
1.  Establecer el `Text` propiedad a una cadena que incluye una y comercial (&) delante de la letra que será el acceso directo.  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  Para incluir una y comercial en un título sin crear una tecla de acceso, incluya dos símbolos de y comercial (& &). Un solo carácter & se muestra en el título y no está subrayados ningún carácter.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Button>  
 [Responder a clics de botones en Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Establecer el texto mostrado por un control de Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
