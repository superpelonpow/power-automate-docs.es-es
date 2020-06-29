---
title: Utilice la acción Aplicar a cada uno para recorrer en iteración una matriz de elementos. | Microsoft Docs
description: Utilice Power Automate para recorrer en iteración una matriz de elementos y comprobar varias condiciones y actuar en función de esas condiciones.
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
ms.date: 05/06/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: fcd99ea786c03eeac6ceabdf9a97886a8bbee022
ms.sourcegitcommit: 8714786a5b632dfd60099871629cf369a31c4125
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346618"
---
# <a name="use-the-apply-to-each-action-in-power-automate-to-process-a-list-of-items-periodically"></a>Utilización de la acción Aplicar a cada uno en Power Automate para procesar periódicamente una lista de elementos

Algunos desencadenadores pueden iniciar inmediatamente un flujo basado en un evento, como cuando llega un nuevo correo electrónico a la Bandeja de entrada. Estos desencadenadores son excelentes, pero a veces se quiere ejecutar un flujo que consulte un origen de datos según una programación predefinida mediante la realización de determinadas acciones en función de las propiedades de los elementos del origen de datos. Para ello, puede iniciar el flujo según una programación (por ejemplo, una vez al día) y usar una acción de bucle como **Aplicar a cada** para procesar una lista de elementos. Por ejemplo, podría utilizar **Aplicar a cada uno** para actualizar registros de una base de datos o una lista de elementos de Microsoft SharePoint.

En este tutorial, vamos a crear un flujo que se ejecuta cada 15 minutos y que hace lo siguiente:

1. Obtiene los últimos 10 mensajes no leídos de la Bandeja de entrada de Office 365 Outlook.
2. Comprueba cada uno de los 10 mensajes para confirmar si alguno tiene **Reunirse ahora** en el asunto.
3. Comprueba si el correo electrónico es de su jefe o se envió con importancia alta.
4. Envía una notificación push y marca como leído cualquier correo electrónico que tenga **Reunirse ahora** en el asunto y que sea de su jefe o se haya enviado con importancia alta.

En este diagrama se muestran los detalles del flujo de que vamos a crear:

![información general sobre el flujo que se está generando](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>Requisitos previos
Estos son los requisitos para realizar correctamente los pasos de este tutorial:

* Una cuenta que esté registrada para usar [Power Automate](https://flow.microsoft.com).
* Una cuenta de Office 365 Outlook.
* La aplicación móvil de Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).
* Conexiones a Office 365 Outlook y al servicio de notificaciones push.

## <a name="create-a-flow"></a>Crear un flujo
1. Inicie sesión en [Power Automate](https://flow.microsoft.com).
1. Seleccione **Mis flujos** > **Nuevo** > **Programado: desde cero**.
1. Especifique un nombre para el flujo en **Nombre de flujo**, en la pantalla **Creación de un flujo programado**. 
1. Configure la programación que se va a ejecutar cada 15 minutos. 
1. Seleccione **Crear** 
   
    ![ejecuciones de programación](./media/apply-to-each/foreach-3.png) 

1. Seleccione **+ Nuevo paso** y escriba **outlook** en el cuadro de búsqueda para buscar todos los conectores y todas las acciones relacionados con Microsoft Outlook.
1. Seleccione la acción **Obtener correos electrónicos (V3)**:
1. Se abre la tarjeta **Obtener correos electrónicos (V3)**. Configure la tarjeta **Obtener correos electrónicos (V3)** para seleccionar los 10 primeros correos electrónicos no leídos en la carpeta Bandeja de entrada. No incluya archivos adjuntos porque no se usarán en el flujo:
   
    ![configurar tarjeta de correo electrónico](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Hasta ahora, ha creado un flujo simple que obtiene algunos correos electrónicos de la Bandeja de entrada. Estos correos electrónicos se devolverán en una matriz; la acción **Aplicar a cada uno** requiere una matriz, por lo que esto es exactamente lo que se necesita.

## <a name="add-actions-and-conditions"></a>Agregar acciones y condiciones
1. Seleccione la acción **Nuevo paso** > **Integrado** > **Aplicar a cada uno**.
1. Inserte el token **valor** en el campo **Seleccionar una salida de los pasos anteriores** en la tarjeta **Aplicar a cada uno**. Esto extrae el cuerpo de los correos electrónicos que se usarán en la acción **Aplicar a cada uno**:
   
    ![agregar token de cuerpo](./media/apply-to-each/foreach-7.png)
1. Seleccione **Nuevo paso** > **Control** > **Condición**.
1. Configure la tarjeta **Condición** para buscar las palabras "Reunirse ahora" en el asunto de cada correo electrónico:
   
   * Insertar el token **Asunto** en el primer campo de la tarjeta **Condición**.
   * Seleccione **contiene** en la lista de operadores.
   * Escriba **reunión ahora** en el tercer campo.
     
     ![configurar condición](./media/apply-to-each/foreach-subject-condition.png)
1. Seleccione **Agregar una acción** > **Condición** en la rama **En caso afirmativo**. Se abrirá la tarjeta **Condición 2**; configure esa tarjeta de esta forma:
   
   * Insertar el token **Importancia** en el primer campo.
   * Seleccione **es igual a** en la lista de operadores.
   * Introduzca **alta** en el campo de la derecha.
     
     ![agregar condición](./media/apply-to-each/foreach-importance-condition.png)
1. Seleccione **Agregar una acción** en la sesión **En caso afirmativo**.     
   Esto abre la tarjeta **Elegir una acción**, donde podrá definir qué ocurre si la condición de búsqueda (el correo electrónico **reunirse ahora** se envió con importancia alta) es un valor true:
1. Busque **Notificación** y, después, seleccione la acción **Send me a mobile notification** (Enviarme una notificación del servicio móvil):
   
    ![buscar y seleccionar notificación](./media/apply-to-each/foreach-10.png)
1. En la tarjeta **Send me a mobile notification** (Enviarme una notificación del servicio móvil), proporcione los detalles de la notificación de inserción que se enviará si el asunto de un correo electrónico contiene "reunirse ahora" y la **Importancia** está establecida en **alta**.
   
    ![configurar notificación](./media/apply-to-each/foreach-11.png)

1. Si vuelve a la tarjeta **Condición 2**, en la rama **En caso negativo**:
    
    * Seleccione **Agregar una acción** y escriba **obtener administrador** en el cuadro de búsqueda.
    * Seleccione la acción **Obtener administrador (V2)** en la lista de resultados de la búsqueda.
    * Introduzca el token **Para** en el cuadro **Usuario (UPN)** de la tarjeta **Obtener administrador (V2)**.
      
      ![agregar y configurar acción obtener administrador](./media/apply-to-each/foreach-get-manager.png)
1. Seleccione **Agregar una acción** en la rama **En caso afirmativo**.
1. Seleccione **Condición** en la tarjeta **Elegir una acción**. Se abrirá la tarjeta **Condición 3**; configure la tarjeta para comprobar si la dirección de correo electrónico del remitente (el token De) es igual a la dirección de correo electrónico de su jefe (el token Correo electrónico):
    
    * Inserte el token **De** en el primer cuadro.
    * Seleccione **contiene** en la lista de operadores.
    * Introduzca el token **correo** en el cuadro de la derecha.
      
      ![configurar condición de búsqueda](./media/apply-to-each/foreach-condition3-card.png)
1. Seleccione **Agregar una acción** en la sección **En caso afirmativo** de la tarjeta **Condición 3**.
    
A continuación, va a definir lo que debe ocurrir si la condición de búsqueda (el correo electrónico se envió desde la dirección de su jefe) es un valor true:

1. Busque **Notificación** y, después, seleccione la acción **Send me a mobile notification** (Enviarme una notificación del servicio móvil):
    
     ![buscar acción de notificación](./media/apply-to-each/foreach-10.png)
1. En la tarjeta **Send me a mobile notification 2** (Enviarme una notificación del servicio móvil 2), proporcione los detalles de la notificación de inserción que se enviará si el correo electrónico procede de su jefe y, después, seleccione **Agregar una acción**:
    
     ![configurar tarjeta de notificación](./media/apply-to-each/foreach-boss-notification.png)
1. Agregue la acción **Marcar como leído o como no leído (V2)**.
1. Agregue el token **Id. de mensaje** a la tarjeta **Marcar como leído o como no leído (V2)**. Es posible que tenga que seleccionar **Ver más** para encontrar el token **Id. de mensaje**. El **Id. de mensaje** es el identificador del mensaje que se va a marcar como leído.
1. Seleccione **Leído** en la lista **Marcar como** de la tarjeta **Marcar como leído o como no leído (V2)**.
    
     ![configurar acción marcar como leído](./media/apply-to-each/foreach-mark-as-read2.png)
1. Seleccione **Guardar** para guardar el flujo.

## <a name="run-the-flow"></a>Ejecución del flujo
1. Envíese un correo electrónico de importancia alta que incluya **reunirse ahora** en el asunto (o pida a alguien de su organización que le envíe este mensaje de correo electrónico).
1. Confirme que el correo electrónico se encuentra en la Bandeja de entrada y no está leído.
1. Inicie sesión en Power Automate y seleccione **Mis flujos**.
   
    Se muestra una lista de sus flujos. 
    
1. Seleccione el flujo que acaba de crear y después seleccione **Ejecutar**.

   ![ejecutar ahora](./media/apply-to-each/run-flow.png)

1. Seleccione **Página de ejecuciones de flujo** y después seleccione la ejecución de flujo en la que está interesado para ver los resultados.
   
    ![resultados de la ejecución](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Ver los resultados de la ejecución
Ahora que ha ejecutado el flujo correctamente, debería recibir la notificación de inserción en el dispositivo móvil.
   
> [!NOTE]
> Si no recibe la notificación de inserción, confirme que el dispositivo móvil tiene una conexión de datos activa.
 

