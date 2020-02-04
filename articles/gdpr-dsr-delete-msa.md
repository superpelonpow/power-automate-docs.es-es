---
title: Solicitudes de eliminación del interesado de acuerdo con el RGPD en Power Automate para cuentas de Microsoft (MSA) | Microsoft Docs
description: Obtenga información sobre cómo usar Power Automate para responder a solicitudes de eliminación del interesado de acuerdo con el RGPD para cuentas de Microsoft.
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
ms.date: 5/25/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: b9ef70579798b353ddcd8a961604665a287cd63a
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74368154"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>Respuesta a solicitudes de eliminación del interesado de acuerdo con el RGPD
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

El **derecho al olvido** mediante la eliminación de datos personales es una protección clave en el RGPD. La eliminación de datos personales incluye la eliminación de todos los datos personales excepto la información del registro de auditoría.

Power Automate permite a los usuarios crear flujos de trabajo automatizados. Cuando un usuario decide eliminar sus datos personales de Power Automate, puede revisarlos y determinar si se deben eliminar algunos o todos.

En la siguiente tabla se muestra qué datos personales se eliminan de manera automática y cuáles requieren un usuario de cuenta de Microsoft (MSA) para revisarlos y eliminarlos.

|Requiere el usuario de MSA para la revisión y eliminación|Se eliminan automáticamente|
|------|------|
|Actividad de productos y servicios|Historial de ejecución|
|Flujos|Fuente de actividades|
|Conexiones||

Power Automate ofrece las experiencias siguientes para ayudar a los usuarios a buscar, revisar o cambiar los datos personales que no se eliminan de forma automática:

## <a name="manage-delete-requests"></a>Administración de las solicitudes de eliminación

En los pasos siguientes se describe cómo iniciar solicitudes de eliminación de autoservicio de acuerdo con el RGPD.

### <a name="delete-product-and-service-activity"></a>Eliminar actividad de productos y servicios

1. Inicie sesión en el [panel de privacidad de Microsoft](https://account.microsoft.com/privacy/) con la MSA.
1. Haga clic en el vínculo **Historial de actividades**.

    ![Historial de actividades](./media/gdpr-dsr-export-msa/activityhistory.png)

1. En el historial de actividades puede buscar o examinar las distintas aplicaciones y servicios de Microsoft que usa, incluido Power Automate. Haga clic en **Eliminar** para quitar eventos de actividad de productos o servicios determinados.

    ![Eliminar evento](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. Tras unos instantes, el elemento se elimina y se quita del panel de privacidad.

### <a name="list-and-delete-flows"></a>Enumerar y eliminar flujos

Un usuario puede enumerar y eliminar sus flujos de [Power Automate](https://flow.microsoft.com) mediante estos pasos:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com) y seleccione **Mis flujos**.

1. Haga clic en **...** junto al flujo que se va a eliminar y, después, seleccione **Eliminar**.

    ![Eliminar evento](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>Eliminar conexiones

Los conectores usan conexiones para comunicarse con API y sistemas SaaS. Las conexiones incluyen referencias al usuario que las crea. El usuario puede eliminar estas referencias en cualquier momento mediante estos pasos:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com), haga clic en el icono de engranaje y, después, seleccione **Conexiones**.

    ![Eliminar evento](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. Seleccione la conexión que quiera eliminar, haga clic en **...** y, después, seleccione **Eliminar**.

    ![Eliminar evento](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. Haga clic en el icono **Eliminar** en el mensaje de confirmación.

    ![Eliminar evento](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> Si la conexión que va a eliminar se usa en otros flujos, se le notificará que se requiere una conexión nueva. En caso contrario, haga clic en **Eliminar** para continuar.
>
>

## <a name="learn-more"></a>Más información

* Introducción a [Power Automate](getting-started.md).
* Información sobre las [novedades](release-notes.md) de Power Automate.
