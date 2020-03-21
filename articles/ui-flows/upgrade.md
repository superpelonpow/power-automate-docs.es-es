---
title: Actualización de la aplicación de flujos de interfaz de usuario y de las conexiones a partir de versiones anteriores | Microsoft Docs
description: Actualización de la aplicación de flujos de interfaz de usuario y de las conexiones a partir de versiones anteriores.
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
ms.date: 03/03/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 617f61e1c08f7a4a51bb6916bcadf5e02691d46f
ms.sourcegitcommit: f7d040ae93eabbc60ce922f497ab47977130d877
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79132944"
---
# <a name="upgrade-ui-flows-app-and-connections-from-previous-releases"></a>Actualización de la aplicación de flujos de interfaz de usuario y de las conexiones a partir de versiones anteriores

Hemos modificado varios componentes subyacentes y hemos agregado varias características en la versión de febrero con soporte desatendido. Deberá actualizar la aplicación de flujos de interfaz de usuario local y las conexiones de puerta de enlace para poder usar estas nuevas características, incluidas las características desatendidas.

### <a name="what-does-it-mean-for-my-existing-ui-flows"></a>¿Qué supone esto para mis flujos de interfaz de usuario existentes?

No es necesario realizar ninguna acción hasta que actualice la aplicación de flujos de interfaz de usuario o la conexión a la puerta de enlace. Debe actualizar ambas al mismo tiempo.

### <a name="how-do-i-upgrade"></a>¿Cómo realizar una actualización?

1.  Descargue la [versión más reciente de la aplicación de flujos de interfaz de usuario](https://go.microsoft.com/fwlink/?linkid=2102613&clcid=0x409) e instálela en sus dispositivos.

1.  En cada dispositivo en el que haya instalado la aplicación de flujos de interfaz de usuario:

    1. Inicie sesión en [Power Automate](https://powerautomate.microsoft.com).
    1. Expanda **Datos** en el lado izquierdo de la pantalla.
    1. Seleccione **Conexiones**.
    1. Edite las conexiones de los flujos de interfaz de usuario que tienen como destino el dispositivo.
    1. Escriba sus credenciales para la conexión y guárdela.

    >[!IMPORTANT]
    >Asegúrese de usar las credenciales correctas, tal como se describe en [Configuración de las conexiones de flujos de interfaz de usuario y las credenciales del equipo](setup.md). Usar las credenciales correctas garantiza que la conexión actualiza y usa las rutas de acceso del código para los flujos de interfaz de usuario que están disponibles con carácter general.

 <!-- todo      1. See (Managing UI flows app (Install, update, versions…)) for more
            details. -->

## <a name="next-steps"></a>Pasos siguientes

- Obtenga información sobre cómo [configurar flujos de interfaz de usuario](setup.md). 
- Obtenga más información sobre los [diferentes tipos de flujos](..\getting-started.md#types-of-flows) que puede usar para automatizar los flujos de trabajo.

