---
title: Utilice la acción Aplicar a cada uno para recorrer en iteración una matriz de elementos. | Microsoft Docs
description: Use Power Automate para recorrer en iteración una matriz de elementos a fin de comprobar varias condiciones y actuar en función de estas.
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
ms.date: 03/16/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3f4ddd361eaad062a7287c1d0b33e00fc320e69e
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74357919"
---
# <a name="use-the-apply-to-each-action-in-power-automate-to-process-a-list-of-items-periodically"></a>Uso de la acción Aplicar a cada uno de Power Automate para procesar periódicamente una lista de elementos
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Algunos desencadenadores pueden iniciar inmediatamente un flujo basado en un evento, como cuando llega un nuevo correo electrónico a la Bandeja de entrada. Estos desencadenadores son excelentes, pero a veces se quiere ejecutar un flujo que consulte un origen de datos según una programación predefinida mediante la realización de determinadas acciones en función de las propiedades de los elementos del origen de datos. Para ello, puede iniciar el flujo según una programación (por ejemplo, una vez al día) y usar una acción de bucle como **Aplicar a cada** para procesar una lista de elementos. Por ejemplo, podría utilizar **Aplicar a cada uno** para actualizar registros de una base de datos o una lista de elementos de Microsoft SharePoint.

En este tutorial, vamos a crear un flujo que se ejecuta cada 15 minutos y que hace lo siguiente:

1. Obtiene los últimos 10 mensajes no leídos de la Bandeja de entrada de Office 365 Outlook.
2. Comprueba cada uno de los 10 mensajes para confirmar si alguno tiene **Reunirse ahora** en el asunto.
3. Comprueba si el correo electrónico es de su jefe o se envió con importancia alta.
4. Envía una notificación push y marca como leído cualquier correo electrónico que tenga **Reunirse ahora** en el asunto y que sea de su jefe o se haya enviado con importancia alta.

Este diagrama muestra los detalles del flujo de que vamos a crear en este tutorial:

![información general sobre el flujo que se está generando](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>Requisitos previos
Estos son los requisitos para realizar correctamente los pasos de este tutorial:

* Una cuenta que esté registrada para usar [Power Automate](https://flow.microsoft.com).
* Una cuenta de Office 365 Outlook.
* La aplicación móvil de Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).
* Conexiones a Office 365 Outlook y el servicio de notificación push.

## <a name="create-a-flow"></a>Creación de un flujo
1. Inicie sesión en [Power Automate](https://flow.microsoft.com):
2. Seleccione la pestaña **Mis flujos** y cree un flujo desde cero:
   
    ![crear desde cero](./media/apply-to-each/foreach-1.png)
3. Escriba "programación" en el cuadro de búsqueda para buscar todos los servicios y desencadenadores que están relacionados con la programación.
4. Seleccione el desencadenador **Programación - Periodicidad** para indicar que el flujo se va a ejecutar en una programación que proporcionará a continuación:
   
    ![acción de periodicidad de la programación](./media/apply-to-each/foreach-2.png)
5. Configure la programación que se va a ejecutar cada 15 minutos:
   
    ![ejecuciones de programación](./media/apply-to-each/foreach-3.png)
6. Seleccione **+ Nuevo paso**, **Agregar una acción** y, después, escriba **Outlook** en el cuadro de búsqueda para buscar todas las acciones relacionadas con Microsoft Outlook.
7. Seleccione la acción **Office 365 Outlook - Obtener correos electrónicos** :
   
    ![seleccionar acción obtener correos electrónicos](./media/apply-to-each/foreach-4.png)
8. Se abrirá la tarjeta **Obtener correos electrónicos**. Configurar la tarjeta **Obtener correos electrónicos** para seleccionar los 10 primeros correos electrónicos no leídos en la carpeta Bandeja de entrada. No incluya archivos adjuntos porque no se usarán en el flujo:
   
    ![configurar tarjeta de correo electrónico](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Hasta ahora, ha creado un flujo simple que obtiene algunos correos electrónicos de la Bandeja de entrada. Estos correos electrónicos se devolverán en una matriz; la acción **Aplicar a cada uno** requiere una matriz, por lo que esto es exactamente lo que se necesita.
   > 
   > 

## <a name="add-actions-and-conditions"></a>Agregar acciones y condiciones
1. Seleccione **+ Nuevo paso**, **Más** y, después, la acción **Agregar Aplicar a cada uno**:
   
    ![seleccionar aplicar a cada uno](./media/apply-to-each/foreach-6.png)
2. Inserte el token **Cuerpo** en el cuadro **Seleccionar una salida de los pasos anteriores** en la tarjeta **Aplicar a cada uno**. Esto extrae el cuerpo de los correos electrónicos que se usarán en la acción **Aplicar a cada uno**:
   
    ![agregar el token cuerpo](./media/apply-to-each/foreach-7.png)
3. Seleccione **Agregar una condición**:
   
    ![agregar condición](./media/apply-to-each/foreach-8.png)
4. Configure la tarjeta **Condición** para buscar el asunto de cada correo electrónico para las palabras "Reunirse ahora":
   
   * Inserte el token **Asunto** en el cuadro **Nombre de objeto**.
   * Seleccione **contiene** en la lista **Relación**.
   * Escriba **Reunirse ahora** en el cuadro **Valor**.
     
     ![configurar condición](./media/apply-to-each/foreach-subject-condition.png)
5. Seleccione **Más** y después seleccione **Agregar una condición** en la rama **IF YES, DO NOTHING** (En caso positivo, no hacer nada). Se abrirá la tarjeta **Condición 2**; configure esa tarjeta de esta forma:
   
   * Inserte el token **Importancia** en el cuadro **Nombre de objeto**.
   * Seleccione **es igual a** en la lista **Relación**.
   * Escriba **Alta** en el cuadro **Valor**.
     
     ![agregar condición](./media/apply-to-each/foreach-importance-condition.png)
6. Seleccione **Agregar una acción** en la sección **IF YES, DO NOTHING** (En caso positivo, no hacer nada). Esto abrirá la tarjeta **Elegir una acción**, donde podrá definir qué debe ocurrir si la condición de búsqueda (el correo electrónico **Reunirse ahora** se envió con importancia alta) es un valor true:
   
    ![agregar acción](./media/apply-to-each/foreach-9.png)
7. Busque **Notificación** y, después, seleccione la acción **Notifications - Send me a mobile notification** (Notificaciones - Enviarme una notificación del servicio móvil):
   
    ![buscar y seleccionar notificación](./media/apply-to-each/foreach-10.png)
8. En la tarjeta **Send me a mobile notification** (Enviarme una notificación del servicio móvil), proporcione los detalles de la notificación push que se enviará si el asunto de un correo electrónico contiene "Reunirse ahora" y, después, seleccione **Agregar una acción**:
   
    ![configurar notificación](./media/apply-to-each/foreach-11.png)
9. Escriba **leer** como término de búsqueda y seleccione la acción **Office 365 Outlook - Marcar como leído**. Esto marcará cada correo electrónico como leído después de enviar la notificación push:
   
    ![agregar acción marcar como leído](./media/apply-to-each/foreach-12.png)
10. Agregue el token **Id. de mensaje** al cuadro **Id. de mensaje** de la tarjeta **Marcar como leído**. Es posible que tenga que seleccionar **Ver más** para encontrar el token **Id. de mensaje**. Esto indica el identificador del mensaje que se va a marcar como leído:
    
     ![agregar identificador de mensaje](./media/apply-to-each/foreach-13.png)
11. Si vuelve a la tarjeta **Condición 2**, de la rama **IF NO, DO NOTHING** (En caso negativo, no hacer nada):
    
    * Seleccione **Agregar una acción** y escriba **Obtener administrador** en el cuadro de búsqueda.
    * Seleccione la acción **Usuarios de Office 365 - Obtener administrador** en la lista de resultados de la búsqueda.
    * Escriba su dirección de correo electrónica *completa* en el cuadro **Usuario** de la tarjeta **Obtener administrador**.
      
      ![agregar y configurar acción obtener administrador](./media/apply-to-each/foreach-get-manager.png)
12. Seleccione **Más** y después seleccione **Agregar una condición** en la rama **EN CASO NEGATIVO**. Se abrirá la tarjeta **Condición 3**; configure la tarjeta para comprobar si la dirección de correo electrónico del remitente (el token De) es igual a la dirección de correo electrónico de su jefe (el token Correo electrónico):
    
    * Inserte el token **De** en el cuadro **Nombre de objeto**.
    * Seleccione **contiene** en la lista **Relación**.
    * Introduzca el token **Correo electrónico** en el cuadro **Valor**.
      
      ![configurar la condición de búsqueda](./media/apply-to-each/foreach-condition3-card.png)
13. Seleccione **Agregar una acción** en la sección **IF YES, DO NOTHING** (En caso negativo, no hacer nada) de la tarjeta **Condición 3**. Esto abrirá la tarjeta **EN CASO POSITIVO**, donde podrá definir qué debe ocurrir si la condición de búsqueda (el correo electrónico se envió desde la dirección de su jefe) es un valor true:
    
     ![configurar condición](./media/apply-to-each/foreah-condition3-add-action.png)
14. Busque **Notificación** y, después, seleccione la acción **Notifications - Send me a mobile notification** (Notificaciones - Enviarme una notificación del servicio móvil):
    
     ![buscar acción de notificación](./media/apply-to-each/foreach-10.png)
15. En la tarjeta **Send me a mobile notification 2** (Enviarme una notificación del servicio móvil 2), proporcione los detalles de la notificación push que se enviará si el correo electrónico procede de su jefe y, después, seleccione **Agregar una acción**:
    
     ![tarjeta configurar notificación](./media/apply-to-each/foreach-boss-notification.png)
16. Agregue la acción **Office 365 Outlook - Marcar como leído**. Esto marcará cada correo electrónico como leído después de enviar la notificación push:
    
     ![agregar acción marcar como leído](./media/apply-to-each/foreach-12.png)
17. Agregue el token **Id. de mensaje** utilizado para la tarjeta **Marcar como leído 2**. Es posible que tenga que seleccionar **Ver más** para encontrar el token **Id. de mensaje**. Esto indica el identificador del mensaje que se va a marcar como leído:
    
     ![configurar acción marcar como leído](./media/apply-to-each/foreach-mark-as-read2.png)
18. Asigne un nombre al flujo y vuelva a crearlo:
    
     ![asignar un nombre al flujo y guardarlo](./media/apply-to-each/foreach-14.png)

Si ha seguido todo el proceso, el flujo debe ser similar al de este diagrama:

![información general sobre el flujo creado](./media/apply-to-each/foreach-flow-finished.png)

## <a name="run-the-flow"></a>Ejecución del flujo
1. Envíese un correo electrónico de importancia alta que incluya **Reunirse ahora** en el asunto (o pida a alguien de su organización que le envíe este mensaje de correo electrónico).
2. Confirme que el correo electrónico se encuentra en la Bandeja de entrada y no está leído.
3. Inicie sesión en Power Automate, seleccione **Mis flujos** y, después, seleccione **Ejecutar ahora**:
   
    ![ejecutar ahora](./media/apply-to-each/foreach-run-1.png)
4. Seleccione **Ejecutar flujo** para confirmar que realmente desea ejecutar el flujo:
   
    ![confirmar ejecución](./media/apply-to-each/foreach-run-2.png)
5. Transcurridos unos instantes, debería ver los resultados de la ejecución correcta:
   
    ![resultados de la ejecución](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Visualización de los resultados de la ejecución
Ahora que ha ejecutado el flujo correctamente, debería recibir la notificación push en el dispositivo móvil.

1. Abra la aplicación Power Automate en su dispositivo móvil y, luego, seleccione la pestaña **Actividad**. Verá la notificación push sobre la reunión:
   
    ![seleccionar pestaña actividad](./media/apply-to-each/foreach-notification-1.png)
2. Para ver todo el contenido de la notificación, puede que tenga que seleccionar la notificación. Verá la notificación completa, de forma similar a la siguiente:
   
    ![detalles de la notificación](./media/apply-to-each/foreach-notification-2.png)
   
   > [!NOTE]
   > Si no recibe la notificación push, confirme que el dispositivo móvil tiene una conexión de datos activa.
   > 
   > 

