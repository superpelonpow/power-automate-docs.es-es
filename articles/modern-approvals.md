---
title: Automatice fácilmente los flujos de trabajo de aprobación. | Microsoft Docs
description: Automatice los flujos de trabajo de aprobación que se integran con SharePoint, Dynamics CRM, Salesforce, One Drive para la Empresa, Zendesk o WordPress.
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
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4892ac2806009a1ed33b8bfb019b551aec6fce70
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "79224317"
---
# <a name="create-and-test-an-approval-workflow-with-power-automate"></a>Creación y prueba de un flujo de trabajo de aprobación con Power Automate


Con Power Automate, puede administrar la aprobación de documentos o procesos en varios servicios, entre los que se incluyen SharePoint, Dynamics 365, Salesforce, OneDrive para la Empresa, Zendesk o WordPress.

Para crear un flujo de trabajo de aprobación, agregue la acción **Approvals - Start an approval** (Aprobaciones - Iniciar una aprobación) a cualquier flujo. Después de agregar esta acción, el flujo puede administrar la aprobación de documentos o procesos. Por ejemplo, puede crear flujos de aprobación de documentos que aprueben facturas, pedidos de trabajo o presupuestos de ventas. También puede crear flujos de aprobación de proceso que aprueben solicitudes de vacaciones, horas extras o planes de viajes.

Los aprobadores pueden responder a las solicitudes desde la bandeja de entrada del correo electrónico, el [centro de aprobaciones](https://flow.microsoft.com/manage/approvals/received/) del sitio web de Power Automate o la aplicación Power Automate.

## <a name="create-an-approval-flow"></a>Creación de un flujo de aprobación
Esta es una visión general del flujo de que vamos a crear y probar:

   ![información general del flujo](./media/modern-approvals/create-flow-overview.png)

El flujo realiza los pasos siguientes:

1. Se inicia cuando alguien crea una solicitud de vacaciones en una lista de SharePoint Online.
2. Agrega la solicitud de vacaciones en el centro de aprobaciones y, después, la envía por correo electrónico al aprobador.
3. Envía un correo electrónico con la decisión del aprobador a la persona que solicita las vacaciones.
4. Actualiza la lista de SharePoint Online con la decisión y los comentarios del aprobador.

## <a name="prerequisites"></a>Requisitos previos
Para completar este tutorial, debe tener acceso a:

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Cree estas columnas en la lista de SharePoint Online:

   ![Columnas de lista de SharePoint Online](./media/modern-approvals/sharepoint-list-fields.png)

Tome nota del nombre y la dirección URL de la lista de SharePoint Online. Necesitará estos elementos después al configurar el desencadenador **SharePoint - Cuando se crea un elemento**.

## <a name="create-your-flow-from-the-blank-template"></a>Creación del flujo en la plantilla en blanco
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Adición de un desencadenador

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

La **dirección del sitio** y el **nombre de la lista** son los elementos que anotó anteriormente en este tutorial.

![Información de SharePoint](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>Adición de una acción de perfil

1. Seleccione **Nuevo paso** y, luego, **Agregar una acción**.
   
    ![nuevo paso](./media/modern-approvals/select-sharepoint-add-action.png)
2. Escriba **perfil** en el cuadro de búsqueda **Elegir una acción**.
   
    ![buscar perfil](./media/modern-approvals/search-for-profile.png)
3. Busque y, después, seleccione la acción **Usuarios de Office 365 - Obtener mi perfil**.
   
    ![seleccionar usuarios de office](./media/modern-approvals/select-my-profile.png)
4. Proporcione un nombre para el flujo y, después, seleccione **Crear flujo** para guardar el trabajo que hemos hecho hasta ahora.
   
    ![guardar flujo](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>Adición de una acción de aprobación

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> Esta acción envía la solicitud de aprobación a la dirección de correo electrónico en el cuadro **Asignado a**.
>
> Si su escenario lo requiere, puede adjuntar archivos a las solicitudes de aprobación que usan Common Data Service.

## <a name="add-a-condition"></a>Agregar una condición

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>Adición de una acción de correo electrónico para aprobaciones

Siga estos pasos para enviar un correo electrónico si se aprueba la solicitud de vacaciones:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar plantilla de correo electrónico aprobado](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>Adición de una acción de actualización para las solicitudes aprobadas

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> Los campos **Dirección del sitio**, **Nombre de la lista**, **Identificador** y **Título** son necesarios.
>
>

![actualizar configuración de elemento](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>Adición de una acción de correo electrónico para rechazos

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![configuración de solicitudes rechazadas](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>Adición de acción de actualización para las solicitudes rechazadas

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > Los campos **Dirección del sitio**, **Nombre de la lista**, **Identificador** y **Título** son necesarios.
   >
   >

![tarjeta actualizar elemento](./media/modern-approvals/configure-update-item-no.png)

1. Seleccione **Actualizar flujo** para guardar el trabajo que hemos hecho.
   
    ![seleccionar actualizar acción](./media/modern-approvals/update.png)

Si ha seguido estos pasos, el flujo debe ser similar al de esta captura de pantalla:

![información general del flujo](./media/modern-approvals/completed-flow.png)

Ahora que hemos creado el flujo, es el momento de probarlo.

## <a name="request-an-approval"></a>Solicitud de una aprobación

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]


## <a name="create-long-running-approvals"></a>Creación de aprobaciones de larga duración

Si es probable que el flujo se ejecute durante más de 30 días, considere la posibilidad de almacenar las aprobaciones en Common Data Service. Esto permite crear flujos que actúan sobre las respuestas a las solicitudes de aprobación, incluso después de que se agote el tiempo de espera de la ejecución del flujo original. Para hacerlo, use dos flujos, uno para enviar una solicitud de aprobación y el otro para ejecutar la lógica de negocios en las respuestas a la solicitud de aprobación, en función de la acción **Crear una aprobación (V2)** . Más información sobre las [aprobaciones de larga duración](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/long-lived-approvals-other-approval-improvements).

>[!TIP]
> Si usa clientes de correo electrónico modernos, no tiene que preguntarse si todavía se requiere una solicitud, porque Power Automate actualiza automáticamente el correo electrónico para indicar que se completó la aprobación.

## <a name="cancel-an-approval-requests"></a>Cancelación de solicitudes de aprobación

En algunas ocasiones, es posible que quiera cancelar una solicitud de aprobación que haya enviado. Posiblemente haya cometido un error en la solicitud o esta ya no sea relevante. En cualquier caso, la persona que envió la solicitud puede cancelarla siguiendo estos pasos:

1. Seleccione la aprobación.
1. Seleccione **Cancelar aprobación** en el panel lateral.

>[!TIP]
>Siempre puede seleccionar la pestaña **Historial** para ver las solicitudes de aprobación que canceló.

>[!NOTE]
> La característica de cancelación es compatible con la acción **Crear una aprobación (v2)** .

## <a name="request-approvals-from-guest-users"></a>Solicitud de aprobaciones de usuarios invitados

Puede enviar solicitudes de aprobación a personas ajenas a la organización. Para hacerlo, use los usuarios invitados de Azure Active Directory (Azure AD) para [invitar a los usuarios de otros inquilinos como invitados](https://docs.microsoft.com/azure/active-directory/b2b/add-user-without-invite).

Cuando asigna un rol a un invitado, se proporciona al invitado el permiso necesario para participar en el proceso de aprobación.

Ahora que ha creado y probado el flujo, asegúrese de que los demás sepan cómo usarlo.

## <a name="learn-more"></a>Más información

* Vea y administre [solicitudes de aprobación pendientes](approve-reject-requests.md)
* Cree [flujos de aprobación secuenciales.](sequential-modern-approvals.md)
* Cree [flujos de aprobación en paralelo.](parallel-modern-approvals.md)
* Instale la aplicación móvil de Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).
