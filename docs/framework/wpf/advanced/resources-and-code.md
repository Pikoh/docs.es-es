---
title: "Recursos y código"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys [WPF], using objects as
- resources [WPF], accessing from procedural code
- procedural code [WPF], creating resources with
- procedural code [WPF], accessing resources from
- resources [WPF], creating with procedural code
ms.assetid: c1cfcddb-e39c-41c8-a7f3-60984914dfae
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 772c44b63627204da7056a5707f2840a82053f11
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="resources-and-code"></a>Recursos y código
Esta información general se centra en cómo obtener acceso a los recursos de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] o crearlos mediante código en lugar de sintaxis [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Para obtener más información sobre el uso de recursos generales y recursos desde una perspectiva de la sintaxis [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], consulte [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
  
  
<a name="accessing"></a>   
## <a name="accessing-resources-from-code"></a>Obtener acceso a recursos desde código  
 Las claves que identifican los recursos si se definen mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] también se usan para recuperar recursos específicos si solicita el recurso en el código. Es la manera más sencilla de recuperar un recurso de código llamar a la <xref:System.Windows.FrameworkElement.FindResource%2A> o <xref:System.Windows.FrameworkElement.TryFindResource%2A> método desde objetos de nivel de marco de la aplicación. La diferencia de comportamiento entre estos métodos es lo que ocurre si no se encuentra la clave solicitada. <xref:System.Windows.FrameworkElement.FindResource%2A>genera una excepción; <xref:System.Windows.FrameworkElement.TryFindResource%2A> no generará una excepción, pero devuelve `null`. Cada método obtiene la clave de recurso como parámetro de entrada y devuelve un objeto escrito de manera imprecisa. Normalmente, una clave de recurso es una cadena, pero hay usos ocasionales en los que no. Consulte la sección [Usar objetos como claves](#objectaskey) para obtener más información. Normalmente, convertiría el objeto devuelto al tipo que necesita la propiedad que está estableciendo al solicitar el recurso. La lógica de búsqueda para la resolución de recursos de código es la misma que la del caso [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de referencia de recursos dinámicos. La búsqueda de recursos comienza desde el elemento que realiza la llamada y continúa hasta los elementos principales sucesivos del árbol lógico. La búsqueda continúa hasta los recursos de la aplicación, los temas y los recursos del sistema, si es necesario. Una solicitud de código para un recurso representará correctamente los cambios en tiempo de ejecución en diccionarios de recursos que puedan haberse realizado después de que se cargara el diccionario desde [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y también para cambios de recursos del sistema en tiempo real.  
  
 Éste es un ejemplo de código breves que busca un recurso por clave y el valor devuelto se utiliza para establecer una propiedad, que se implementa como un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos.  
  
 [!code-csharp[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#resourceproceduralget)]
 [!code-vb[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#resourceproceduralget)]  
  
 Un método alternativo para asignar una referencia de recurso es <xref:System.Windows.FrameworkElement.SetResourceReference%2A>. Este método usa dos parámetros: la clave del recurso y el identificador de una propiedad de dependencia determinada que existe en la instancia del elemento al que se debe asignar el valor del recurso. Funcionalmente, este método es el mismo y tiene la ventaja de que no necesita ninguna conversión de valores devueltos.  
  
 Todavía otra manera de tener acceso a recursos mediante programación es tener acceso al contenido de la <xref:System.Windows.FrameworkElement.Resources%2A> propiedad como un diccionario. Obtener acceso al diccionario que contiene esta propiedad también es el modo de agregar nuevos recursos a las colecciones existentes, comprobar si el nombre de una clave ya existe en la colección y otras operaciones de diccionario o colección. Si está escribiendo un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación completamente en el código, se puede crear la colección completa en código, asignarle claves y, a continuación, asignar la colección acabada a la <xref:System.Windows.FrameworkElement.Resources%2A> propiedad de un elemento establecido. Esto se describe en la sección siguiente.  
  
 Puede indizar dentro de cualquier <xref:System.Windows.FrameworkElement.Resources%2A> colección con una clave específica como el índice, pero debe tener en cuenta que obtiene acceso a los recursos de esta manera no sigue las reglas en tiempo de ejecución normal de la resolución de recursos. Solo obtiene acceso a esa colección concreta. La búsqueda de recursos no recorrerá el ámbito hasta la raíz o aplicación si no se encuentra ningún objeto válido en la clave solicitada. Sin embargo, este enfoque puede tener ventajas de rendimiento en algunos casos, precisamente porque el ámbito de la búsqueda de la clave está más restringido. Consulte la <xref:System.Windows.ResourceDictionary> clase para obtener más información sobre cómo trabajar directamente con el diccionario de recursos.  
  
<a name="creating"></a>   
## <a name="creating-resources-with-code"></a>Crear recursos mediante código  
 Si quiere crear toda una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con código, también es posible que quiera crear los recursos de la aplicación con código. Para lograr esto, cree un nuevo <xref:System.Windows.ResourceDictionary> de instancia y, a continuación, agregar todos los recursos al diccionario mediante llamadas sucesivas a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>. A continuación, utilice la <xref:System.Windows.ResourceDictionary> así creado para establecer el <xref:System.Windows.FrameworkElement.Resources%2A> propiedad en un elemento que está presente en el ámbito de una página, o la <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>. También puede mantener el <xref:System.Windows.ResourceDictionary> como un objeto independiente sin agregarlo a un elemento. Sin embargo, si lo hace, deberá obtener acceso a los recursos que contenga mediante clave de producto, como si fuera un diccionario genérico. A <xref:System.Windows.ResourceDictionary> que no está conectado a un elemento `Resources` propiedad no existiría como parte del árbol de elementos y no tiene ningún ámbito en una secuencia de búsqueda que puede usarse en <xref:System.Windows.FrameworkElement.FindResource%2A> y otros métodos relacionados.  
  
<a name="objectaskey"></a>   
## <a name="using-objects-as-keys"></a>Usar objetos como claves  
 La mayoría de los usos de recursos establecen la clave de recurso en una cadena. Sin embargo, varias características de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no usan deliberadamente un tipo de cadena para especificar las claves. En su lugar, este parámetro es un objeto. La compatibilidad de temas y estilos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aprovecha la funcionalidad de que un objeto asigne la clave a un recurso. Los estilos en los temas que se convierten en el estilo predeterminado para un control en caso contrario, no con tipos de cada uno de ellos codificados por el <xref:System.Type> del control que se debe aplicar. Asignar claves por tipo proporciona un mecanismo de búsqueda confiable que funciona en instancias predeterminadas de cada tipo de control. La reflexión puede detectar el tipo y usarlo para clases derivadas de estilo aunque el tipo derivado no tenga ningún estilo predeterminado. Puede especificar un <xref:System.Type> clave para un recurso definido en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] mediante el uso de la [extensión de marcado x: Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md). Existen extensiones similares para otros usos de clave que no son cadenas que admiten características de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], como [ComponentResourceKey (extensión de marcado)](../../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md).  
  
## <a name="see-also"></a>Vea también  
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)
