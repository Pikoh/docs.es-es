---
title: 'Cómo: Definir márgenes de elementos y controles'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting [WPF], Margin property
- properties [WPF], Margin property
- Margin property [WPF], setting
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f32107074239e9713feaa9e0b9b7e1f89869d111
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-set-margins-of-elements-and-controls"></a>Cómo: Definir márgenes de elementos y controles
En este ejemplo se describe cómo establecer el <xref:System.Windows.FrameworkElement.Margin%2A> propiedad, al cambiar cualquier valor de propiedad existente para el margen en el código subyacente. El <xref:System.Windows.FrameworkElement.Margin%2A> propiedad es una propiedad de la <xref:System.Windows.FrameworkElement> basar el elemento y, por tanto, es heredada por una variedad de controles y otros elementos.  
  
 Este ejemplo está escrito en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], con un código subyacente de los archivos que el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hace referencia a. Se muestra el código subyacente en C# y una versión de Microsoft Visual Basic.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[FEMarginProgrammatic#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
