---
title: "Cómo: Animar los cambios de tamaño mediante fotogramas clave"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30ee897efd01712bf4313da87e1050c5a16e4523
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>Cómo: Animar los cambios de tamaño mediante fotogramas clave
En este ejemplo se muestra cómo animar los cambios del tamaño mediante fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> clase para animar la <xref:System.Windows.Media.ArcSegment.Size%2A> propiedad de un <xref:System.Windows.Media.ArcSegment>. Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1.  Durante el primer medio segundo de la animación, usa una instancia de la <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> clase aumentar gradualmente el tamaño del arco. Al igual que los fotogramas clave lineales <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> crear una transición lineal suave entre valores.  
  
2.  Al final de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> clase repentinamente aumentar el tamaño del arco. Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> crear saltos súbitos entre los valores, es decir, los cambios de tamaño se producen de repente y no son sutiles.  
  
3.  En los dos últimos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> clase para aumentar el tamaño del arco. Al igual que los fotogramas clave spline <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> crear una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> propiedad. En este ejemplo, el tamaño del arco aumenta lentamente al principio y va aumentando exponencialmente hacia el final del segmento temporal.  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.ArcSegment.Size%2A>  
 <xref:System.Windows.Media.ArcSegment>  
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Temas de procedimientos de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
