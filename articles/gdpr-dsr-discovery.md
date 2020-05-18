---
title: Solicitudes de detección del titular de los datos de acuerdo con el RGPD en Power Automate| Microsoft Docs
description: Obtenga información sobre cómo usar Power Automate para responder a solicitudes de detección del titular de los datos de acuerdo con el RGPD.
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
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 05def202f2a0b0db8a6eebb067406c96221e7d1c
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297173"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-power-automate"></a>Responder a las solicitudes de detección del titular de los datos de acuerdo con el RGPD para Power Automate


El primer paso para responder a un derecho de los titulares de datos es buscar los datos personales a los que se refiere la solicitud. Este primer paso le ayudará a determinar si un derecho de los titulares de datos cumple los requisitos de su organización para tener en cuenta o rechazar una solicitud de este tipo. Por ejemplo, después de encontrar y revisar los datos personales en cuestión, puede determinar que la solicitud no cumple los requisitos de su organización porque al hacerlo puede que afecte negativamente a los derechos y las libertades de terceros.

A continuación se proporciona un resumen de los tipos de recursos de Power Automate que contienen información personal para un usuario específico.

|**Recursos que contienen datos personales**|**Finalidad**|
|-----|-----|
|Registros generados por el sistema|Telemetría que captura el historial y los eventos del sistema.|
|Historial de ejecución|El historial de cada ejecución de flujo de los últimos 28 días. Estos datos incluyen la hora de inicio, la hora de finalización, el estado y toda la información de entrada/salida para el flujo. [Más información](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Fuente de actividades| Proporciona un resumen de las actividades de flujo, como el estado de ejecución, los errores y las notificaciones.|
|Trabajos de usuario|No visibles para el usuario, los trabajos del sistema que se ejecutan en nombre del usuario para que se ejecuten los flujos.|
|Flows|La lógica de flujo de trabajo que existe para un flujo. [Más información](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Permisos de flujo|Los flujos pueden compartirse y volverse a asignar a otros usuarios. Existen listas de permisos para todos los flujos. [Más información](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Detalles del usuario|Detalles, no percibidos por el usuario, que respaldan la ejecución del flujo.|
|Conexiones|La usan los conectores y permite establecer conectividad con las API, los sistemas, las bases de datos, etcétera. [Más información](https://docs.microsoft.com/flow/add-manage-connections)|
|Permisos de conexión|Permisos para una conexión específica. [Más información](https://docs.microsoft.com/flow/add-manage-connections)|
|Conectores personalizados|Conectores personalizados que ha creado y publicado un usuario que permiten la conectividad con sistemas de otros fabricantes o personalizados. [Más información](https://docs.microsoft.com/connectors/custom-connectors/)|
|Permisos del conector personalizado|Listas de permisos para los conectores personalizados. [Más información](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Puerta de enlace|Las puertas de enlace son servicios de datos locales que un usuario puede instalar para transferir datos de forma rápida y segura entre Power Automate y un origen de datos que no se encuentra en la nube. [Más información](https://docs.microsoft.com/flow/gateway-manage)|
|Permisos de puerta de enlace|Las puertas de enlace se pueden compartir entre usuarios de una organización. [Más información](https://go.microsoft.com/fwlink/?linkid=872249)|
