---
title: Inicio de flujos con botones Flic | Microsoft Docs
description: Inicie fácilmente flujos de botón con botones físicos Flic de Shortcut Labs.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/19/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 65d9a93215030905f41e082d38789592a4267404
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194356"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>Ejecute flujos presionando un botón inteligente Flic (versión preliminar)

Desencadene flujos presionando un botón físico, conocido como Flic, de Shortcut Labs. Por ejemplo, presione un Flic para realizar un seguimiento de las horas de trabajo, bloquear el calendario, contar los visitantes de un evento o guardar ubicaciones geográficas.

> [!IMPORTANT]
> Antes de crear un flujo, configure todas las propiedades del Flic mediante la aplicación móvil de Flic para [Android](https://play.google.com/store/apps/details?id=io.flic.app) o [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8).
> 
> 

## <a name="prerequisites"></a>Requisitos previos
Para usar Flics con Power Automate, debe cumplir estos requisitos:

* Disponer de acceso a [Power Automate](https://flow.microsoft.com).
* Haber descargado la aplicación móvil de Flic para [Android](https://play.google.com/store/apps/details?id=io.flic.app) o [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8), y haberla usado para emparejar uno o varios Flics.

## <a name="configure-flic-properties"></a>Configurar las propiedades del Flic
Usar la aplicación móvil de Flic para programar los eventos del Flic. Los eventos son:

* click (presionar una vez rápidamente)
* double-click (presionar dos veces rápidamente)
* hold (presionar una vez de manera prolongada)

En esta captura de pantalla se muestra un ejemplo de cómo podría ser el proceso de configuración de un Flic:

![configurar Flics](./media/flic-button-flows/configure-flic-actions.png)

Una vez que haya vinculado un evento de Flic a Power Automate, puede seleccionar dicho flic como desencadenador para sus flujos. Los desencadenadores los seleccionará más adelante en el tutorial.

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>Cree un flujo desencadenado por un Flic
En este tutorial, usamos un Flic para ejecutar un flujo que registra el tiempo que un consultor invierte en cada cliente. El consultor pulsa el Flic al llegar y vuelve a pulsarlo inmediatamente antes de salir del cliente. Cada vez que se pulsa el Flic se inicia una ejecución del flujo al que está conectado. El flujo guarda la hora actual en Hojas de cálculo de Google y, después, envía una notificación por correo electrónico. El correo electrónico contiene detalles acerca de la ejecución de flujo.

Nota: asegúrese de que ha usado la aplicación móvil Flic para realizar el emparejamiento y configure al menos una acción **click** que desencadene Power Automate. En esta captura de pantalla, he configurado la acción **click** para desencadenar Power Automate. Más adelante configuraremos que se desencadene nuestro flujo cuando el Flic se pulsa una vez (se hace clic en él).

   ![configuración de flic](./media/flic-button-flows/flic-configured-for-flow.png)

Vamos a empezar a crear un flujo.

### <a name="start-with-a-template"></a>Empiece con una plantilla
1. Inicie sesión en [Power Automate](https://flow.microsoft.com).
   
    ![iniciar sesión](./media/flic-button-flows/sign-into-flow.png)
2. Escriba **flic** en el cuadro de búsqueda y seleccione el icono de búsqueda.
   
    ![buscar flic](./media/flic-button-flows/search-flic.png)
3. Seleccione la plantilla **Track your working hours with Flic smart button** (Seguimiento de horas trabajadas con botón inteligente Flic).
   
    ![seleccionar plantilla](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>Creación de una hoja de cálculo en Hojas de cálculo de Google
1. Revise los detalles de la plantilla y verá que requiere una plantilla en Hojas de cálculo de Google.
   
   ![revisar detalles de plantilla](./media/flic-button-flows/flic-template-details.png)
2. En Hojas de cálculo de Google, cree una hoja de cálculo que contenga una hoja con las columnas **ClickType** y **TimeStamp**.
   
      Sugerencia: para asignar nombres a las columnas en Hojas de cálculo de Google escriba el nombre al principio de la columna. Por consiguiente, la hoja debería ser como la que aparece en esta captura de pantalla:
   
   ![Hoja de cálculo de Google](./media/flic-button-flows/flic-google-sheet.png)
   
   Nota: esta hoja se usa más adelante en este mismo tutorial.

### <a name="add-the-flic-trigger-to-your-flow"></a>Agregue el desencadenador de Flic al flujo
1. Inicie sesión en los servicios de la plantilla y seleccione **Continuar**.
   
     La opción **Continuar** está habilitada después de iniciar sesión en todos los servicios requeridos para la plantilla.
   
    ![proporcionar credenciales](./media/flic-button-flows/flic-template-services-sign-in.png)
2. Escriba **flic** en el cuadro de búsqueda y seleccione **Flic - When a Flic is pressed** (Flic: cuando se presiona un Flic).
   
    ![buscar desencadenador de flic](./media/flic-button-flows/flic-search-trigger.png)
3. En la lista **Flic button** (Botón Flic) de la tarjeta **Flic - When a Flic is pressed** (Flic: cuando se presiona un Flic), seleccione el Flic que desea usar.
4. Seleccione **click** en la lista **Events** (Eventos) para indicar que desea desencadenar el flujo cuando el Flic se presione una vez.
   
    ![seleccionar acción de flic](./media/flic-button-flows/select-flic.png)
   
   Si lo desea, puede seleccionar **any** para indicar que todos los eventos del Flic (click, double-click o hold) desencadenan el flujo.
   
   **Double-click** indica que el flujo se desencadena cuando el Flic se presiona rápidamente dos veces. **Hold** indica que una presión prolongada en el Flic desencadena el flujo.
   
   Puede crear otros flujos y desencadenarlo con los restantes eventos de la lista **Events** (Eventos). Por ejemplo, puede usar el evento **double-click** para registrar la hora a la que sale del cliente.

### <a name="configure-the-sheet"></a>Configurar la hoja
   En la tarjeta **Insert row** (Insertar fila):

1. Seleccione la hoja de cálculo que creó anteriormente en la lista **Archivo**.
2. Seleccione la hoja en la lista **Hoja de cálculo**.
   
   Nota: después de seleccionar la hoja aparecen dos cuadros adicionales en la tarjeta **Insert row** (Insertar tarjeta). Dichos cuadros representan las dos columnas de la hoja que creó anteriormente.
3. Seleccione el cuadro **ClickType** y, después, seleccione el token **Click type** (Tipo de clic).
4. Seleccione el cuadro **Timestamp** y, después, seleccione el token **Click time** (Hora de clic).
   
    ![configurar datos de Hojas de cálculo de Google](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>Confirme que la configuración del correo electrónico es correcta
1. Confirme que la tarjeta **Send me an email notification** (Enviarme una notificación por correo electrónico).
   
    ![confirmar notificación por correo electrónico](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>Guarde el flujo y pruébelo.
1. Asigne un nombre al flujo y guárdelo.
   
    ![guardar el flujo](./media/flic-button-flows/save.png)

Si ha seguido todos los pasos, al presionar el Flic una vez se desencadena el flujo. Después, el flujo registra el tipo de clic y la hora actual en la hoja y le envía un correo electrónico.

1. Presione una vez el Flic.
2. Abra la hoja de cálculo en Hojas de cálculo de Google. Debería ver que las columnas **ClickType** y **Timestamp** están llenas con el "clic" y la hora, respectivamente.
   
    ![ver resultados de ejecución](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. Los resultados de la ejecución también se pueden ver desde el sitio web de Power Automate o desde la aplicación móvil Power Automate. Esta es una captura de pantalla de la ejecución de prueba.
   
    ![guardar el flujo](./media/flic-button-flows/flic-test-run-results-portal.png)
4. Este es el cuerpo del correo electrónico de notificación que he recibido de la ejecución del flujo.
   
    ![guardar el flujo](./media/flic-button-flows/flic-email-body.png)

Si lo desea, puede considerar la posibilidad de extender el flujo para grabar automáticamente su ubicación (latitud y longitud) cuando se presiona el Flic.

## <a name="more-information"></a>Más información
* [Compartir flujos de botones en Microsoft Flow](share-buttons.md).
* Aprenda a usar [tokens de desencadenadores de botones](introduction-to-button-trigger-tokens.md) para enviar datos activos cuando se ejecuten los flujos de botón.
* Instale la aplicación móvil de Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).

