---
title: "Cómo: Obtener acceso al código fuente HTML en el Modelo de objetos de documento HTML administrado"
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
helpviewer_keywords:
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b0c4f894c3d9178f1dc32f7c99481a7daf565511
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a>Cómo: Obtener acceso al código fuente HTML en el Modelo de objetos de documento HTML administrado
Las propiedades <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> y <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del control <xref:System.Windows.Forms.WebBrowser> devuelven el HTML del documento actual tal y como existía cuando se mostró por primera vez. Sin embargo, si modifica la página usando llamadas a métodos y propiedades, como <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> y <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, estos cambios no aparecerán cuando llame a <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> y <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>. Para obtener el código fuente HTML más actualizado para el DOM, debe llamar a la propiedad <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> del elemento HTML.  
  
 El procedimiento siguiente muestra cómo recuperar el código fuente dinámico y mostrarlo en un menú contextual diferente.  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a>Recuperar el código fuente dinámico con la propiedad OuterHtml  
  
1.  Cree una nueva aplicación de Windows Forms. Comience con un solo <xref:System.Windows.Forms.Form>y llámelo `Form1`.  
  
2.  Host de la <xref:System.Windows.Forms.WebBrowser> controlar en su aplicación de Windows Forms y asígnele el nombre `WebBrowser1`. Para obtener más información, consulte [Cómo: agregar funciones de explorador Web a una aplicación de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).  
  
3.  Cree un segundo <xref:System.Windows.Forms.Form> en su aplicación llamado `CodeForm`.  
  
4.  Agregar un <xref:System.Windows.Forms.RichTextBox> el control a `CodeForm` y establecer su <xref:System.Windows.Forms.Control.Dock%2A> propiedad `Fill`.  
  
5.  Cree una propiedad pública en `CodeForm` denominado `Code`.  
  
     [!code-csharp[DisplayWebBrowserCode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  Agregar un <xref:System.Windows.Forms.Button> control denominado `Button1` a su <xref:System.Windows.Forms.Form>y supervise la <xref:System.Windows.Forms.Control.Click> eventos. Para obtener más información sobre cómo supervisar eventos, vea [eventos](../../../../docs/standard/events/index.md).  
  
7.  Agregue el código siguiente al controlador de eventos <xref:System.Windows.Forms.Control.Click>.  
  
     [!code-csharp[DisplayWebBrowserCode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Pruebe siempre el valor de <xref:System.Windows.Forms.WebBrowser.Document%2A> antes de intentar recuperarlo. Si la página actual no termina de cargarse, puede que <xref:System.Windows.Forms.WebBrowser.Document%2A> o alguno de sus objetos secundarios no se haya inicializado.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar el Modelo de objetos de documento HTML administrado](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)  
 [Información general sobre el control WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)
