---
title: Ejecución de flujos en función de las propiedades del correo electrónico | Microsoft Docs
description: Inicie un flujo basándose en propiedades como el asunto, la dirección del remitente o la del destinatario de un correo electrónico.
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
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f7588a3ca1db5c62a4e60380575542671e8d408d
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297877"
---
# <a name="trigger-a-flow-based-on-email-properties"></a>Desencadenamiento de un flujo basado en las propiedades del correo electrónico

Use el desencadenador **Cuando llega un correo electrónico nuevo** para crear un flujo que se ejecuta cuando una o varias de las propiedades de correo electrónico que se indican a continuación coinciden con los criterios que ha proporcionado:

| Propiedad | Cuándo usar |
| --- | --- |
| Carpeta |Desencadene un flujo cada vez que lleguen correos electrónicos a una carpeta concreta. Esta propiedad puede ser útil si tiene reglas que enruten los correos electrónicos a carpetas diferentes. |
| Hasta |Desencadene un flujo en función de la dirección a la que se envió un correo electrónico. Esta propiedad puede ser útil cuando se recibe correo electrónico que se envió a direcciones de correo electrónico diferente en la misma Bandeja de entrada. |
| De |Desencadene un flujo en función de la dirección de correo electrónico del remitente. |
| Importancia |Desencadene un flujo basado en la importancia con la que se enviaron los mensajes de correo electrónico. El correo electrónico puede enviarse con importancia alta, normal o baja. |
| Tiene datos adjuntos |Desencadene un flujo en función de la presencia de datos adjuntos en los correos electrónicos entrantes. |
| Filtro de asunto |Busque la presencia de palabras específicas en el asunto de un correo electrónico. Después, el flujo ejecutará *acciones* basadas en los resultados de la búsqueda. |

> [!IMPORTANT]
> Cada [plan de Power Automate](https://flow.microsoft.com/pricing/) incluye una cuota de ejecución. Siempre que sea posible, compruebe las propiedades en el desencadenador del flujo. De esta forma, evitará usar la cuota de ejecución de forma innecesaria. Si selecciona una propiedad en una condición, cada ejecución cuenta en la cuota de ejecución del plan, incluso si no se cumple la condición de filtro que ha definido. 

Por ejemplo, si comprueba la dirección *de* de un correo electrónico en una condición, cada ejecución se descuenta de la cuota de ejecución de su plan, aunque no proceda *de* la dirección que le interesa.
> 
> 

En los tutoriales siguientes, comprobamos todas las propiedades del desencadenador **Cuando llega un correo electrónico nuevo**. Puede obtener más información en las páginas de [preguntas más frecuentes sobre facturación](billing-questions.md#what-counts-as-a-run) y [precios](https://ms.flow.microsoft.com/pricing/).

## <a name="prerequisites"></a>Requisitos previos
* Una cuenta con acceso a [Power Automate](https://flow.microsoft.com)
* Una cuenta de Office 365 Outlook
* La aplicación móvil de Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).
* Conexiones a Office, Outlook y al servicio de notificaciones push

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>Desencadenamiento de un flujo basado en el asunto del correo electrónico
En este tutorial, vamos a crear un flujo que envía una notificación push a su teléfono móvil si el asunto de cualquier correo electrónico nuevo tiene la palabra "lotería" en él. El flujo marca después cualquier correo electrónico como *leído*.

>[!NOTE]
>Aunque en este tutorial se envía una notificación push, está libre de usar cualquier otra acción que se adapte a las necesidades del flujo de trabajo. Por ejemplo, podría almacenar el contenido del correo electrónico en otro repositorio como Google Sheets o un archivo de Microsoft Excel almacenado en Dropbox.

De acuerdo, empecemos:

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. En el cuadro **Filtro de asunto**, escriba el texto que usa el flujo para filtrar los correos electrónicos entrantes.
   
     En este ejemplo, nos interesa cualquier correo electrónico que contenga la palabra "lotería" en el asunto.
   
    ![Opciones avanzadas](./media/email-triggers/email-triggers-subject-text.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Escriba los detalles de la notificación móvil que quiere recibir cuando le llegue un correo electrónico que coincide con el **filtro de asunto** especificado.
   
    ![Detalles de la notificación](./media/email-triggers/email-triggers-4.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Asígnele un nombre al flujo. Después, guárdelo seleccionando **Crear flujo** en la parte superior de la página.
   
    ![Guardar flujo](./media/email-triggers/email-triggers-subject-notification.png)

Enhorabuena. Recibirá una notificación push cada vez que reciba un correo electrónico que contenga la palabra "lotería" en el asunto.

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>Desencadenamiento de un flujo basado en remitente del correo electrónico
En este tutorial, vamos a crear un flujo que envía una notificación push a su teléfono móvil si llega cualquier correo electrónico nuevo procedente de un remitente específico (dirección de correo electrónico). El flujo marca también cualquier correo electrónico como *leído*.

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. En el cuadro **De**, escriba la dirección de correo electrónico del remitente. 
   
     El flujo realiza una acción sobre los correos electrónicos enviados desde esta dirección.
   
    ![Propiedad de correo electrónico](./media/email-triggers/email-triggers-from.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Escriba los detalles de la notificación móvil que le gustaría recibir siempre que llegue un mensaje de la dirección de correo electrónico que ha especificado anteriormente.
   
    ![Detalles de la notificación](./media/email-triggers/email-triggers-sender-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Asigne un nombre a su flujo y, después, guárdelo seleccionando **Crear flujo** en la parte superior de la página.
   
    ![Guardar flujo](./media/email-triggers/email-triggers-sender-5.png)

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>Desencadenamiento de un flujo cada vez que lleguen correos electrónicos a una carpeta concreta
Si tiene reglas que enrutan los correos electrónicos a carpetas diferentes en función de ciertas propiedades, como la dirección, puede que desee este tipo de flujo.

Empecemos:

> [!NOTE]
> Si aún no tiene una regla que enrute el correo electrónico a una carpeta distinta de la Bandeja de entrada, cree dicha regla y confirme que funciona mediante el envío de un mensaje de prueba.
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. Seleccione la carpeta a la que va a enrutar determinados correos electrónicos. Para mostrar todas las carpetas de correo electrónico, primero seleccione el icono **Mostrar selector**, que se encuentra a la derecha del cuadro **Carpeta** en la tarjeta **Cuando llega un correo electrónico nuevo**.
   
    ![Seleccionar carpeta](./media/email-triggers/email-triggers-2.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Escriba los detalles de la notificación móvil que le gustaría recibir siempre que llegue un correo electrónico a la carpeta que ha seleccionado anteriormente. Si no lo ha hecho ya, escriba las credenciales para el servicio de notificaciones.
   
    ![Detalles de la notificación](./media/email-triggers/email-triggers-folder-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Asigne un nombre a su flujo y, después, guárdelo seleccionando **Crear flujo** en la parte superior de la página.
   
    ![Guardar flujo](./media/email-triggers/email-triggers-7.png)

Pruebe el flujo enviando un correo electrónico que se enrute a la carpeta que ha seleccionado anteriormente en este tutorial.

