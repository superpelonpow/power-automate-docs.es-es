---
title: Aprender a crear y administrar flujos en Microsoft Teams | Microsoft Docs
description: Cree y administre flujos para publicar mensajes a petición, mencionar usuarios (utilice @) y canales, publicar tarjetas con opciones de respuesta, etc.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 1fbd0c6b1f6a7cd453f6c1a336f5ce450e236c5e
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296843"
---
# <a name="power-automate-in-teams"></a>Power Automate en Teams


### <a name="prerequisites"></a>Requisitos previos

1. Obtenga acceso a Microsoft Teams.
1. Obtenga acceso a Power Automate.

## <a name="install-the-power-automate-app-in-teams"></a>Instalar la aplicación Power Automate en Teams

Siga estos pasos para instalar la aplicación Power Automate en Microsoft Teams.

1. Inicie sesión en Microsoft Teams.

1. Pulse el icono **Aplicaciones** situado en la parte inferior izquierda de la barra de navegación de Teams.

    ![Selección de aplicaciones](media/flows-teams/apps.png)

1. Seleccione la aplicación **Flow**. Es posible que tenga que buscar **Flow** si no lo ve.

    ![Selección de la aplicación Flow](media/flows-teams/select-flow-app.png)

1. Seleccionar **Instalar**.

    ![Botón de instalación](media/flows-teams/select-install.png)

1. Power Automate ya está instalada.

    ![Instalado](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Creación de un flujo en Teams

1. Inicie sesión en Microsoft Teams.

1. Seleccione el vínculo **Más aplicaciones agregadas** (...) en la barra de navegación y, a continuación, seleccione la aplicación **Flow**.

    ![Icono de aplicaciones agregadas](media/flows-teams/added-apps-icon.png)

1. Si no lo ha hecho antes, puede que tenga que iniciar sesión y conceder permisos.

    ![Inicio de sesión](media/flows-teams/grant-permissions-sign-in.png)


    Observe las pestañas siguientes:

    ![Página de aterrizaje de Flow](media/flows-teams/flow-landing-page.png)

    Nombre|Finalidad
    ----|-----|
    Conversación|Interactúe con el bot de Flow.
    Flows|Cree y administre flujos
    Aprobaciones|Enumera las solicitudes de aprobación enviadas y recibidas.
    Acerca de la aplicación|Muestra la versión y otra información sobre Power Automate.


    Ahora verá todos los flujos que ha creado a partir del diseñador de Power Automate (si hay alguno). 

    También puede crear flujos a partir de una plantilla personalizada o de una plantilla en blanco, de la misma manera que lo hace desde el diseñador de Power Automate. 

## <a name="manage-approvals"></a>Administrar aprobaciones

Puede gestionar [aprobaciones](modern-approvals.md) en Microsoft Teams, tal como lo haría en Power Automate. Siga estos pasos para administrar las aprobaciones:

1. Inicie sesión en Microsoft Teams.
1. Seleccione la pestaña **Aprobaciones**.

    ![Pestaña de aprobaciones](media/flows-teams/approvals-tab.png)

    Observará las siguientes subpestañas:

    Ficha|Finalidad
    ----|-----|
    Recibida|Muestra las solicitudes de aprobación que ha recibido y que están pendientes de acción por su parte.
    Enviados|Muestra las solicitudes de aprobación que ha enviado y que están pendientes de acción por otros.
    Historial|Enumera las solicitudes de aprobación enviadas y recibidas.
    Creación de un flujo de aprobación|Cree flujos de aprobación.

1. Seleccione las pestañas **Recibidas**, **Enviadas**o **Historial** para obtener más información.

    ![Pestaña de aprobaciones](media/flows-teams/approvals-tab-2.png)

1. Seleccione **Crear flujo de aprobación** para crear un flujo de aprobación.

    ![Pestaña de aprobaciones](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>Uso de un bot con flujos

### <a name="list-and-launch-flows-with-the-bot"></a>Enumeración e inicio de flujos con el bot

> [!TIP]
> El bot muestra y ejecuta los flujos desencadenados por una programación o desencadenados manualmente sin intervención del usuario.

1. Inicie sesión en Microsoft Teams.
1. Seleccione el vínculo **Más aplicaciones agregadas** (...) en la barra de navegación y, a continuación, seleccione la aplicación **Flow**.

    ![Icono de aplicaciones agregadas](media/flows-teams/added-apps-icon.png)
    
1. Seleccione la pestaña **Conversación**.

    ![Pestaña de conversación](media/flows-teams/conversations-tab.png)

En la pestaña **Conversación**, puede enviar comandos al bot, que responde realizando las acciones que le pide que ejecute. Por ejemplo, para mostrar los flujos y ejecutar el flujo con el índice 1, ejecute los siguientes comandos:

- ```List flows```: el bot muestra una lista de los flujos, precedidos por un número de índice.
- ```Run flow 1```: ejecuta el flujo número 1. Aquí, *1* es el número de índice del flujo que desea ejecutar.

   ![Comandos de bot](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>Obtención de la descripción para los flujos

Para obtener la descripción del flujo con el índice 1 de la lista de flujos, ejecute ```describe flow 1```. La respuesta de bot será similar a esta imagen:

   ![Descripción de flujos](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>Obtención de la lista de comandos para el bot

Para obtener la lista de comandos que controla el bot, pídaselo con este comando: ```learn more``` 

La respuesta de bot será similar a esta imagen:

![Descripción de flujos](media/flows-teams/bot-learn-more.png) 
