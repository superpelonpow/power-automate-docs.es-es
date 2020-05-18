---
title: Solicitudes de detección del titular de los datos de acuerdo con el RGPD en Power Automate para cuentas Microsoft (MSA) | Microsoft Docs
description: Obtenga información sobre cómo usar Power Automate para responder a solicitudes de detección del titular de los datos de acuerdo con el RGPD para cuentas de Microsoft.
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
ms.date: 5/16/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 5e1dc452bdbe7aa65700d159cf9365812dc50bfb
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298009"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>Respuesta a solicitudes de detección del interesado de acuerdo con el RGPD 


El primer paso para responder a una solicitud DSR consiste en encontrar los datos personales objeto de la solicitud.
Este es un resumen de los recursos de Power Automate que contienen datos personales de un usuario que se autentica con su cuenta de Microsoft (MSA).

|Recurso|Finalidad|
|-----|-----|
|Historial de ejecución|Proporciona el historial de cada ejecución del flujo de los últimos 28 días. Estos datos incluyen la hora de inicio, la hora de finalización, el estado y toda la información de entrada y salida de cada ejecución del flujo. Obtenga más información sobre el [historial de ejecución de flujo](https://flow.microsoft.com/blog/download-history-recurrence/).|
|Fuente de actividades| Proporciona un resumen de las actividades de cada flujo, como el estado de ejecución, los errores y las notificaciones.|
|Flows|La lógica de flujo de trabajo para un [flujo](https://docs.microsoft.com/flow/get-started-logic-flow).|
|Conexiones|Usadas por los conectores, permiten la conectividad a las API, los sistemas, las bases de datos y mucho más. Obtenga más información sobre las [conexiones](add-manage-connections.md).|

