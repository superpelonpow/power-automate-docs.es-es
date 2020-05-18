---
title: Espera de la aprobación de un flujo | Microsoft Docs
description: Los flujos pueden esperar hasta que se produzca un evento externo, como que un usuario apruebe o rechace un cambio, antes de realizar una acción, como enviar la notificación de la decisión.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2018
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 34e17dbb8fdc1c3b3f6ba835b80c687504b9abd6
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298383"
---
# <a name="wait-for-approval-in-power-automate"></a>Espere aprobación en Power Automate


> [!VIDEO https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]
>


Cree un flujo que, si crea un elemento en SharePoint, envíe un mensaje de aprobación y luego le avise de si el elemento se ha aprobado o rechazado. Para seguir este tutorial con precisión, cree una lista simple de SharePoint como acción desencadenante, pero puede usar otro origen de datos, como Dropbox o OneDrive.

**Requisitos previos**

* Cree una lista simple de SharePoint denominada **Seguimiento de proyectos**, agregue una columna denominada **Título** y luego una columna de persona o grupo denominada **Asignado a**.

   ![Imagen de la lista de SharePoint Online Seguimiento de proyectos](./media/wait-for-approvals/project-tracker.png)

## <a name="add-an-event-to-trigger-the-flow"></a>Adición de un evento que desencadene el flujo

1. Inicie sesión en [Power Automate](https://flow.microsoft.com), seleccione **Mis flujos** en la barra de navegación superior y luego **Crear desde cero**.

1. Seleccione el cuadro **Buscar entre cientos de conectores y desencadenadores**, escriba **nuevo elemento** y luego vaya a **SharePoint - Cuando se crea un elemento**.

1. Si se le solicita, inicie sesión en SharePoint.
1. En **Dirección del sitio**, escriba la dirección URL del sitio de SharePoint que contiene la lista.

1. En **Nombre de lista**, seleccione la lista que ha creado anteriormente. Si va siguiendo el tutorial, el nombre es **Seguimiento de proyectos**.

    ![Imagen de nombre de lista de SPO](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>Adición de la acción resultante

1. Seleccione el botón **Nuevo paso** y luego **Agregar una acción**.

1. En el cuadro **Buscar en todos los conectores y acciones**, escriba o pegue **enviar correo electrónico** y luego seleccione **Office 365 Outlook - Enviar correo electrónico con opciones**.

1. Si se le solicita, inicie sesión en Office 365 Outlook.

1. Seleccione el campo **Para** y luego el token **Asignado a correo electrónico**.

    El usuario de la columna **Asignado a** recibe el correo electrónico para aprobar o rechazar elementos. Cuando cree un elemento para probar el flujo, especifíquese a sí mismo en este campo. De esa forma, no solo aprueba o rechaza el elemento, sino que también recibe el correo electrónico de notificación.

    > [!NOTE]
    > Puede personalizar los campos **Asunto** y **Opciones de usuario** para que se ajusten a sus necesidades.

    ![Imagen del campo Enviar correo electrónico de aprobación a](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>Agrega una condición

1. Seleccione el botón **Nuevo paso** y luego **Agregar una condición**.

    ![Imagen de Agregar una condición](./media/wait-for-approvals/add-a-condition.png)
1. Seleccione el primer cuadro y luego el token **SelectedOption**.
1. Seleccione el último cuadro y luego escriba **Aprobar**.

    ![Imagen de la tarjeta de condición](./media/wait-for-approvals/condition-card-2.png)

1. En el área **Si sí**, seleccione **Agregar una acción**.

1. En el cuadro **Buscar en todos los conectores y acciones**, escriba o pegue **enviar correo electrónico** y luego seleccione **Office 365 Outlook - Enviar correo electrónico**.

1. En el campo **Para**, escriba un destinatario como **Creado por correo electrónico**.

1. En el cuadro **Asunto**, especifique un asunto.

    Por ejemplo, seleccione **Assigned To DisplayName**, escriba **ha aprobado** con un espacio en cada lado y, luego, seleccione **Título**.

1. En el cuadro **Cuerpo**, especifique un cuerpo del correo electrónico como **Listo para continuar con la siguiente fase del proyecto.**

    > [!NOTE]
    > A la persona que creó el elemento en la lista de SharePoint se le notificará si el proyecto se ha aprobado o rechazado.

    ![Imagen de Sí-enviar-correo electrónico](./media/wait-for-approvals/if-yes-send-email-card-3.png)

1. En el área **Si no**, repita los últimos cinco pasos, excepto cambiar el contenido de los campos **Asunto** y **Cuerpo** para reflejar que el proyecto se ha rechazado.

     ![Imagen de No-enviar-correo electrónico](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>Finalización y prueba del flujo

1. Asigne un nombre al flujo y, luego, seleccione **Crear flujo**.

     ![Imagen de Crear flujo](./media/wait-for-approvals/create-flow.png)
1. Cree un elemento en la lista de SharePoint.

    Se envía un correo electrónico de aprobación al destinatario especificado. Cuando el destinatario selecciona **Aprobar** o **Rechazar** en ese correo, usted recibe un correo electrónico en el que se indica la respuesta.

## <a name="learn-more"></a>Más información

* [Tutorial de aprobaciones modernas de un aprobador único](modern-approvals.md)
* Crear [aprobaciones secuenciales](sequential-modern-approvals.md)
* Crear [aprobaciones en paralelo](parallel-modern-approvals.md)
* Aprobar [solicitudes sobre la marcha](mobile-approvals.md)
