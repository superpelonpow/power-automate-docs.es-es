---
title: Aprender a crear flujos de interfaz de usuario con WinAutomation | Microsoft Docs
description: Aprenda a crear flujos de interfaz de usuario con WinAutomation.
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
ms.date: 05/19/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1b9bd3a1f79885d17406e882b4432eff930d342c
ms.sourcegitcommit: 549224cf13fc761f473c880e8d0d8f2741cc7b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "3435049"
---
# <a name="use-softomotives-winautomation-with-ui-flows"></a>Use WinAutomation de Softomotive con flujos de interfaz de usuario.

Ahora su licencia de Power Automate Attended RPA (de pago o de prueba) le ofrece acceso total a la aplicación [WinAutomation](https://www.winautomation.com/) de Softomotive. Este documento le servirá de guía para hacer que los procesos de WinAutomation se ejecuten con Power Automate.

Los usuarios existentes de WinAutomation pueden obtener más información en la [página de soporte técnico de Softomotive](https://support.softomotive.com/support/home)

## <a name="overview-for-existing-ui-flows-users"></a>Información general para los usuarios de flujos de interfaz de usuario

[Descargue](https://aka.ms/rpaDesktopAutomationInstallPage) el software, instálelo y después inicie sesión en WinAutomation con la misma cuenta profesional o educativa que usa para Power Automate. Después de crear un proceso en WinAutomation, puede ejecutarlo de forma asistida o desatendida desde Power Automate mediante un flujo de interfaz de usuario. Para ello, siga estos pasos:

1. Inicie una grabación de escritorio de flujos de interfaz de usuario.
1. Abra el símbolo del sistema.
1. Introduzca el comando para desencadenar el proceso.
   - Para un proceso que no requiere variables de entrada, introduzca *"% programfiles%\WinAutomation\WinAutomationController.exe" /start "/My Robots/MyAutomationName"*.
   - Para un proceso que requiere variables de entrada, introdúzcalas a continuación del nombre del proceso. Por ejemplo, si un proceso llamado *MyAutomationName* requiere especificar *Variable A* y *Variable B*, coloque estos valores de esta manera: *"% programfiles%\WinAutomation\ WinAutomationController.exe" / start "/My Robots/MyAutomationName" ValueA ValueB.*

   >[!TIP] 
   >Puede usar entradas de flujos de interfaz de usuario y contenido dinámico para cambiar el proceso de WinAutomation de destino desde Power Automate.

1. Presione Entrar en el símbolo del sistema y, a continuación, detenga la grabación de flujos de interfaz de usuario. 
   Los flujos de interfaz de usuario capturan toda la información necesaria en el momento en que se inicia el proceso de WinAutomation.
   
1. Agregue el flujo de interfaz de usuario a un flujo y, a continuación, seleccione el tipo de ejecución *asistida* o *desatendida*.

   >[!TIP] 
   >En el proceso de WinAutomation, use la acción *Obtener argumentos de línea de comandos* para obtener los argumentos de la línea de comandos. Los argumentos están en una matriz. Haga referencia a cada argumento por su índice.
   
## <a name="set-up-winautomation"></a>Configuración de WinAutomation

>[!TIP]
>En WinAutomation, los scripts de automatización se llaman **procesos**. En Power Automate, los scripts de automatización se llaman *flujos* o *flujos de interfaz de usuario*.

Antes de crear un proceso de WinAutomation, compruebe la [lista de conectores](https://flow.microsoft.com/connectors/) para ver si la aplicación que quiere automatizar ya tiene un conector. En caso afirmativo, considere la posibilidad de crear un flujo en lugar de un flujo de interfaz de usuario. También puede [crear su propio conector](https://docs.microsoft.com/connectors/custom-connectors/). En general, los conectores basados en API proporcionan una mejor experiencia general que la automatización de la interfaz de usuario en términos de escalabilidad, fiabilidad y coste.

>[!TIP]
>Para ejecutar scripts de WinAutomation desde Power Automate, primero debe iniciar la reproducción de los scripts desde flujos de interfaz de usuario.

## <a name="prerequisites"></a>Requisitos previos 

Para ejecutar WinAutomation como parte de Power Automate, tiene que:
1. Asegurarse de que su equipo cumpla los [requisitos de uso de los flujos de interfaz de usuario](https://docs.microsoft.com/power-automate/ui-flows/setup#prerequisites).
1. Instalar la aplicación [Flujos de interfaz de usuario](https://docs.microsoft.com/power-automate/ui-flows/setup) y, a continuación, instalar y configurar la puerta de enlace de datos local.

## <a name="licensing"></a>Licencias

Necesitas un *Plan por usuario con RPA asistida* para usar Flujos de interfaz de usuario y WinAutomation. Si no tiene un plan de pago, puede empezar a usar una versión de prueba del *Plan por usuario con RPA asistida*. Para ello, vaya a Power Automate y seleccione la pestaña **Flujos de interfaz de usuario** en **Mis flujos**. Verá el cuadro de diálogo de prueba desde el que puede iniciar la prueba.

![Iniciar una prueba o comprar una licencia](../media/create-processes/trial.png)

Si ya tiene un plan pago o utilizó una versión de prueba anteriormente, no podrá iniciar una nueva prueba. En este caso, tendrá que solicitar a su administrador que compre o inicie una versión de prueba del *Plan por usuario con RPA asistida* de Power Automate. Para realizar la compra pueden ir a **Facturación** > **Adquirir servicios** en el Centro de administración de Microsoft 365, y buscar el plan adecuado.

![Plan por usuario con RPA asistida](../media/create-processes/license-plan.png)

Por último, cuando hayan adquirido un plan u obtenido la versión de prueba gratuita, tienen que asignar ese plan a un usuario. 

>[!NOTE]
>Cuando se asigna un plan a un usuario, pueden pasar unos minutos antes de que la asignación sea efectiva.

>[!WARNING]
>Para grabar, probar o ejecutar la automatización de la interfaz de usuario, debe tener la versión más reciente de cada componente.

## <a name="install-winautomation"></a>Instalar WinAutomation

Una vez que haya instalado Flujos de interfaz de usuario en su equipo, puede instalar WinAutomation para grabar, editar y probar los scripts de automatización para el escritorio siguiendo estos pasos:

1.  Descargar el [instalador de WinAutomation](https://aka.ms/rpaDesktopAutomationInstallPage).

1.  Abra el archivo **WinAutomationSetup.exe**. Es probable que este archivo esté en la careta **Descargas**.

1.  Siga las instrucciones del instalador de WinAutomation para completar la instalación. Durante la instalación, asegúrese de que **Tipo de licencia** esté establecido en **Microsoft Power Automate**.

## <a name="sign-in-to-winautomation"></a>Iniciar sesión en WinAutomation 

Una vez completada la instalación, inicie la consola de WinAutomation desde el menú de inicio de Windows. Se iniciará la aplicación y le pedirá que inicie sesión. Si ya tiene una licencia de *Plan por usuario con RPA asistida* para Power Automate o si tiene una licencia de versión de prueba de Power Automate, introduzca las credenciales de usuario que utiliza para [Power Automate](https://flow.microsoft.com). También puede visitar la [página de precios](https://flow.microsoft.com/pricing/) para obtener más información sobre esta licencia o para obtener una licencia de prueba.

Si no tiene una licencia válida, verá este mensaje de error.

![Error de licencia](../media/create-processes/license-error.png)


>[!WARNING]
>Necesitará que el administrador del inquilino le otorgue su consentimiento para usar su cuenta profesional o educativa de Power Automate con WinAutomation. Con este fin, pueden instalar WinAutomation, iniciar sesión con su cuenta de administrador del inquilino y otorgar consentimiento.

![Solicitud de permisos](../media/create-processes/permissions-request.png)

Una vez que haya iniciado sesión, verá la consola de WinAutomation con algunos procesos de ejemplo. Para empezar, vaya a **Opciones** > **Ayuda** > **Introducción**, y luego revise algunos ejemplos de creación de procesos sencillos. Además, están disponibles varios [tutoriales de iniciación para WinAutomation](https://www.winautomation.com/support/tutorials/).

## <a name="run-winautomation-processes-from-power-automate"></a>Ejecutar procesos de WinAutomation desde Power Automate

Una vez que haya definido su script de automatización en WinAutomation, puede ejecutarlo desde un flujo en Power Automate mediante la compatibilidad con los flujos de interfaz de usuario para iniciar aplicaciones desde el símbolo del sistema. Encontrará más información sobre cómo crear y probar flujos de interfaz de usuario [aquí](https://docs.microsoft.com/power-automate/ui-flows/create-desktop).

### <a name="running-winautomation-processes"></a>Ejecutar procesos de WinAutomation 

Para ejecutar un proceso de WinAutomation sin el entorno de la consola, puede usar el comando WinAutomationController.EXE. Este proceso se encuentra en la carpeta de instalación de WinAutomation y se puede iniciar desde el **Símbolo del sistema** de Windows. Aunque tiene muchos parámetros útiles, para iniciar la automatización solo tiene que usar el indicador '/start', que iniciará el proceso especificado. Veamos un ejemplo del comando: **WinAutomationController /start rutaProceso**

*rutaProceso* es la ruta del proceso en la consola de WinAutomation, desde el directorio base Mis procesos en el panel Carpetas del lado izquierdo. Si ha colocado el proceso en una subcarpeta, deberá incluir esa información en rutaProceso. Tenga en cuenta que, si rutaProceso contiene espacios, debe escribirse entre comillas dobles (por ejemplo, WinAutomationController /start "/Mis procesos/../../nombreProceso").

### <a name="launching-winautomation-processes-from-ui-flows"></a>Lanzamiento de procesos de WinAutomation desde flujos de interfaz de usuario

Una vez que haya identificado correctamente el comando para ejecutar los procesos de WinAutomation anteriores, podrá invocar este comando directamente desde los flujos de interfaz de usuario. Para hacerlo:

1.  Agregue un nuevo paso en la experiencia de grabación de flujo de interfaz de usuario. Para ello, haga clic en **Iniciar grabadora** si tiene un flujo de interfaz de usuario en blanco. Si ya tiene pasos predefinidos en el flujo de interfaz de usuario, puede hacer clic en **Nuevo paso** y después hacer clic en **Grabar aplicación** para iniciar la grabadora. Encontrará más información sobre la experiencia de grabación [aquí](https://docs.microsoft.com/power-automate/ui-flows/create-desktop).

1.  Seleccione **Grabar** en la grabadora iniciada.

1.  Abra la aplicación **Símbolo del sistema** en Windows.

1.  Escriba el comando WinAutomationController que creó anteriormente (por ejemplo, WinAutomationController /start "/Mis procesos/../../ proceso").

1.  Seleccione **Listo** en la grabadora.

Notará que la grabadora agrega nuevos pasos al flujo de interfaz de usuario, entre los que ahora se incluye el lanzamiento de WinAutomationController.


>[!TIP]
>Los flujos de interfaz de usuario pueden ejecutarse tanto en modo de automatización asistida como en modo de automatización desatendida. También puede ejecutar WinAutomationController en ambos casos. Si ejecuta flujos de interfaz de usuario en un clúster desatendido, asegúrese de que se ejecute el comando WinAutomationController especificado anteriormente en todos los equipos del clúster. Para obtener más información sobre los flujos de interfaz de usuario asistidos y desatendidos, haga clic [aquí](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow).

## <a name="waiting-for-a-winautomation-process-to-complete-in-ui-flows"></a>Esperar a que se complete un proceso de WinAutomation en flujos de interfaz de usuario

De forma predeterminada, WinAutomationController.exe ejecuta los procesos en segundo plano. Si desea que los flujos de interfaz de usuario esperen a que se complete la automatización del proceso de WinAutomation, puede generar un cuadro de mensaje informativo al final del proceso de WinAutomation mediante el comando **Mostrar mensaje** y esperar en flujos de interfaz de usuario para hacer clic en el botón del cuadro de mensaje. Para hacerlo:

1.  Agregue un comando "Mostrar mensaje" como último paso de su proceso de WinAutomation. Para ello, filtre el panel de acciones de la izquierda para buscar Mostrar mensaje y arrastre y coloque ese comando en el editor de scripts de proceso. Puede asignarle un título descriptivo y una descripción, y dejar la selección de botón predeterminada que muestra el botón Aceptar.
1.  Ejecute el proceso WinAutomation hasta que se muestre el cuadro de mensaje. 
1.  Agregue una nueva grabación de flujo de interfaz de usuario, haga clic en el título del cuadro Mostrar mensaje y, a continuación, haga clic en Aceptar. 
1.  Haga clic en Listo para detener la grabación. Ahora verá que el script en el flujo de la interfaz de usuario tiene un nuevo conjunto de acciones para hacer clic en el cuadro de diálogo y descartar el cuadro de mensaje.
1.  Por último, debe indicarle al flujo de interfaz de usuario que asigne a WinAutomation un tiempo determinado para completarse. Para ello, expanda el comando Enviar teclas anterior que inicia el comando WinAutomationController.exe, expanda para ver las opciones avanzadas y configure la propiedad Esperar después para esperar la cantidad máxima de tiempo que tardará en ejecutarse el script del proceso de WinAutomation.


## <a name="uninstall-winautomation"></a>Desinstalar WinAutomation

1.  Abra el menú **Inicio** \> **Configuración** \> **Aplicaciones**.

1.  Busque **WinAutomation** y selecciónelo.

1.  Seleccione **Desinstalar**.

## <a name="troubleshooting-winautomation-licensing-issues"></a>Solución de problemas de licencia de WinAutomation

Si aparecen errores de licencia al iniciar WinAutomation, asegúrese de que el usuario con el que inicia sesión tiene una licencia válida de flujos de interfaz de usuario. Para ello: 

1.  Vaya a [Power Automate](https://flow.microsoft.com) e inicie sesión.
1.  Seleccione Mis flujos en la barra de navegación de la izquierda.
1.  Seleccione flujos de interfaz de usuario en la página de la derecha. Es posible que deba iniciar una prueba o pedirle a su administrador que lo haga.

Para restablecer la información de licencia almacenada por WinAutomation, puede eliminar el siguiente archivo: %localappdata%\Softomotive\WinAutomation\msalcache.bin3

>[!NOTE]
>Esta licencia se almacena en caché cuando los usuarios inician WinAutomation mientras están conectados a Internet. 


## <a name="learn-more"></a>Más información

- Más información sobre la [Adquisición de WinAutomation](https://flow.microsoft.com/blog/microsoft-acquires-softomotive-to-expand-low-code-robotic-process-automation-capabilities-in-microsoft-power-automate/)
- Obtener soporte para [WinAutomation](https://support.softomotive.com/support/home).
- Póngase en marcha con los [Tutoriales de WinAutomation](https://www.winautomation.com/support/tutorials/).
- Aprenda a [crear flujos de interfaz de usuario de escritorio](https://docs.microsoft.com/power-automate/ui-flows/create-desktop).
- Aprenda a [ejecutar flujos de interfaz de usuario](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow).
- Aprenda a [administrar flujos de interfaz de usuario](https://docs.microsoft.com/power-automate/ui-flows/manage).
- Más información sobre la [puerta de enlace local](https://docs.microsoft.com/power-automate/gateway-reference#use-a-gateway).
