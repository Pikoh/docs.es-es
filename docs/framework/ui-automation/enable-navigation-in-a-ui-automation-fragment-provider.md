---
title: "Enable Navigation in a UI Automation Fragment Provider | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "UI Automation, enabling navigation in provider"
  - "navigation, enabling in UI Automation provider"
ms.assetid: 3cb6092a-58c9-4ca0-84a5-0e54d5d00a0d
caps.latest.revision: 16
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 16
---
# Enable Navigation in a UI Automation Fragment Provider
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tema contiene código de ejemplo que muestra cómo habilitar la navegación en un proveedor de automatización de interfaz de usuario para un elemento que está dentro de un fragmento.  
  
## Ejemplo  
 El siguiente código de ejemplo implementa <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> para un elemento de lista dentro de una lista. El elemento primario es el elemento de cuadro de lista y los elementos del mismo nivel son otros elementos de la colección de lista. El método devuelve `null` \(`Nothing` en Visual Basic\) para las direcciones que no son válidas; en este caso, <xref:System.Windows.Automation.Provider.NavigateDirection> y <xref:System.Windows.Automation.Provider.NavigateDirection>, ya que el elemento no tiene elementos secundarios.  
  
 [!code-csharp[UIAFragmentProvider_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListItemFragment.cs#103)]
 [!code-vb[UIAFragmentProvider_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListItemFragment.vb#103)]  
  
## Vea también  
 [UI Automation Providers Overview](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)   
 [Server\-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)