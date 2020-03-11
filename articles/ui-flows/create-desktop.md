---
title: Información sobre cómo crear flujos de la interfaz de usuario de escritorio | Microsoft Docs
description: Aprenda a crear flujos de la interfaz de usuario de escritorio para aplicaciones Windows.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/28/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c27637f56defb1acff07302954424953ec48b506
ms.sourcegitcommit: 26cda5060446812f3725ccd4fe435839088f50fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "78244315"
---
# <a name="create-and-test-desktop-ui-flows"></a>Creación y prueba de los flujos de la interfaz de usuario de escritorio

[Este tema es documentación preliminar y está sujeto a cambios].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Consulte los [problemas conocidos](create-desktop.md#known-issues-and-solutions) que aparecen más adelante en este tema para más información sobre los problemas que podría encontrar, soluciones alternativas para esos problemas y escenarios no admitidos en esta versión preliminar.


## <a name="create-a-desktop-ui-flow"></a>Creación de un flujo de la interfaz de usuario de escritorio

En los pasos siguientes, se muestra cómo automatizar la aplicación Calculadora para sumar dos números y, después, almacenar el resultado para usarlo más adelante.

> [!TIP]
> Puede automatizar otras aplicaciones de escritorio de Windows siguiendo un patrón similar.

1. Asegúrese de que el [dispositivo está listo](setup.md) para crear flujos de interfaz de usuario. <!--Todo: link to the prereqs section-->

1. Use la [versión Chromium de Microsoft Edge](https://www.microsoftedgeinsider.com) o Google Chrome para abrir [Power Automate](https://flow.microsoft.com) y, luego, inicie sesión con la misma cuenta profesional o educativa que en el dispositivo.

1. Seleccione **Mis flujos** > **Flujos de interfaz de usuario (versión preliminar)**  > **Nuevo**.

   ![Creación de un flujo de interfaz de usuario](../media/create-windows-ui-flow/create-new.png "Creación de un flujo de interfaz de usuario")

1. Elija **Aplicación de escritorio** y seleccione **Siguiente**.

   ![Selección de escritorio](../media/create-windows-ui-flow/select-desktop.png "Selección de escritorio") 

1. Escriba un nombre para el flujo de interfaz de usuario en el campo **Nombre del flujo** y seleccione **Siguiente**.

   ![Selección de escritorio](../media/create-windows-ui-flow/give-a-name.png "Selección de escritorio") 

1. Seleccione **Siguiente** en la parte inferior para omitir la pantalla **Configuración de entradas**, porque no usaremos entradas en este tutorial.

1.  Seleccione **Descargar paquete**.
1.  Abra el archivo **Setup.Microsoft.Flow.UIflow.exe**. Es probable que este archivo esté en la carpeta **Descargas** después de que lo descargó en el paso anterior.
1.  Siga las instrucciones del instalador de configuración de flujos de interfaz de usuario (versión preliminar) para completar la instalación.

    Una vez que el instalador de flujos de interfaz de usuario complete el proceso, el explorador le pedirá activar la extensión.

1. En Microsoft Edge (Chromium), seleccione cada icono de advertencia en la esquina superior derecha del explorador y, luego, seleccione **Enable extension** (Habilitar extensión).
1. En Google Chrome, seleccione **Enable extension** (Habilitar extensión) cuando se le solicite.

   > [!TIP]
   > Si no ve la solicitud en el explorador, revise lo siguiente:
   > - Debe usar el explorador Microsoft Edge (Chromium) o Google Chrome.
   > - Es posible que tenga que habilitar manualmente la extensión. Para Microsoft Edge (Chromium), vaya a **edge://extensions** o, para Google Chrome, vaya a **chrome://extensions**.
   > - Si la extensión de los flujos de interfaz de usuario de Power Automate no aparece, puede volver a instalarla con el [instalador de flujos de interfaz de usuario](https://go.microsoft.com/fwlink/?linkid=2102613).

   Continúe después de haber instalado la extensión.

1. Seleccione la tarjeta **Record app** (Grabar aplicación) para expandirla.

   ![Seleccionar Record app (Grabar aplicación)](../media/create-windows-ui-flow/select-record-app.png "Seleccionar Record app (Grabar aplicación)")

1. Seleccione **Launch recorder** (Iniciar grabadora).

   ![Seleccionar Launch recorder (Iniciar grabadora)](../media/create-windows-ui-flow/select-launch-recorder.png "Seleccionar Launch recorder (Iniciar grabadora)")

   El control de la grabadora aparece en la parte superior de la pantalla.

   ![El control de la grabadora](../media/create-windows-ui-flow/recorder-control.png "El control de la grabadora")

1. Inicie la aplicación Calculadora.

     >[!TIP]
     >Si mantiene el mouse sobre los controles de la aplicación, verá que cada control se resalta con un contorno azul. Espere siempre el resaltado azul antes de seleccionar un control.
     >
     >Si el resaltado azul no aparece alrededor del elemento, es posible que no se grabe correctamente.

1. Seleccione **Record** (Grabar) en el control de la grabadora.
1. Seleccione el primer número y luego, **+** , seleccione el segundo número y, luego, **=** .

    ![La aplicación Calculadora](../media/create-windows-ui-flow/app-to-record.png "La aplicación Calculadora")
    
     > [!TIP] 
     > Para mejorar la confiabilidad de la automatización, puede hacer lo siguiente:
     > - Abra y maximice las aplicaciones que quiere grabar *antes*  de empezar a grabar.
     > - Empiece a grabar con un clic en la barra de título de la aplicación para centrarse en ella.

1. Seleccione **Done** (Listo) en el control de la grabadora cuando complete las acciones que quiere grabar.

1. Cierre la aplicación que grabó.

1. Seleccione la tarjeta que empieza con "Run <app name> script" (Ejecutar script) para ver capturas de pantalla de los pasos grabados.

     >[!TIP]
     >Seleccione **…**  > **Delete** (Eliminar) para quitar cualquier paso duplicado.

    ![Mostrar los pasos grabados](../media/create-windows-ui-flow/show-recorded-steps.png "Mostrar los pasos grabados")

1. Seleccione **Siguiente**. 

1. Seleccione **Siguiente** para omitir el paso de **configuración de salidas**, porque no usaremos salidas en este tutorial.

1. Para probar el flujo de interfaz de usuario, seleccione el botón **Test now** (Probar ahora) y vea la ejecución del flujo de interfaz de usuario.
    
 >[!IMPORTANT]
 >Si quiere obtener los mejores resultados posibles, no interactúe con el dispositivo durante la reproducción.

1. Seleccione **Guardar y salir** para guardar el flujo de interfaz de usuario.

## <a name="next-steps"></a>Pasos siguientes

- Obtenga información sobre cómo [desencadenar el flujo de interfaz de usuario](run-ui-flow.md) que acaba de crear.

- Si quiere hacer más cosas con los flujos de interfaz de usuario, también puede probar los flujos de interfaz de usuario con parámetros de [entrada y salida](inputs-outputs-web.md).

## <a name="known-issues-and-solutions"></a>Problemas conocidos y soluciones

- Actualmente, las capturas de pantalla se pierden después de guardarlas. Estamos trabajando para corregirlo.

- Es posible que quiera agregar una [acción de **cierre**](edit-desktop.md#add-a-manual-action) al final del flujo de interfaz de usuario porque los flujos de interfaz de usuario inician una instancia nueva de las aplicaciones con cada prueba o ejecución.

- Seleccione **…**  > **Delete** (Eliminar) en la tarjeta de acciones grabadas para quitar toda acción innecesaria o duplicada.

- Es posible que los clics con el botón derecho no se reproduzcan correctamente. En tal caso, mientras grabe, haga clic con el botón izquierdo para centrar los flujos de interfaz de usuario en el elemento de interfaz de usuario de destino y, luego, clic con el botón derecho.

- Si los flujos de interfaz de usuario ya no graban ni reproducen las aplicaciones Windows después de instalar una versión nueva, confirme que disponga de la [versión más reciente](https://go.microsoft.com/fwlink/?linkid=2102613&clcid=0x409).


### <a name="unsupported-application-types"></a>Tipos de aplicaciones no compatibles

- Interacciones en Windows (Explorador de archivos, menú de inicio, barra de tareas, etc.).

- Exploradores web (Chrome, IE, Edge, Edge Chromium, Firefox, Mozilla, etc.).
    En su lugar, consulte [Creación de un flujo de interfaz de usuario web](edit-web.md) para automatizar sitios web.

-   Aplicaciones Java

-   Aplicaciones ClickOnce.

-   Aplicaciones con una vista web como, por ejemplo, aplicaciones Electron.

-   Microsoft Office 2016 y versiones anteriores. 

-   Microsoft Office Online.

### <a name="unsupported-configurations"></a>Configuraciones no compatibles

-   Varias pantallas.

-   Grabar a través de un cliente de máquina virtual (Escritorio remoto, Citrix, etc.).

-   Varias instancias de una aplicación donde los títulos de la ventana principal son idénticos.

-   Ventanas de aplicación con títulos idénticos, por ejemplo, Microsoft Outlook con varias ventanas de correo nuevas **Sin título: mensaje (HTML)** activas al mismo tiempo.

-   Sesiones de grabación simultáneas en un dispositivo determinado.

-   Sesiones de reproducción simultáneas en un dispositivo determinado. En el caso de ejecuciones de flujos de interfaz de usuario simultáneas, la primera tiene prioridad y las subsiguientes generar un error hasta que se completa la primera.

-   Reproducir en un dispositivo con un diseño de teclado distinto del dispositivo en el que se grabó.

-   Grabar en un dispositivo o sesión de Windows mientras el explorador con Microsoft Flow está en otro dispositivo o en otra sesión de Windows.

### <a name="unsupported-action-types-and-behaviors"></a>Comportamientos y tipos de acciones no compatibles

No se grabarán estas acciones:

-   Doble clics.

-   Movimiento del mouse.

-   Mantener el mouse sobre un elemento.

-   Clic y arrastrado.

-   Entrada táctil o de lápiz.

-   Una aplicación abierta antes de la grabación.

<!-- -   Closed app before playback starts. -->

## <a name="unreliable-behaviors-and-workarounds-for-microsoft-office-desktop"></a>Comportamientos no confiables y soluciones alternativas de Microsoft Office (escritorio)
- Ancle la cinta de opciones antes de empezar la reproducción para evitar problemas que puedan producirse si la cinta de opciones está configurada para ocultarse automáticamente durante la reproducción.
- No seleccione los elementos mediante clic y arrastrado. Por ejemplo, no use Mayús + clic para seleccionar celdas de Microsoft Excel y no arrastre el mouse para seleccionar texto en Microsoft Word ni Microsoft PowerPoint.
- Es posible que algunos elementos no funcionen correctamente en los flujos de interfaz de usuario (versión preliminar	) de las aplicaciones de escritorio de Microsoft Word y Microsoft PowerPoint. Por ejemplo, es posible que no funcionen las opciones del menú Archivo, como empezar desde cero o hacer clic con el botón derecho en controles como agregar un párrafo en Microsoft Word o cambiar el diseño de las diapositivas en Microsoft PowerPoint.
