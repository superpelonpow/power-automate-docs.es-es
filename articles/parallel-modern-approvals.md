---
title: Creación de un flujo de trabajo de aprobaciones modernas en paralelo | Microsoft Docs
description: Creación de un flujo de trabajo de aprobaciones modernas en paralelo
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
ms.date: 05/09/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9515fee127c1130803f075c6b6a08802a7c1eaea
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296997"
---
# <a name="create-parallel-approval-workflows-with-power-automate"></a>Creación de flujos de trabajo de aprobaciones en paralelo con Power Automate


En un flujo de trabajo de aprobación paralelo, se requieren varias personas para aprobar artículos tales como facturas, órdenes de compra, solicitudes de vacaciones, etc. La aprobación de cada persona es independiente de todos los demás aprobadores.

En este tutorial, usamos Power Automate para crear un flujo que automatiza un flujo de trabajo de aprobaciones en paralelo. Este flujo automatiza un proceso de solicitud de vacaciones de los empleados que requiere la aprobación de todas las personas (o equipos) con los que el empleado colabora regularmente. Los empleados usan una [lista de SharePoint](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) para solicitar vacaciones. Son necesarias las aprobaciones de las vacaciones por parte del administrador directo del empleado, el equipo de ventas y el equipo de recursos humanos. Cada solicitud de vacaciones se enruta a cada aprobador para que tome una decisión. El flujo envía un correo electrónico con los cambios de estado y, después, actualiza SharePoint con las decisiones.

## <a name="prerequisites"></a>Requisitos previos

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

La lista de SharePoint Online que cree debe incluir las columnas siguientes:

   ![Columnas de lista de SharePoint](./media/parallel-modern-approvals/sharepoint-columns.png)

Tome nota del nombre y la dirección URL de la lista de SharePoint Online. Usamos estos elementos después al configurar el desencadenador **SharePoint - Cuando se crea un elemento**.

## <a name="create-your-flow-from-the-blank-template"></a>Creación del flujo en la plantilla en blanco

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Adición de un desencadenador

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![Información de SharePoint](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Obtención del administrador de la persona que creó la solicitud de vacaciones

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>Asignación de un nombre al flujo y guardarlo

1. Indique un nombre para el flujo y, después, seleccione el icono **Guardar** para guardar el trabajo que hemos hecho hasta ahora.

   ![guardar flujo](./media/parallel-modern-approvals/save.png)

> [!NOTE]
> Seleccione **Guardar** cada cierto tiempo para guardar los cambios en el flujo.
> 
> 


## <a name="add-an-approval-action-for-immediate-manager"></a>Adición de una acción de aprobación para el administrador inmediato

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!IMPORTANT]
> Esta acción envía la solicitud de vacaciones a la dirección de correo electrónico del cuadro **Asignado a**, por tanto inserte el token **Correo electrónico** en la lista **Obtener el administrador (v2)**.
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>Inserción de una acción de aprobación en la rama paralela para el equipo de ventas

1. Seleccione la flecha hacia abajo que se encuentra entre la tarjeta **Obtener el administrador (v2)** y la tarjeta **Iniciar una aprobación**.
2. Seleccione el signo más que se muestra en la flecha hacia abajo después de haberla seleccionado.
3. Seleccione **Add a parallel branch** (Agregar una rama paralela).
4. Seleccione **Agregar una acción**.

    ![configuración de obtener administrador](./media/parallel-modern-approvals/add-parallel-branch.png)
5. Busque, seleccione y, después, configure una acción **Start an approval** (Iniciar una aprobación) que envía la solicitud de vacaciones al equipo de ventas. Consulte los [pasos seguidos para agregar una acción de aprobación para el administrador inmediato](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager) si no está seguro de cómo agregar la acción **Iniciar una aprobación**.

> [!IMPORTANT]
> Use la dirección de correo electrónico del equipo de ventas en el cuadro **Asignado a** de la acción **Iniciar una aprobación 2**.
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>Inserción de una acción de aprobación en la rama paralela para el equipo de recursos humanos

1. Repita los pasos para [insertar una rama paralela para el equipo de ventas](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team) con objeto de agregar y configura una acción **Iniciar una aprobación** para enviar las solicitudes de vacaciones a recursos humanos.

> [!IMPORTANT]
> Use la dirección de correo electrónico del equipo de recursos humanos en el cuadro **Asignado a** de la acción **Iniciar una aprobación 3**.
> 
> 

Si ha seguido estos pasos, el flujo debe ser similar al de este ejemplo:

   ![flujo con ramas paralelas](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>Opciones después de agregar ramas paralelas

Después de agregar acciones a las ramas paralelas, tienes dos opciones para agregar más pasos al flujo:

1. Utilice el botón pequeño de **inserción de un nuevo paso** (el botón circular con un signo más que aparece cuando se selecciona cualquier espacio en blanco en una rama o en la zona justo debajo de una rama). Este botón agrega un paso a esa **rama concreta**. Los pasos que agregue con este botón se ejecutan una vez completada esta rama concreta.
1. Use botón más grande **Nuevo paso** situado en la parte inferior del flujo de trabajo completo. Los pasos que agregue con este botón se ejecutan una vez completadas todas las ramas.

En las siguientes secciones, se usa el botón pequeño de **inserción de un nuevo paso** para realizar estos pasos en cada rama:

* Agregue una condición que comprueba si se aprueba o rechaza la solicitud de vacaciones.
* Envíe un correo electrónico que informa a los empleados de la decisión.
* Actualice la solicitud de vacaciones en SharePoint con la decisión de aprobación.

A continuación, usamos el botón **Nuevo paso** más grande para enviar un correo electrónico que resume todas las decisiones tomadas sobre la solicitud de vacaciones.

Sigamos:

## <a name="add-a-condition-to-each-branch"></a>Adición de una condición a cada rama

1. Seleccione cualquier espacio en blanco en la rama **Start an approval** (Iniciar una aprobación).
2. Seleccione el botón pequeño de **inserción de un nuevo paso** (el botón circular con un signo más que aparece cuando se selecciona el espacio en blanco en el paso anterior).
3. Seleccione **Agregar una condición** en el menú que se muestra.
4. Seleccione el primer cuadro en la tarjeta **Condición** y, después, seleccione el token **Respuesta** de la categoría **Start an approval** (Iniciar una aprobación) en la lista de contenido dinámica.

    ![flujo con condición de ramas paralelas](./media/parallel-modern-approvals/configure-approval-condition.png)
5. Confirme que la lista (en el medio de la **tarjeta de condición**) se establece en **es igual a**.
6. Escriba **Aprobar** (este texto distingue mayúsculas de minúsculas) en el último cuadro.
7. Su tarjeta de condición debe ser similar a la de esta imagen:

    ![flujo con condición de ramas paralelas](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > Esta condición comprueba la respuesta de la acción **Start an approval** (Iniciar una aprobación) que se dirige al administrador del empleado.
   > 
   > 
8. Repita los pasos anteriores en las ramas **Start an approval 2** (Iniciar una aprobación 2) (la solicitud de aprobación para ventas) y **Start an approval 3** (Iniciar una aprobación 3) (la solicitud de aprobación para recursos humanos).

## <a name="add-email-actions-to-each-branch"></a>Adición de acciones de correo electrónico a cada rama

Realice los siguientes pasos en la sección **EN CASO POSITIVO** de la rama **Condición**.

   Nota: El flujo usa estos pasos para enviar un correo electrónico cuando se aprueba la solicitud:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar plantilla de correo electrónico previamente aprobado](includes/media/parallel-modern-approvals/yes-email-config.png)

Para enviar un correo electrónico cuando se rechaza una solicitud, use el lado **EN CASO NEGATIVO** de la rama **Condición** y, después, repita los pasos anteriores para agregar una plantilla al correo electrónico de rechazo.

Repita los pasos anteriores en las ramas **Start an approval 2** (Iniciar una aprobación 2) (la solicitud de aprobación para ventas) y **Start an approval 3** (Iniciar una aprobación 3) (la solicitud de aprobación para recursos humanos).

## <a name="update-the-vacation-request-with-the-decision"></a>Actualización de la solicitud de vacaciones con la decisión

Realice los pasos siguientes para actualizar SharePoint cuando se toman decisiones.

   Nota: Asegúrese de realizar estos pasos en ambos lados **IF YES** (En caso positivo) y **IF NO** (En caso negativo) de la sucursal.

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![actualizar configuración de elemento](./media/parallel-modern-approvals/configure-update-item.png)

Repita los pasos anteriores en las ramas **Start an approval 2** (Iniciar una aprobación 2) y **Start an approval 3** (Iniciar una aprobación 3).

## <a name="complete-the-flow"></a>Finalización del flujo

1. Seleccione **Nuevo paso** > **Agregar una acción**.

    ![actualizar configuración de elemento](includes/media/parallel-modern-approvals/add-an-action-2-step.png)
1. Utilice los pasos indicados anteriormente para enviar un correo electrónico que resuma los resultados de cada aprobación. Envíe este correo electrónico al empleado que solicitó vacaciones. La tarjeta puede ser similar a la de este ejemplo:

   ![actualizar configuración de elemento](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>Más información sobre las aprobaciones modernas

[Introducción a las aprobaciones modernas](modern-approvals.md)

