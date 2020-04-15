---
title: Administración de aprobaciones de páginas de SharePoint con Power Automate | Microsoft Docs
description: Aprenda a administrar aprobaciones de páginas de SharePoint con Power Automate.
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
ms.date: 04/06/2020
ms.author: deonhe
ms.openlocfilehash: 5fa6c10245c5fbc974ae96dd926c8e5b193aaab4
ms.sourcegitcommit: c43c98cc777780d42d15e287233c040771a6e147
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2020
ms.locfileid: "80801512"
---
# <a name="manage-sharepoint-page-approvals-with-power-automate"></a>Administración de aprobaciones de páginas de SharePoint con Power Automate


Los administradores de sitios de SharePoint pueden usar Power Automate para exigir la aprobación de páginas de sitio nuevas o actualizadas antes de publicarse.

En este artículo, aprenderá a configurar el sitio de SharePoint para que use un flujo que exija que se aprueben los cambios en el sitio antes de que se apliquen.

## <a name="configure-sharepoint-for-page-approvals"></a>Configuración de SharePoint para aprobaciones de páginas

### <a name="prerequisites"></a>Requisitos previos 

Debe ser administrador del sitio de SharePoint para realizar las actividades de este artículo.

1. Inicie sesión en SharePoint como administrador del sitio.
1. Seleccione **Páginas** en la barra de navegación.

    ![Seleccionar flujo de aprobación de páginas](media/customize-sharepoint-page-approvals/pages.png)

1. Seleccione **Automatizar** > **Power Automate** > **Configurar flujo de aprobación de páginas**.
    
    ![Seleccionar flujo de aprobación de páginas](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. Seleccione **Crear flujo**.

1. De forma opcional, es posible que tenga que iniciar sesión en los servicios que esta plantilla de Power Automate usa.

1. Seleccione **Continuar**.

1. Proporcione un valor para **Nombre del flujo**, al menos un nombre en el cuadro **Aprobadores** y, luego, seleccione **Crear**.
    
    ![Seleccionar flujo de aprobación de páginas](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

Eso es todo. Ahora, cada vez que se agrega o se modifica una página, se envía una solicitud de aprobación a los **Aprobadores** que se muestran en el flujo.

El flujo de aprobación de páginas es igual que cualquier otro flujo, por lo que se muestra en la pestaña **Mis flujos**.

![Seleccionar flujo de aprobación de páginas](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Envío de una página para su aprobación

Ahora que ha creado un flujo de aprobación de páginas, cualquier persona que agregue o cambie una página deberá hacer lo siguiente:

 - Realice un cambio en el sitio (agregue una nueva página, por ejemplo) y, luego, guarde el cambio.

     ![Envío de página para aprobación](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Espere a que alguien apruebe el cambio.
    
    ![Envío de página para aprobación](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Aprobación de una página

Los aprobadores reciben un correo electrónico cada vez que hay una solicitud de aprobación de páginas. Pueden aprobar las solicitudes directamente en el correo electrónico (si su cliente de correo electrónico admite mensajes accionables) o abrir la página del correo electrónico para revisar y, luego, aprobar la página en SharePoint.

## <a name="customize-page-approval-flows"></a>Personalización de los flujos de aprobación de páginas

Dado que en las aprobaciones de páginas se usa Power Automate en segundo plano, el flujo de aprobación de páginas está disponible para que los propietarios del sitio modifiquen y agreguen lógica de negocios personalizada al flujo. Para modificar el flujo, el propietario del sitio puede seleccionar **Flujos** y, después, **Ver los flujos** en la biblioteca de páginas para buscar el flujo de aprobación de páginas.

## <a name="learn-more"></a>Más información

- [Flujo de aprobación de páginas](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Configuración de la aprobación de páginas](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
