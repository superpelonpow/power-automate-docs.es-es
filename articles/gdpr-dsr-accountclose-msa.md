---
title: Solicitudes de cierre de cuenta del interesado de acuerdo con el RGPD en Power Automate para cuentas Microsoft (MSA) | Microsoft Docs
description: Obtenga información sobre cómo usar Power Automate para responder a solicitudes de cierre de cuenta del interesado de acuerdo con el RGPD para cuentas de Microsoft.
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
ms.openlocfilehash: 277765754683a6690b186a5f592517482b32666f
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74366383"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-power-automate"></a>Respuesta a solicitudes de cierre de cuenta del interesado de acuerdo con el RGPD para Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

El **derecho al olvido** de los datos personales es una protección clave en el RGPD. Este derecho incluye la eliminación de todos los datos personales excepto la información del registro de auditoría. Cuando un usuario decide cerrar su cuenta Microsoft (MSA), también se eliminan los datos subyacentes del usuario.

Estos recursos contienen datos personales que se eliminan de manera automática cuando un usuario cierra una MSA:

|Recursos que contienen datos personales|
|------|
|Actividad de productos y servicios|
|Historial de ejecución|
|Flujos|
|Fuente de actividades|
|Detalles del usuario|
|Conexiones|

## <a name="account-close-requests"></a>Solicitudes de cierre de cuenta

En estos pasos se describe cómo iniciar solicitudes de cierre de cuenta de autoservicio de acuerdo con el RGPD.

1. Inicie sesión en el [portal de cierre de cuenta de Microsoft](https://go.microsoft.com/fwlink/?LinkId=523898) con la cuenta de Microsoft y, después, haga clic en **Siguiente**.

    > [!NOTE]
    > Se le recordará que cancele las suscripciones existentes o que exporte los datos de los servicios existentes a los que se haya suscrito.
    >
    >

    ![Cancelar las suscripciones](./media/gdpr-dsr-delete-msa/accountclose.png)

1. Confirme que conoce el impacto de cerrar su MSA y, después, haga clic en **Marcar cuenta para cierre**.

    Aparecerá una notificación en la que se indica que la cuenta se cerrará en 30 días. Puede volver a abrir esta cuenta en cualquier momento durante este período de 30 días.

    ![Cuenta cerrada](./media/gdpr-dsr-delete-msa/accountclosed.png)

    Al final de este período de 30 días, comienza el proceso de eliminación de todos los recursos de Power Automate para esta MSA.

## <a name="learn-more"></a>Más información

* Introducción a [Power Automate](getting-started.md).
* Información sobre las [novedades](release-notes.md) de Power Automate.
