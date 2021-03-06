---
title: "Cómo: Descargar un archivo en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- downloading Internet resources [Visual Basic], files
- downloading files [Visual Basic]
- remote computers [Visual Basic], downloading from
- files [Visual Basic], downloading
- files [Visual Basic], transferring
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dc67d28b870f86c6464e86f7682f71e6e36ea9e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-download-a-file-in-visual-basic"></a>Cómo: Descargar un archivo en Visual Basic
El método <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> se puede usar para descargar un archivo remoto y almacenarlo en una ubicación específica. Si el parámetro `ShowUI` se establece en `True`, se abre un cuadro de diálogo que muestra el progreso de la descarga y permite a los usuarios cancelar la operación. De forma predeterminada, no se sobrescriben los archivos existentes que tengan el mismo nombre. Si quiere sobrescribir los archivos existentes, establezca el parámetro `overwrite` en `True`.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de unidad no es válido (<xref:System.ArgumentException>).  
  
-   No se ha proporcionado la autenticación necesaria (<xref:System.UnauthorizedAccessException> o <xref:System.Security.SecurityException>).  
  
-   El servidor no responde en el `connectionTimeout` especificado (<xref:System.TimeoutException>).  
  
-   El sitio web ha denegado la solicitud (<xref:System.Net.WebException>).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
> [!IMPORTANT]
>  No tome ninguna decisión sobre el contenido del archivo basándose en su nombre. Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic. Compruebe todas las entradas antes de utilizar los datos en la aplicación. Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.  
  
### <a name="to-download-a-file"></a>Para descargar un archivo  
  
-   Use el método `DownloadFile` para descargar el archivo, especificando la ubicación del archivo de destino como una cadena o un identificador URI, y la ubicación en la que se va a almacenar el archivo. En este ejemplo se descarga el archivo `WineList.txt` de `http://www.cohowinery.com/downloads` y se guarda en `C:\Documents and Settings\All Users\Documents`:  
  
     [!code-vb[VbResourceTasks#9](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_1.vb)]  
  
### <a name="to-download-a-file-specifying-a-time-out-interval"></a>Para descargar un archivo, especificando un intervalo de tiempo de espera  
  
-   Use el método `DownloadFile` para descargar el archivo, especificando la ubicación del archivo de destino como una cadena o un identificador URI, la ubicación en la que se va a almacenar el archivo y el intervalo de tiempo de espera en milisegundos (el valor predeterminado es 1000). En este ejemplo se descarga el archivo `WineList.txt` de `http://www.cohowinery.com/downloads` y se guarda en `C:\Documents and Settings\All Users\Documents`, especificando un intervalo de tiempo de espera de 500 milisegundos:  
  
     [!code-vb[VbResourceTasks#10](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_2.vb)]  
  
### <a name="to-download-a-file-supplying-a-user-name-and-password"></a>Para descargar un archivo, proporcionando un nombre de usuario y contraseña  
  
-   Use el método `DownLoadFile` para descargar el archivo, especificando la ubicación del archivo de destino como una cadena o un identificador URI, y la ubicación en la que se va a almacenar el archivo, el nombre de usuario y la contraseña. En este ejemplo se descarga el archivo `WineList.txt` de `http://www.cohowinery.com/downloads` y se guarda en `C:\Documents and Settings\All Users\Documents`, con el nombre de usuario `anonymous` y una contraseña en blanco.  
  
     [!code-vb[VbResourceTasks#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_3.vb)]  
  
    > [!IMPORTANT]
    >  El protocolo FTP que usa el método `DownLoadFile` envía información, incluidas las contraseñas, en texto sin formato y no debe usarse para transmitir información confidencial.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Devices.Network>  
 <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>  
 [Cargar un archivo](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)  
 [Analizar rutas de acceso a archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
