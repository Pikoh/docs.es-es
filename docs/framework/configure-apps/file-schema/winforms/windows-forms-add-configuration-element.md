---
title: "Formularios Windows Forms Agregar elemento de configuración"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 367ca30c577cbb4ed7fed130bdcbd4faac2d46c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="windows-forms-add-configuration-element"></a><span data-ttu-id="b23ca-102">Formularios Windows Forms Agregar elemento de configuración</span><span class="sxs-lookup"><span data-stu-id="b23ca-102">Windows Forms Add Configuration Element</span></span>

<span data-ttu-id="b23ca-103">El `<add>` elemento agrega una clave predefinida que especifica si la aplicación de Windows Forms admite características agregadas a las aplicaciones de Windows Forms en el 4.7 de .NET Framework o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="b23ca-103">The `<add>` element adds a predefined key that specifies whether your Windows Form app supports features added to Windows Forms apps in the .NET Framework 4.7 or later.</span></span>

## <a name="syntax"></a><span data-ttu-id="b23ca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b23ca-104">Syntax</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="key-name" value="key-value" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b23ca-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b23ca-105">Attributes and elements</span></span>

<span data-ttu-id="b23ca-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b23ca-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b23ca-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="b23ca-107">Attributes</span></span>

| <span data-ttu-id="b23ca-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="b23ca-108">Attribute</span></span> | <span data-ttu-id="b23ca-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b23ca-109">Description</span></span> |
| --------- | ----------- |
| `key`     | <span data-ttu-id="b23ca-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b23ca-110">Required attribute.</span></span> <span data-ttu-id="b23ca-111">Nombre de clave predefinido que se corresponde con una determinada característica personalizable de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b23ca-111">A predefined key name that corresponds to a particular Windows Forms customizable feature.</span></span> |
| `value`   | <span data-ttu-id="b23ca-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b23ca-112">Required attribute.</span></span> <span data-ttu-id="b23ca-113">El valor que se asigna a `key`.</span><span class="sxs-lookup"><span data-stu-id="b23ca-113">The value to assign to `key`.</span></span> |

### <a name="key-attribute-names-and-associated-values"></a><span data-ttu-id="b23ca-114">`key`nombres de atributos y valores asociados</span><span class="sxs-lookup"><span data-stu-id="b23ca-114">`key` attribute names and associated values</span></span>

| <span data-ttu-id="b23ca-115">Nombre `key`</span><span class="sxs-lookup"><span data-stu-id="b23ca-115">`key` name</span></span> | <span data-ttu-id="b23ca-116">Valores</span><span class="sxs-lookup"><span data-stu-id="b23ca-116">Values</span></span> | <span data-ttu-id="b23ca-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b23ca-117">Description</span></span> |
| ---------- | ------ | ----------- |
| <span data-ttu-id="b23ca-118">"AnchorLayout.DisableSinglePassControlScaling"</span><span class="sxs-lookup"><span data-stu-id="b23ca-118">"AnchorLayout.DisableSinglePassControlScaling"</span></span> | <span data-ttu-id="b23ca-119">"true" &#124;" False"</span><span class="sxs-lookup"><span data-stu-id="b23ca-119">"true"&#124;"false"</span></span> | <span data-ttu-id="b23ca-120">Indica si se escalan anclados controles en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="b23ca-120">Indicates whether anchored controls are scaled in a single pass.</span></span> <span data-ttu-id="b23ca-121">pasa "true" para deshabilitar el único ajuste de escala; en caso contrario, false.</span><span class="sxs-lookup"><span data-stu-id="b23ca-121">"true" to disable single pass scaling; otherwise, false.</span></span> <span data-ttu-id="b23ca-122">Vea la sección "Solo pasar escalado" en la [comentarios](#Remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b23ca-122">See the "Single pass scaling" section in the [Remarks](#Remarks) for more information.</span></span> |
| <span data-ttu-id="b23ca-123">"DpiAwareness"</span><span class="sxs-lookup"><span data-stu-id="b23ca-123">"DpiAwareness"</span></span> | <span data-ttu-id="b23ca-124">"PerMonitorV2" &#124;" False"</span><span class="sxs-lookup"><span data-stu-id="b23ca-124">"PerMonitorV2"&#124;"false"</span></span> | <span data-ttu-id="b23ca-125">Indica si una aplicación es compatible con PPP.</span><span class="sxs-lookup"><span data-stu-id="b23ca-125">Indicates whether an application is DPI-aware.</span></span> <span data-ttu-id="b23ca-126">Establezca la clave para "PerMonitorV2" para admitir el reconocimiento de PPP; de lo contrario, establézcala en "false".</span><span class="sxs-lookup"><span data-stu-id="b23ca-126">Set the key to "PerMonitorV2" to support Dpi awareness; otherwise, set it to "false".</span></span> <span data-ttu-id="b23ca-127">Reconocimiento de PPP es una característica opcional; para aprovechar las ventajas de la compatibilidad con PPP alta de formularios Windows Forms, debe establecer su valor en "PerMonitorV2".</span><span class="sxs-lookup"><span data-stu-id="b23ca-127">DPI awareness is an opt-in feature; to take advantage of Windows Forms' high DPI support, you should set its value to "PerMonitorV2".</span></span> <span data-ttu-id="b23ca-128">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b23ca-128">See the [Remarks](#remarks) section for more information.</span></span> |
| <span data-ttu-id="b23ca-129">"CheckedListBox.DisableHighDpiImprovements"</span><span class="sxs-lookup"><span data-stu-id="b23ca-129">"CheckedListBox.DisableHighDpiImprovements"</span></span> | <span data-ttu-id="b23ca-130">"true" &#124;" False"</span><span class="sxs-lookup"><span data-stu-id="b23ca-130">"true"&#124;"false"</span></span> | <span data-ttu-id="b23ca-131">Indica si el <xref:System.Windows.Forms.CheckedListBox> control aprovecha las ventajas de ajuste de escala y el diseño mejoras introducidas en la 4.7 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b23ca-131">Indicates whether the <xref:System.Windows.Forms.CheckedListBox> control takes advantage of scaling and layout improvements introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="b23ca-132">"true" para no participar en las mejoras de diseño y caling; en caso contrario, "false".</span><span class="sxs-lookup"><span data-stu-id="b23ca-132">"true" to opt out of caling and layout improvements; otherwise, "false".</span></span> |
| <span data-ttu-id="b23ca-133">"DataGridView.DisableHighDpiImprovements"</span><span class="sxs-lookup"><span data-stu-id="b23ca-133">"DataGridView.DisableHighDpiImprovements"</span></span> | <span data-ttu-id="b23ca-134">"true" &#124;" False"</span><span class="sxs-lookup"><span data-stu-id="b23ca-134">"true"&#124;"false"</span></span> | <span data-ttu-id="b23ca-135">Indica si la <xref:System.Windows.Forms.DataGridView> controlar el ajuste de escala y el diseño mejoras introducidas en la 4.7 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b23ca-135">Indicates whether the <xref:System.Windows.Forms.DataGridView> control scaling and layout improvements introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="b23ca-136">"true" para no participar en el reconocimiento de PPP; "false" en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="b23ca-136">"true" to opt out of DPI awareness; "false" otherwise.</span></span> |
| <span data-ttu-id="b23ca-137">"DisableDpiChangedMessageHandling"</span><span class="sxs-lookup"><span data-stu-id="b23ca-137">"DisableDpiChangedMessageHandling"</span></span> | <span data-ttu-id="b23ca-138">"true" &#124;" False"</span><span class="sxs-lookup"><span data-stu-id="b23ca-138">"true"&#124;"false"</span></span> | <span data-ttu-id="b23ca-139">"true" para no participar en la recepción de mensajes relacionados con cambios; de ajuste de escala de PPP "false" en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="b23ca-139">"true" to opt out of receiving messages related to DPI scaling changes; "false" otherwise.</span></span> <span data-ttu-id="b23ca-140">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b23ca-140">See the [Remarks](#remarks) section for more information.</span></span> |
| <span data-ttu-id="b23ca-141">"EnableWindowsFormsHighDpiAutoResizing"</span><span class="sxs-lookup"><span data-stu-id="b23ca-141">"EnableWindowsFormsHighDpiAutoResizing"</span></span> | <span data-ttu-id="b23ca-142">"true" &#124;" False"</span><span class="sxs-lookup"><span data-stu-id="b23ca-142">"true"&#124;"false"</span></span> | <span data-ttu-id="b23ca-143">Indica si una aplicación de formularios Windows Forms cambia automáticamente de tamaño debido a cambios de escala de PPP.</span><span class="sxs-lookup"><span data-stu-id="b23ca-143">Indicates whether a Windows Forms application is automatically resized due to DPI scaling changes.</span></span> <span data-ttu-id="b23ca-144">"true" para habilitar el cambio de tamaño automático; en caso contrario, false.</span><span class="sxs-lookup"><span data-stu-id="b23ca-144">"true" to enable automatic resizing; otherwise, false.</span></span> |
| <span data-ttu-id="b23ca-145">"Form.DisableSinglePassControlScaling"</span><span class="sxs-lookup"><span data-stu-id="b23ca-145">"Form.DisableSinglePassControlScaling"</span></span> | <span data-ttu-id="b23ca-146">"true" &#124;" False"</span><span class="sxs-lookup"><span data-stu-id="b23ca-146">"true"&#124;"false"</span></span> | <span data-ttu-id="b23ca-147">Indica si el <xref:System.Windows.Forms.Form> se escala en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="b23ca-147">Indicates whether the <xref:System.Windows.Forms.Form> is scaled in a single pass.</span></span> <span data-ttu-id="b23ca-148">"true" para deshabilitar la fase de único ajuste de escala; en caso contrario, false.</span><span class="sxs-lookup"><span data-stu-id="b23ca-148">"true" to disable single-pass scaling; otherwise, false.</span></span> <span data-ttu-id="b23ca-149">Vea la sección "Solo pasar escalado" en la [comentarios](#Remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b23ca-149">See the "Single pass scaling" section in the [Remarks](#Remarks) for more information.</span></span> |
| <span data-ttu-id="b23ca-150">"MonthCalendar.DisableSinglePassControlScaling"</span><span class="sxs-lookup"><span data-stu-id="b23ca-150">"MonthCalendar.DisableSinglePassControlScaling"</span></span> | <span data-ttu-id="b23ca-151">"true" &#124;" False"</span><span class="sxs-lookup"><span data-stu-id="b23ca-151">"true"&#124;"false"</span></span> | <span data-ttu-id="b23ca-152">Indica si el <xref:System.Windows.Forms.MonthCalendar> se escala el control en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="b23ca-152">Indicates whether the <xref:System.Windows.Forms.MonthCalendar> control is scaled in a single pass.</span></span> <span data-ttu-id="b23ca-153">"true" para deshabilitar la fase de único ajuste de escala; en caso contrario, false.</span><span class="sxs-lookup"><span data-stu-id="b23ca-153">"true" to disable single-pass scaling; otherwise, false.</span></span> <span data-ttu-id="b23ca-154">Vea la sección "Solo pasar escalado" en la [comentarios](#Remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b23ca-154">See the "Single pass scaling" section in the [Remarks](#Remarks) for more information.</span></span> |
| <span data-ttu-id="b23ca-155">"Toolstrip.DisableHighDpiImprovements"</span><span class="sxs-lookup"><span data-stu-id="b23ca-155">"Toolstrip.DisableHighDpiImprovements"</span></span> | <span data-ttu-id="b23ca-156">"true" &#124;" False"</span><span class="sxs-lookup"><span data-stu-id="b23ca-156">"true"&#124;"false"</span></span> | <span data-ttu-id="b23ca-157">Indica si el <xref:System.Windows.Forms.ToolStrip> control aprovecha las ventajas de ajuste de escala y el diseño mejoras introducidas en la 4.7 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b23ca-157">Indicates whether the <xref:System.Windows.Forms.ToolStrip> control takes advantage of scaling and layout improvements introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="b23ca-158">"true" para no participar en el reconocimiento de PPP; "false" en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="b23ca-158">"true" to opt out of DPI awareness; "false" otherwise.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="b23ca-159">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b23ca-159">Child elements</span></span>

<span data-ttu-id="b23ca-160">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b23ca-160">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b23ca-161">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b23ca-161">Parent elements</span></span>

| <span data-ttu-id="b23ca-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="b23ca-162">Element</span></span> | <span data-ttu-id="b23ca-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="b23ca-163">Description</span></span> |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) | <span data-ttu-id="b23ca-164">Configura el soporte para las nuevas características de aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b23ca-164">Configures support for new Windows Forms application features.</span></span> |

## <a name="a-nameremarks--remarks"></a><span data-ttu-id="b23ca-165"><a name="remarks" />Comentarios</span><span class="sxs-lookup"><span data-stu-id="b23ca-165"><a name="remarks" /> Remarks</span></span>

<span data-ttu-id="b23ca-166">A partir de .NET Framework 4.7, el elemento `<System.Windows.Forms.ApplicationConfigurationSection>` permite configurar las aplicaciones de Windows Forms para aprovechar las características agregadas en versiones recientes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b23ca-166">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="b23ca-167">El `<System.Windows.Forms.ApplicationConfigurationSection>` elemento le permite agregar uno o más secundarios `<add>` elementos, cada uno de los cuales define un valor de configuración específico.</span><span class="sxs-lookup"><span data-stu-id="b23ca-167">The `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to add one or more child `<add>` elements, each of which defines a specific configuration setting.</span></span>  

<span data-ttu-id="b23ca-168">Para obtener información general de soporte técnico de resolución alta de Windows Forms, vea [alta admiten PPP en formularios Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b23ca-168">For an overview of Windows Forms High DPI support, see [High DPI Support in Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).</span></span>

### <a name="dpiawareness"></a><span data-ttu-id="b23ca-169">DpiAwareness</span><span class="sxs-lookup"><span data-stu-id="b23ca-169">DpiAwareness</span></span>

<span data-ttu-id="b23ca-170">Aplicaciones de formularios Windows Forms que se ejecutan en versiones de Windows a partir de Windows 10 creadores de edición y destinadas a versiones de .NET Framework a partir de la 4.7 de .NET Framework pueden configurarse para aprovechar las ventajas de las mejoras de PPP alta introducidas en .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="b23ca-170">Windows Forms apps that run under Windows versions starting with Windows 10 Creators Edition and target versions of the .NET Framework starting with the .NET Framework 4.7 can be configured to take advantage of high DPI improvements introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="b23ca-171">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b23ca-171">These include:</span></span>

- <span data-ttu-id="b23ca-172">Compatibilidad con escenarios de PPP dinámicos en el que el usuario cambia el factor de escala o PPP después de que se ha iniciado una aplicación de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b23ca-172">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

- <span data-ttu-id="b23ca-173">Mejoras en el ajuste de escala y el diseño de una serie de formularios Windows Forms controles, como el <xref:System.Windows.Forms.MonthCalendar> control y el <xref:System.Windows.Forms.CheckedListBox> control.</span><span class="sxs-lookup"><span data-stu-id="b23ca-173">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span> 

<span data-ttu-id="b23ca-174">Reconocimiento de PPP alta es una característica opcional; de forma predeterminada, el valor de `DpiAwareness` es `false`.</span><span class="sxs-lookup"><span data-stu-id="b23ca-174">High DPI awareness is an opt-in feature; by default, the value of `DpiAwareness` is `false`.</span></span> <span data-ttu-id="b23ca-175">Puede participar en el soporte de formularios Windows Forms para que el reconocimiento de PPP estableciendo el valor de esta clave para `PerMonitorV2` en el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b23ca-175">You can opt into Windows Forms' support for DPI awareness by setting the value of this key to `PerMonitorV2` in the application configuration file.</span></span> <span data-ttu-id="b23ca-176">Si está habilitado el reconocimiento de PPP, todas las características individuales de PPP también están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="b23ca-176">If DPI awareness is enabled, all individual DPI features are also enabled.</span></span> <span data-ttu-id="b23ca-177">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b23ca-177">These include:</span></span>

- <span data-ttu-id="b23ca-178">PPP cambiado mensajes, que están controlados por el `DisableDpiChangedMessageHandling` clave.</span><span class="sxs-lookup"><span data-stu-id="b23ca-178">DPI changed messages, which are controlled by the `DisableDpiChangedMessageHandling` key.</span></span>

- <span data-ttu-id="b23ca-179">Soporte de PPP dinámico, que está controlado por el `EnableWindowsFormsHighDpiAutoResizing` clave.</span><span class="sxs-lookup"><span data-stu-id="b23ca-179">Dynamic DPI support, which is controlled by the `EnableWindowsFormsHighDpiAutoResizing` key.</span></span>

- <span data-ttu-id="b23ca-180">Único paso se escala el control, que se controlan mediante la `Form.DisableSinglePassControlScaling` individuo <xref:System.Windows.Forms.Form> controla, por el `AnchorLayout.DisableSinglePassControlScaling` clave para los controles anclados y por la `MonthCalendar.DisableSinglePassControlScaling` clave para el <xref:System.Windows.Forms.MonthCalendar> control</span><span class="sxs-lookup"><span data-stu-id="b23ca-180">Single-pass control scaling, which is controlled by the `Form.DisableSinglePassControlScaling` for individual <xref:System.Windows.Forms.Form> controls, by the `AnchorLayout.DisableSinglePassControlScaling` key for anchored controls, and by the `MonthCalendar.DisableSinglePassControlScaling` key for the <xref:System.Windows.Forms.MonthCalendar> control</span></span> 

- <span data-ttu-id="b23ca-181">Alta PPP escala y el diseño de las mejoras, que se controla mediante el `CheckListBox.DisableHighDpiImprovements` clave para la <xref:System.Windows.Forms.CheckedListBox> controlar, mediante el `DataGridView.DisableHighDpiImprovements` clave para el <xref:System.Windows.Forms.DataGridView> (control) y el `Toolstrip.DisableHighDpiImprovements` clave para el <xref:System.Windows.Forms.ToolStrip> control.</span><span class="sxs-lookup"><span data-stu-id="b23ca-181">High DPI scaling and layout improvements, which is controlled by the `CheckListBox.DisableHighDpiImprovements` key for the <xref:System.Windows.Forms.CheckedListBox> control, by the `DataGridView.DisableHighDpiImprovements` key for the <xref:System.Windows.Forms.DataGridView> control, and by the `Toolstrip.DisableHighDpiImprovements` key for the <xref:System.Windows.Forms.ToolStrip> control.</span></span>  

<span data-ttu-id="b23ca-182">La única participación en configuración predeterminada proporcionada estableciendo `DpiAwareness` a `PerMonitorV2` son más que suficientes para las nuevas aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b23ca-182">The single default opt-in setting provided by setting `DpiAwareness` to `PerMonitorV2` is generally adequate for new Windows Forms applications.</span></span> <span data-ttu-id="b23ca-183">Sin embargo, puede, a continuación, dejar de seguir individuales mejoras alta de PPP agregando la clave correspondiente en el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b23ca-183">However, You can then opt out of individual high DPI improvements by adding the corresponding key to the application configuration file.</span></span> <span data-ttu-id="b23ca-184">Por ejemplo, para aprovechar las ventajas de todas la nueva PPP características del salvo dinámica compatibilidad de PPP, agregar lo siguiente al archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="b23ca-184">For example, to take advantage of all the new DPI featuers except for dynamic DPI support, you would add the following to your application configuration file:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <--! Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```
<span data-ttu-id="b23ca-185">Normalmente, para dejar de seguir una característica determinada porque ha decidido controlarla mediante programación.</span><span class="sxs-lookup"><span data-stu-id="b23ca-185">Typically, you opt out of a particular feature because you've chosen to handle it programmatically.</span></span>

<span data-ttu-id="b23ca-186">Para obtener más información sobre el aprovechamiento de la compatibilidad con valores altos de PPP en aplicaciones de Windows Forms, vea [alta admiten PPP en formularios Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b23ca-186">For more information on taking advantage of High DPI support in Windows Forms applications, see [High DPI Support in Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).</span></span>
 
### <a name="disabledpichangedmessagehandling"></a><span data-ttu-id="b23ca-187">DisableDpiChangedMessageHandling</span><span class="sxs-lookup"><span data-stu-id="b23ca-187">DisableDpiChangedMessageHandling</span></span>

<span data-ttu-id="b23ca-188">A partir de la 4.7 de .NET Framework, los controles de formularios Windows Forms plantear una serie de eventos relacionados con los cambios de ajuste de escala de PPP.</span><span class="sxs-lookup"><span data-stu-id="b23ca-188">Starting with the .NET Framework 4.7, Windows Forms controls raise a number of events related to changes in DPI scaling.</span></span> <span data-ttu-id="b23ca-189">Puede tratarse de la <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, y <xref:System.Windows.Forms.Form.DpiChanged> eventos.</span><span class="sxs-lookup"><span data-stu-id="b23ca-189">These include the <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, and <xref:System.Windows.Forms.Form.DpiChanged> events.</span></span> <span data-ttu-id="b23ca-190">El valor de la `DisableDpiChangedMessageHandling` clave determina si se generan estos eventos en una aplicación de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b23ca-190">The value of the `DisableDpiChangedMessageHandling` key determines whether these events are raised in a Windows Forms application.</span></span> 

### <a name="single-pass-scaling"></a><span data-ttu-id="b23ca-191">Ajuste de escala de paso único</span><span class="sxs-lookup"><span data-stu-id="b23ca-191">Single-pass scaling</span></span>

<span data-ttu-id="b23ca-192">El ajuste de escala única o pasar varios influye en la capacidad de respuesta percibida de la interfaz de usuario y los elementos de la interfaz de la apariencia visual del usuario puesto que se pueden escalar.</span><span class="sxs-lookup"><span data-stu-id="b23ca-192">Single or multi-pass scaling influences the perceived responsiveness of the user interface and the the visual appearance of user interface elements as they are scaled.</span></span> <span data-ttu-id="b23ca-193">A partir de la 4.7 de .NET Framework, Windows Forms utiliza una escala de paso único.</span><span class="sxs-lookup"><span data-stu-id="b23ca-193">Starting with the .NET Framework 4.7, Windows Forms uses single pass scaling.</span></span> <span data-ttu-id="b23ca-194">En versiones anteriores de .NET Framework, el ajuste de escala se realizó a través de varios supera, lo que provocó algunos controles escalar más que era necesario.</span><span class="sxs-lookup"><span data-stu-id="b23ca-194">In previous versions of the .NET Framework, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span> <span data-ttu-id="b23ca-195">Ajuste de escala en un solo paso sólo debe deshabilitarse si la aplicación utiliza el comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="b23ca-195">Single-pass scaling should only be disabled if your app depends on the old behavior.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b23ca-196">Vea también</span><span class="sxs-lookup"><span data-stu-id="b23ca-196">See also</span></span>
 
<span data-ttu-id="b23ca-197">[Sección de configuración de Windows Forms](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) </span><span class="sxs-lookup"><span data-stu-id="b23ca-197">[Windows Forms Configuration Section](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) </span></span>  
[<span data-ttu-id="b23ca-198">Compatibilidad con valores altos de PPP en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b23ca-198">High DPI Support in Windows Forms</span></span>](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)