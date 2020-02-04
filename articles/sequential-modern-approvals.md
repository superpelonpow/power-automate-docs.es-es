---
title: Creación de un flujo de trabajo de aprobación moderno con varios aprobadores | Microsoft Docs
description: 'Creación de un flujo de trabajo de aprobación moderno con varios aprobadores '
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
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
ms.openlocfilehash: e8f7b993b59c269b56dac2f13d4db166ed3e91b7
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74373076"
---
# <a name="manage-sequential-approvals-with-power-automate"></a>Administración de aprobaciones secuenciales con Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Algunos flujos de trabajo requieren la aprobación previa antes de que se requiera al aprobador final que cierre la sesión. Por ejemplo, una compañía puede tener una directiva de aprobación secuencial que requiere la aprobación previa de las facturas de más de 1000 USD antes de que estén aprobados por el departamento de finanzas.

En este tutorial, creamos un flujo de aprobación secuencial que administra las solicitudes de vacaciones de los empleados.

> [!NOTE]
> SharePoint se usa aquí solo como ejemplo; no es necesario crear flujos de aprobación. Puede usar cualquiera de los más de 200 servicios con los que Power Automate se integra para impulsar los flujos.


## <a name="detailed-steps-in-the-flow"></a>Pasos detallados del flujo
El flujo:

1. Se inicia cuando un empleado crea una solicitud de vacaciones en una [lista de SharePoint Online](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7).
2. Agrega la solicitud de vacaciones en el centro de aprobaciones y, después, envía por correo electrónico la solicitud al aprobador previo.
3. Envía por correo electrónico la decisión de aprobación previa al empleado.
4. Actualiza la lista de SharePoint Online con la decisión y los comentarios del aprobador previo.
   
   Nota: Si la solicitud se ha aprobado previamente, el flujo continuará con estos pasos:
5. Envía la solicitud al aprobador final.
6. Envía por correo electrónico la decisión final al empleado.
7. Actualiza la lista de SharePoint con la decisión final.

Esta imagen resume los pasos anteriores:

   ![diagrama de Visio del flujo](./media/sequential-modern-approvals/visio-overview.png)

## <a name="prerequisites"></a>Requisitos previos
[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Para este tutorial, la lista de SharePoint Online que crea debe incluir estas columnas:

   ![Columnas de la lista de SharePoint](./media/sequential-modern-approvals/sharepoint-columns.png)

Tome nota del nombre y la dirección URL de la lista de SharePoint Online. Usamos estos elementos después al configurar el desencadenador **SharePoint - Cuando se crea un elemento**.

## <a name="create-your-flow-from-the-blank-template"></a>Creación del flujo en la plantilla en blanco
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Adición de un desencadenador
[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![información de sharepoint](./media/sequential-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Obtención del administrador de la persona que creó la solicitud de vacaciones
[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

1. Proporcione un nombre para el flujo y, después, seleccione **Crear flujo** para guardar el trabajo que hemos hecho hasta ahora.
   
    ![guardar flujo](./media/sequential-modern-approvals/save.png)
   
   > [!NOTE]
   > Seleccione **Actualizar flujo** en la parte superior de la pantalla periódicamente para guardar los cambios en el flujo.
   > 
   > 
   
    ![seleccionar actualizar acción](./media/sequential-modern-approvals/update.png)

Después de cada operación de guardado, seleccione **Editar flujo** en la parte superior de la pantalla y, después, continúe haciendo cambios.

## <a name="add-an-approval-action-for-pre-approvals"></a>Adición de una acción de aprobación para aprobaciones previas
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

Nota: Esta acción envía la solicitud de aprobación previa a la dirección de correo electrónico en el cuadro **Asignado a**.

## <a name="add-a-condition"></a>Agregar una condición
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

> [!NOTE]
> Esta condición comprueba la respuesta de la acción **Start an approval** (Iniciar una aprobación).
> 
> 

## <a name="add-an-email-action-for-pre-approvals"></a>Adición de una acción de correo electrónico para aprobaciones previas
[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar plantilla de correo electrónico previamente aprobado](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-pre-approved-requests"></a>Adición de una acción de actualización para las solicitudes previamente aprobadas
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![actualizar configuración de elemento](./media/sequential-modern-approvals/configure-update-item.png)

## <a name="get-the-pre-approvers-manager"></a>Obtención del administrador del aprobador previo
1. Use los pasos de [Obtención del administrador de la persona que creó la solicitud de vacaciones](sequential-modern-approvals.md#get-the-manager-for-the-person-who-created-the-vacation-request) que se realizaron anteriormente para agregar y configurar otra acción **Obtener administrador**. Esta vez vamos a obtener el administrador del aprobador previo.
2. La tarjeta **Obtener administrador 2** debe ser similar a la de esta imagen cuando haya terminado. Asegúrese de utilizar el token **Correo electrónico** de la categoría **Obtener administrador** de la tarjeta **Agregue contenido dinámico de las aplicaciones y servicios que se usan en este flujo**
   
   ![obtener administrador del aprobador previo](includes/media/modern-approvals/get-pre-approver-manager.png)

## <a name="add-the-final-approval-action"></a>Adición de la acción de aprobación final
1. Siga los pasos de [Adición de una acción de aprobación para aprobaciones previas](sequential-modern-approvals.md#add-an-approval-action-for-pre-approvals) que se realizaron anteriormente para agregar y, después, configure otra acción **Start an approval** (Iniciar una aprobación). Esta acción envía una solicitud de correo electrónico para la aprobación final.
2. Cuando haya terminado, la tarjeta debe ser similar a la de esta imagen:
   
    ![configurar la aprobación](./media/sequential-modern-approvals/provide-approval-config-info.png)

## <a name="add-the-final-approval-condition"></a>Adición de la condición de aprobación final
1. Repita los pasos de [agregar una condición](sequential-modern-approvals.md#add-a-condition) para agregar y configurar una **condición** que comprueba la decisión del aprobador final.

## <a name="send-email-with-final-approval"></a>Envío de correo electrónico con aprobación final
1. Siga los pasos de [Adición de una acción de correo electrónico para aprobaciones previas](sequential-modern-approvals.md#add-an-email-action-for-pre-approvals) para agregar y configurar una acción que envía un correo electrónico cuando se aprueban las solicitudes de vacaciones.
2. Cuando haya terminado, la tarjeta debe ser similar a la de esta imagen:
   
   ![plantilla de correo electrónico de aprobación final](./media/sequential-modern-approvals/vacatioin-request-approved-email-template.png)

## <a name="update-sharepoint-with-approval"></a>Actualización de SharePoint con aprobación
1. Siga los pasos de [Adición de una acción de actualización para las solicitudes aprobadas previamente](sequential-modern-approvals.md#add-an-update-action-for-pre-approved-requests) para agregar y configurar una acción que actualiza SharePoint cuando se aprueba la solicitud de vacaciones.
2. Cuando haya terminado, la tarjeta debe ser similar a esta imagen:
   
    ![actualizar configuración de elemento](./media/sequential-modern-approvals/configure-update-item-approved.png)

## <a name="send-email-with-pre-approval-rejection"></a>Envío de correo electrónico con el rechazo de la aprobación previa
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

   ![configuración de solicitudes rechazadas](./media/sequential-modern-approvals/configure-rejected-email.png)

Nota: Esta acción debe agregarse a la rama **IF NO, DO NOTHING** (En caso negativo, no hacer nada) que aparece en la tarjeta **Condición**.

## <a name="update-sharepoint-with-pre-approval-rejection"></a>Actualización de SharePoint con el rechazo de la aprobación previa
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   ![actualizar sharepoint para solicitudes rechazadas](./media/sequential-modern-approvals/update-sharepoint-with-rejection.png)

## <a name="send-email-with-final-rejection"></a>Envío de correo electrónico con rechazo final
1. Siga los pasos de [Envío de correo electrónico con el rechazo de la aprobación previa](sequential-modern-approvals.md#send-email-with-pre-approval-rejection) para agregar y configurar una acción que envía un correo electrónico cuando el aprobador final rechaza la solicitud de vacaciones.
   
    Nota: Esta acción debe agregarse a la rama **IF NO, DO NOTHING** (En caso negativo, no hacer nada) que aparece en la tarjeta **Condición 2**.
2. Cuando haya terminado, la tarjeta debe ser similar a esta imagen:
   
   ![configuración de solicitudes rechazadas](./media/sequential-modern-approvals/final-rejection-email-card.png)

## <a name="update-sharepoint-with-final-rejection"></a>Actualización de SharePoint con el rechazo final
1. Siga los pasos de [Actualización de SharePoint con el rechazo de la aprobación previa](sequential-modern-approvals.md#update-sharepoint-with-pre-approval-rejection) para agregar y configurar una acción que actualiza SharePoint cuando el aprobador final rechaza la solicitud de vacaciones.
2. Cuando haya terminado, la tarjeta debe ser similar a esta imagen:
   
   ![tarjeta actualizar elemento](./media/sequential-modern-approvals/final-rejection-update-sharepoint.png)
3. Seleccione **Actualizar flujo** para guardar el trabajo que hemos hecho.
   
   ![seleccionar actualizar acción](./media/sequential-modern-approvals/update.png)

Si ha seguido estos pasos, el flujo debe ser similar al de esta imagen:

![información general del flujo](./media/sequential-modern-approvals/completed-flow.png)

Ahora que hemos creado el flujo, vamos a verlo en acción.

## <a name="request-an-approval"></a>Solicitud de una aprobación
[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

La solicitud debe ser similar a la de esta imagen:

![solicitud de vacaciones](./media/sequential-modern-approvals/vacation-request.png)

## <a name="view-pending-approval-requests"></a>Visualización de las solicitudes de aprobación pendiente
[!INCLUDE [view-pending-approvals](includes/view-pending-approvals.md)]

## <a name="pre-approve-a-request"></a>Aprobación previa de una solicitud
[!INCLUDE [approve-request-from-different-locations](includes/approve-request-from-different-locations.md)]

## <a name="approve-the-request"></a>Aprobación de la solicitud
Los pasos para aprobar una solicitud son idénticos a los pasos para [aprobar previamente una solicitud](sequential-modern-approvals.md#pre-approve-a-request).

Nota: El aprobador final obtiene la solicitud de vacaciones solo después de la aprobación previa de la solicitud.

## <a name="reject-a-request"></a>Rechazo de una solicitud
[!INCLUDE [reject-a-request](includes/reject-a-request.md)]

## <a name="more-information"></a>Más información
[Tutorial de aprobaciones modernas de un aprobador único](modern-approvals.md)

