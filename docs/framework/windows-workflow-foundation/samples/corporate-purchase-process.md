---
title: "Proceso de compra corporativa | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a5e57336-4290-41ea-936d-435593d97055
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Proceso de compra corporativa
En este ejemplo se muestra cómo crear solicitudes de propuesta \(RFP\) muy básicas en función del proceso de compra con selección automática de la mejor propuesta.  Combina <xref:System.Activities.Statements.Parallel>, <xref:System.Activities.Statements.ParallelForEach%601> y una actividad personalizada <xref:System.Activities.Statements.ForEach%601> para crear un flujo de trabajo que representa el proceso.  
  
 Este ejemplo incluye una aplicación cliente [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] que permite interactuar con el proceso como diferentes participantes \(como el solicitante original o un proveedor en particular\).  
  
## Requisitos  
  
-   [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
-   [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].  
  
## Demostraciones  
  
-   Actividades personalizadas  
  
-   Composición de actividades.  
  
-   Marcadores  
  
-   Persistencia  
  
-   Persistencia esquematizada  
  
-   Traza  
  
-   Seguimiento  
  
-   Hospedaje de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] en clientes diferentes \(aplicaciones web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y aplicaciones WinForms\).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\PurchaseProcess`  
  
## Descripción del proceso  
 En este ejemplo se muestra una implementación de un programa [!INCLUDE[wf](../../../../includes/wf-md.md)] para recopilar las propuestas de los proveedores para una compañía genérica.  
  
1.  Un empleado de la compañía X crea una solicitud de propuestas \(RFP\).  
  
    1.  El empleado escribe el título de la solicitud de propuestas y una descripción.  
  
    2.  El empleado selecciona los proveedores que desea invitar a que envíen sus propuestas.  
  
2.  El empleado envía la propuesta.  
  
    1.  Se crea una instancia del flujo de trabajo.  
  
    2.  El flujo de trabajo espera a que todos los proveedores envíen sus propuestas.  
  
3.  Una vez recibidas todas las propuestas, el flujo de trabajo recorre en iteración todas las propuestas recibidas y selecciona la mejor.  
  
    1.  Cada proveedor tiene una reputación \(en este ejemplo la lista de reputaciones se almacena en VendorRepository.cs\).  
  
    2.  El valor total de la propuesta se determina por \(El valor escrito por el proveedor\) \* \(La reputación grabada del proveedor\) \/ 100.  
  
4.  El solicitante original puede ver todas las propuestas enviadas.  La mejor propuesta se presenta en una sección especial del informe.  
  
## Definición del proceso  
 La lógica básica del ejemplo utiliza una actividad <xref:System.Activities.Statements.ParallelForEach%601> que espera las ofertas de cada proveedor \(utilizando una actividad personalizada que crea un marcador\) y registra la propuesta del proveedor como una solicitud de propuesta \(mediante una actividad <xref:System.Activities.Statements.InvokeMethod>\).  
  
 A continuación, el ejemplo recorre en iteración todas las propuestas recibidas almacenadas en `RfpRepository`, calculando el valor ajustado \(mediante una actividad <xref:System.Activities.Statements.Assign> y las actividades <xref:System.Activities.Expressions>\), y si el valor ajustado es mejor que la mejor oferta anterior, asigna el nuevo valor como la mejor oferta \(utilizando actividades <xref:System.Activities.Statements.If> y <xref:System.Activities.Statements.Assign>\).  
  
## Proyectos en este ejemplo  
 Este ejemplo contiene los siguientes proyectos.  
  
|Project|Descripción|  
|-------------|-----------------|  
|Común|Los objetos entidad utilizados dentro del proceso \(solicitud de propuesta, proveedor y propuesta del proveedor\).|  
|WfDefinition|La definición del proceso \(como un programa [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\) y el host \(`PurchaseProcessHost`\) utilizado por las aplicaciones cliente para crear y utilizar instancias del flujo de trabajo del proceso de compra.|  
|WebClient|Una aplicación cliente [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] que permite a los usuarios crear y participar en instancias del proceso de compra.  Utiliza un host creado de forma personalizada para interactuar con el motor del flujo de trabajo.|  
|WinFormsClient|Una aplicación cliente de Windows Forms que permite a los usuarios crear y participar en instancias del proceso de compra.  Utiliza un host creado de forma personalizada para interactuar con el motor del flujo de trabajo.|  
  
### WfDefinition  
 La siguiente tabla contiene una descripción de los archivos más importantes dentro del proyecto WfDefinition.  
  
|Archivo|Descripción|  
|-------------|-----------------|  
|IPurchaseProcessHost.cs|Interfaz del host del flujo de trabajo.|  
|PurchaseProcessHost.cs|Implementación de un host para el flujo de trabajo.  El host resume los detalles del tiempo de ejecución del flujo de trabajo y se utiliza en todas las aplicaciones cliente para cargar, ejecutar e interactuar con instancias de flujo de trabajo `PurchaseProcess`.|  
|PurchaseProcessWorkflow.cs|Una actividad que contiene la definición del flujo de trabajo del proceso de compra \(se deriva de <xref:System.Activities.Activity>\).<br /><br /> Las actividades que se derivan de <xref:System.Activities.Activity> crean la funcionalidad ensamblando actividades personalizadas existentes y actividades procedentes de la biblioteca de actividades de [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].  Ensamblar estas actividades es la manera más básica de crear la funcionalidad personalizada.|  
|WaitForVendorProposal.cs|Esta actividad personalizada se deriva de <xref:System.Activities.NativeActivity> y crea un marcador con nombre que debe reanudar posteriormente un proveedor al enviar la propuesta.<br /><br /> Las actividades que deriven de <xref:System.Activities.NativeActivity>, como aquéllas que derivan de <xref:System.Activities.CodeActivity>, crean la funcionalidad imperativa invalidando <xref:System.Activities.NativeActivity.Execute%2A>, pero también tienen acceso a toda la funcionalidad del tiempo de ejecución del flujo de trabajo a través de <xref:System.Activities.ActivityContext> que se transfiere al método `Execute`.  Este contexto tiene soporte técnico para programar y cancelar actividades secundarias, configurando zonas sin persistencia \(bloques de ejecución durante los cuales el tiempo de ejecución no conserva los datos del flujo de trabajo, como dentro de las transacciones atómicas\) y los objetos <xref:System.Activities.Bookmark> \(controladores para reanudar los flujos de trabajo en pausa\).|  
|TrackingParticipant.cs|<xref:System.Activities.Tracking.TrackingParticipant> que recibe todos los eventos de seguimiento y los guarda en un archivo de texto.<br /><br /> Los participantes de seguimiento se agregan a la instancia de flujo de trabajo como extensiones.|  
|XmlWorkflowInstanceStore.cs|Un objeto <xref:System.Runtime.DurableInstancing.InstanceStore> personalizado que guarda las aplicaciones de flujo de trabajo en archivos XML.|  
|XmlPersistenceParticipant.cs|Un objeto <xref:System.Activities.Persistence.PersistenceParticipant> personalizado que guarda una instancia de solicitud de propuesta en un archivo XML.|  
|AsyncResult.cs \/ CompletedAsyncResult.cs|Clases de aplicación auxiliar para implementar el patrón asincrónico en los componentes de persistencia.|  
  
### Común  
 La siguiente tabla contiene una descripción de las clases más importantes dentro del proyecto Común.  
  
|Clase|Descripción|  
|-----------|-----------------|  
|Vendor|Un proveedor que envía propuestas en una solicitud de propuestas.|  
|RequestForProposal|Una solicitud de propuestas \(RFP\) es una invitación para que los proveedores envíen propuestas para un artículo o un servicio concretos.|  
|VendorProposal|Una propuesta enviada por un proveedor a una determinada solicitud de propuestas.|  
|VendorRepository|El repositorio de los proveedores.  Esta implementación contiene una colección ubicada en memoria de instancias de proveedor y métodos para exponer esas instancias.|  
|RfpRepository|El repositorio de solicitudes de propuestas.  Esta implementación contiene usos de Linq to XML para consultar el archivo XML de solicitudes de propuestas generado por la persistencia esquematizada.  Esta clase implementa <xref:System.Runtime.Persistence.IDataViewMapper>.|  
|IOHelper|Esta clase administra todos los problemas relacionados con E\/S \(carpetas, rutas de acceso, etc.\).|  
  
### Cliente web  
 La siguiente tabla contiene una descripción de las páginas web más importantes dentro del proyecto Cliente web.  
  
|||  
|-|-|  
|Archivo|Descripción|  
|CreateRfp.aspx|Crea y envía nuevas solicitudes de propuestas.|  
|Default.aspx|Muestra todas las solicitudes de propuestas activas y completas.|  
|GetVendorProposal.aspx|Recibe una propuesta de un proveedor en una solicitud de propuestas concreta.  Esta página la usan solo los proveedores.|  
|ShowRfp.aspx|Muestra toda la información sobre una solicitud de propuestas \(propuestas recibidas, fechas, valores y otra información\).  Esta página solo la usa el creador de la solicitud de propuestas.|  
  
### Cliente de WinForms  
 La siguiente tabla contiene una descripción de los formularios más importantes dentro del proyecto de WinForms.  
  
|||  
|-|-|  
|Form|Descripción|  
|NewRfp|Crea y envía nuevas solicitudes de propuestas.|  
|ShowProposals|Muestra todas las solicitudes de propuestas activas y finalizadas. **Note:**  Puede que necesite hacer clic en el botón **Actualizar** en la interfaz de usuario para ver los cambios en la pantalla después de crear o modificar una solicitud de propuesta.|  
|SubmitProposal|Recibe una propuesta de un proveedor en una solicitud de propuestas concreta.  Esta ventana solo la usan los proveedores.|  
|ViewRfp|Muestra toda la información sobre una solicitud de propuestas \(propuestas recibidas, fechas, valores y otra información\).  Esta ventana solo la usa el creador de la solicitud de propuestas.|  
  
### Archivos de persistencia  
 La siguiente tabla muestra los archivos generados por el proveedor de persistencia \(`XmlPersistenceProvider`\) que se encuentran en la ruta de acceso de la carpeta temporal del sistema actual \(utilizando <xref:System.IO.Path.GetTempPath%2A>\).  El archivo de traza se crea en la ruta de acceso de ejecución actual.  
  
||||  
|-|-|-|  
|Nombre de archivo|Descripción|Ruta de acceso|  
|rfps.xml|El archivo XML con todas las solicitudes de propuestas activas y finalizadas.|<xref:System.IO.Path.GetTempPath%2A>|  
|\[instanceid\]|Este archivo contiene toda la información sobre una instancia de flujo de trabajo.<br /><br /> La implementación de la persistencia esquematizada \(PersistenceParticipant en XmlPersistenceProvider\) genera este archivo.|<xref:System.IO.Path.GetTempPath%2A>|  
|\[instanceId\] .tracking|Un archivo de texto con todos los eventos que se produjeron dentro de una instancia concreta.<br /><br /> TrackingParticipant genera este archivo.|<xref:System.IO.Path.GetTempPath%2A>|  
|PurchaseProcess.Tracing.TraceLog.txt|El archivo de traza generado por el flujo de trabajo en base a los parámetros de configuración de los archivos App.config o Web.config.|Ruta de acceso de ejecución actual|  
  
#### Para utilizar este ejemplo  
  
1.  Abra el archivo de solución PurchaseProcess.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para ejecutar el proyecto Cliente web, abra el **Explorador de soluciones** y haga clic con el botón secundario en el proyecto **Cliente web**.  Seleccione **Establecer como proyecto de inicio**.  
  
3.  Para ejecutar el proyecto Cliente de WinForms, abra el **Explorador de soluciones** y haga clic con el botón secundario en el proyecto **Cliente de WinForms**.  Seleccione **Establecer como proyecto de inicio**.  
  
4.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
5.  Para ejecutar la solución, presione CTRL\+F5.  
  
### Opciones del cliente web  
  
-   **Crear un nuevo RFP**: crea una solicitud de propuestas \(RFP\) e inicia un flujo de trabajo de proceso de compra.  
  
-   **Actualizar**: actualiza la lista de solicitudes de propuestas activas y finalizadas en la ventana principal.  
  
-   **Ver**: muestra el contenido de una solicitud de propuestas existente.  Los proveedores pueden enviar sus propuestas \(si están invitados o la solicitud de propuestas no finaliza\).  
  
-   Ver como: el usuario puede tener acceso a la solicitud de propuestas mediante diferentes identidades seleccionando el participante deseado en el cuadro combinado **Ver como** de la cuadrícula de la solicitud de propuestas activa.  
  
### Opciones del cliente de WinForms  
  
-   **Crear RFP**: crea una solicitud de propuestas \(RFP\) e inicia un flujo de trabajo de proceso de compra.  
  
-   **Actualizar**: actualiza la lista de solicitudes de propuestas activas y finalizadas en la ventana principal.  
  
-   **Ver RFP**: muestra el contenido de una solicitud de propuestas existente.  Los proveedores pueden enviar sus propuestas \(si están invitados o la solicitud de propuestas no finaliza\).  
  
-   **Conectar como**: el usuario puede tener acceso a la solicitud de propuestas utilizando diferentes identidades seleccionando el participante deseado en el cuadro combinado **View as** de la cuadrícula de la solicitud de propuestas activa.  
  
## Vea también