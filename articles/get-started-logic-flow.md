---
title: Automatización de tareas mediante la creación de un flujo | Microsoft Docs
description: Cree un flujo que realice automáticamente una o más acciones, como enviar correo electrónico, cuando se produzcan eventos, como que alguien agregue una fila a una lista de SharePoint.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/04/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 569408367130c6f5121b30d2c8c14833b142b934
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74368798"
---
# <a name="create-a-flow-in-power-automate"></a>Creación de un flujo en Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

> [!VIDEO https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]

Cree un flujo que realizará una o varias tareas automáticamente después de que un evento lo desencadene. Por ejemplo, cree un flujo que le envíe una notificación por correo electrónico cuando alguien envíe un tweet que contenga una palabra clave que especifique. En este ejemplo, el envío de un tweet es el evento y el envío de correo es la acción.

## <a name="prerequisites"></a>Requisitos previos

* Una cuenta en [flow.microsoft.com](https://flow.microsoft.com)
* Una cuenta de Twitter
* Credenciales de Office 365

## <a name="specify-an-event-to-start-the-flow"></a>Especificación del evento que va a iniciar el flujo

En primer lugar, será preciso que seleccione el evento, o *desencadenador*, que inicia el flujo.

1. En [flow.microsoft.com](https://flow.microsoft.com), seleccione **Mis flujos** en la barra de navegación superior y, después, seleccione **Crear desde cero**.

    ![Opciones de flujos de la barra de navegación izquierda](./media/get-started-logic-flow/create-logic-flow.png)
1. Seleccione el cuadro **Buscar entre cientos de conectores y desencadenadores** en la parte inferior de la pantalla, escriba **Twitter** en el cuadro que indica **Buscar en todos los conectores y desencadenadores** y luego seleccione **Twitter - Cuando se publica un nuevo tweet**.

    ![Evento de Twitter](./media/get-started-logic-flow/twitter-search.png)

   >[!TIP]
   >Los conectores admiten varios tipos de autenticación. Por ejemplo, SQL Server admite Azure AD, autenticación de SQL Server, autenticación de Windows y cadena de conexión SQL. Los usuarios eligen qué tipo de autenticación desean usar al configurar un conector.

1. Si todavía no ha conectado su cuenta de Twitter con Power Automate, seleccione **Iniciar sesión en Twitter** y, luego, escriba sus credenciales.

1. En el cuadro **Buscar texto**, escriba la palabra clave que desea buscar.

    ![Palabra clave de Twitter](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Especificación de una acción

1. Seleccione **Nuevo paso** y, luego, **Agregar una acción**.

    ![Agregar acción](./media/get-started-logic-flow/add-action-icon.png)

1. En el cuadro **Buscar todos los conectores y acciones**, escriba o pegue **enviar correo electrónico** y seleccione **Office 365 Outlook - Enviar un correo electrónico**.

    ![Lista de acciones](./media/get-started-logic-flow/send-email.png)

1. Si se le solicita, seleccione el botón de inicio de sesión y especifique sus credenciales.

1. En el formulario que aparece, escriba o pegue la dirección de correo electrónico en el **Para** y, a continuación, seleccione el nombre en la lista de contactos que aparece.

    ![Mensaje de correo electrónico en blanco](./media/get-started-logic-flow/blank-email.png)
1. En el cuadro **Asunto**, escriba o pegue **Nuevo tweet de:** y, a continuación, agregue un espacio.

    ![Línea de asunto con marcador de posición](./media/get-started-logic-flow/message-token.png)
1. En la lista de tokens, seleccione **Twitteado por** para agregarle un marcador de posición.

    ![Agregar parámetro](./media/get-started-logic-flow/add-parameter.png)
1. Seleccione el cuadro **Cuerpo** y luego el token **Texto del tweet** para agregarle un marcador de posición.
1. (opcional) Agregue más tokens, otro tipo de contenido, o ambas cosas, al cuerpo del correo electrónico.
1. Cerca de la parte superior de la pantalla, asigne un nombre al flujo y, después, seleccione **Crear flujo**.

    ![Seleccionar el botón Crear flujo](./media/get-started-logic-flow/create-button.png)
1. Seleccione **Listo** para actualizar la lista de flujos.

     ![Seleccionar el botón Listo](./media/get-started-logic-flow/done-button.png)
1. Envíe un tweet con la palabra clave que ha indicado o espere a que otra persona publique un tweet de este tipo.

     Menos de un minuto después de la publicación del tweet, un mensaje de correo electrónico le notifica el nuevo tweet.

> [!TIP]
> Use la acción **Enviar correo electrónico (V2)** para dar formato al correo electrónico personalizando la fuente; usando negrita, cursiva o subrayado; adaptando el color y el resaltado; y creando listas o vínculos, entre otras posibilidades.

![Correo electrónico con edición enriquecida](media/get-started-logic-flow/email-rich-text.png)

## <a name="manage-a-flow"></a>Administración de un flujo

1. En [flow.microsoft.com](https://flow.microsoft.com), seleccione **Mis flujos** en la barra de navegación superior.
1. En la lista de flujos, realice una de las siguientes acciones:

   * Para pausar un flujo, establezca el control de alternancia en **Desactivar**.

       ![Pausar el flujo](./media/get-started-logic-flow/pause-flow.png)
   * Para reanudar un flujo, establezca el control de alternancia en **Activar**.

       ![Reanudar el flujo](./media/get-started-logic-flow/resume-flow.png)
   * Para editar un flujo, seleccione el icono de lápiz correspondiente al flujo que quiere editar.

       ![Seleccionar flujo](./media/get-started-logic-flow/select-flow.png)
   * Para eliminar un flujo, seleccione el icono **...** , seleccione **Eliminar**y, después, seleccione **Eliminar** en el cuadro de mensaje que aparece.

       ![Icono de eliminar](./media/get-started-logic-flow/delete-icon.png)
   * Para ver el historial de ejecuciones de un flujo, seleccione dicho flujo en la página **Mis flujos de** y vea el historial de la sección **HISTORIAL DE EJECUCIONES** de la página que se abre.

       ![historial de ejecuciones](./media/get-started-logic-flow/run-history.png)

     Seleccione una ejecución de flujo en la lista de ejecuciones para ver las entradas y salidas de cada paso.

> [!NOTE]
> La cuenta puede tener un máximo de 600 flujos. Si ya los tiene, para crear uno es preciso eliminar otro antes.
>
>

## <a name="next-steps"></a>Pasos siguientes

* [Agregue pasos](multi-step-logic-flow.md), como las diferentes formas de recibir una notificación, a su flujo.
* [Ejecute las tareas según una programación](run-scheduled-tasks.md), cuándo desea que una acción se produzca: cada día, en una fecha concreta o después de un número determinado de minutos.
* [Agregue un flujo a una aplicación](https://powerapps.microsoft.com/tutorials/using-logic-flows/) para que la aplicación pueda iniciar la lógica en la nube.
* [Cree flujos de equipo](create-team-flows.md) e invite a otros a colaborar en el diseño de flujos.
