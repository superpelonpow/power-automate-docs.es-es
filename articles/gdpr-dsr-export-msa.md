---
title: Solicitudes de exportación de los interesados en el RGPD en Power Automate para cuentas Microsoft (MSA) | Microsoft Docs
description: Aprenda a usar Power Automate para responder a las solicitudes de exportación de los interesado en el RGPD para cuentas Microsoft.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: Deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 487f19badd67650c686c9e497cad739ee1560885
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195112"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-power-automate"></a>Respuesta a las solicitudes de exportación de los interesados en el RGPD para Power Automate


Como parte de nuestro compromiso de acompañarle en su viaje de adaptación al Reglamento general de protección de datos (RGPD), hemos elaborado una documentación que le ayudará a prepararse. En esta documentación no solo se describe lo que estamos haciendo para prepararnos para el RGPD, sino que también se comparten ejemplos de pasos que se pueden adoptar actualmente para el cumplimiento de este reglamento al usar Power Automate.

## <a name="manage-export-requests"></a>Administrar solicitudes de exportación

El *derecho de portabilidad de datos* permite que los interesados soliciten una copia de sus datos personales en formato electrónico (es decir, en un "formato estructurado, de uso frecuente, legible por máquinas e interoperable") que se pueda transmitir a otro controlador de datos.

Use el [panel de privacidad de Microsoft](https://account.microsoft.com/privacy/) o [Power Automate](https://flow.microsoft.com/) para buscar o exportar datos personales de un usuario específico.

|Datos personales|Ubicación|
|-----------------|-------------------|
|Actividad de productos y servicios|Panel de privacidad de Microsoft|
|Flujos|Portal de creadores de Power Automate|
|Historial de ejecución|Portal de creadores de Power Automate|
|Fuente de actividades|Portal de creadores de Power Automate|
|Conexiones|Portal de creadores de Power Automate|

## <a name="export-product-and-service-activity"></a>Exportar actividad de productos y servicios

1. Inicie sesión en el [Panel de privacidad de Microsoft](https://account.microsoft.com/privacy/) con su cuenta de Microsoft (MSA).
1. Seleccione **Historial de actividades**.

    ![Historial de actividades](./media/gdpr-dsr-export-msa/activityhistory.png) Puede examinar el historial de actividades para las distintas aplicaciones de Microsoft y los servicios que usa.
1. Para exportar los datos de **Actividad de productos y servicios**, haga clic en **Descargar los datos** y después en **CREAR UN NUEVO ARCHIVO**.

    ![Descargar los datos](./media/gdpr-dsr-export-msa/downloaddata.png)

1. Seleccione **Uso de aplicaciones y servicios** y, después, haga clic en **Crear archivo**.

    ![Descargar los datos](./media/gdpr-dsr-export-msa/create-archive.png)
1. Se creará un archivo nuevo. Haga clic en **Descargar** para obtener los datos exportados de actividad de productos y servicios.

    ![Descargar](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>Exportación de un flujo

Un usuario final que tenga acceso a un flujo puede exportarlo siguiendo estos pasos:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com/).

1. Seleccione **Mis flujos** y, después, seleccione el flujo que se va a exportar.

1. Seleccione **... Más** y, a continuación, seleccione **Exportar**.

    ![Exportación de flujo](./media/gdpr-dsr-export/export-flow.png)

1. Seleccione **Paquete (.zip)** .

El flujo estará ahora disponible como un paquete comprimido. Para obtener más información, consulte la entrada de blog sobre [cómo exportar e importar un flujo](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exportación de historial de ejecuciones

En el historial de ejecuciones se incluye una lista de todas las ejecuciones de un flujo. Estos datos incluyen el estado del flujo, la hora de inicio, la duración y los datos de entrada/salida para los desencadenadores y las acciones.

Un usuario final que tenga acceso al flujo puede seguir estos pasos para exportar estos datos:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com/).
1. Seleccione el vínculo **Mis flujos** y, a continuación, seleccione el flujo cuyo historial de ejecución desea exportar.
1. En el panel **HISTORIAL DE EJECUCIÓN**, seleccione **Ver todo**.

    ![Historial de ejecución](./media/gdpr-dsr-export/run-history.png)

1. Seleccione **Descargar CSV**.

    ![Descargar CSV](./media/gdpr-dsr-export/download-csv.png)

El historial de ejecuciones se descarga como un archivo .csv para que pueda abrirlo en Microsoft Excel o un editor de texto y analizar los resultados.

## <a name="export-a-users-activity-feed"></a>Exportación de la fuente de actividad de un usuario

En [Power Automate](https://flow.microsoft.com/), la fuente de actividad muestra el historial de actividades, errores y notificaciones de un usuario. Los usuarios pueden ver su fuente de actividad siguiendo estos pasos:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com/), seleccione el icono de campana cerca de la esquina superior derecha y, luego, seleccione **Mostrar todas las actividades**.

    ![Muestra de la fuente de actividades](./media/gdpr-dsr-export/show-activity-feed.png)

1. En la pantalla **Actividad**, copie los resultados y, después, péguelos en un editor de texto como Microsoft Word.

    ![Muestra de la fuente de actividades](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exportación de las conexiones de un usuario

Las conexiones permiten a los flujos conectarse a las API, las aplicaciones de SaaS y otros sistemas de terceros. Siga estos pasos para ver las conexiones:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com/), seleccione el icono de engranaje cerca de la esquina superior derecha y, luego, seleccione **Conexiones**.

    ![Muestra de conexiones](./media/gdpr-dsr-export/show-connections.png)
1. Copie los resultados y, después, péguelos en un editor de texto como Microsoft Word.
