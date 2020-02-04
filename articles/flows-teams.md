---
title: Creación y administración de flujos en Microsoft Teams | Microsoft Docs
description: Cree y administre flujos para publicar mensajes a petición, @mention usuarios y canales, publicar tarjetas con opciones de respuesta, etc.
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
ms.openlocfilehash: a2a9b5d5a6ed8305ed3e7c29717ef19978bae0a7
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74367073"
---
# <a name="power-automate-in-teams"></a>Power Automate en Teams
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

### <a name="prerequisites"></a>Requisitos previos

1. Access a Microsoft Teams.
1. Acceso a Power Automate.

## <a name="install-the-power-automate-app-in-teams"></a>Instalación de la aplicación Power Automate en Teams

Siga estos pasos para instalar la aplicación Power Automate en Microsoft Teams.

1. Inicie sesión en Microsoft Teams.

1. Pulse el icono **Aplicaciones** situado en la parte inferior izquierda de la barra de navegación de Teams.

    ![Selección de aplicaciones](media/flows-teams/apps.png)

1. Seleccione la aplicación **Flow**. Es posible que tenga que buscar **Flow** si no lo ve.

    ![Selección de la aplicación Flow](media/flows-teams/select-flow-app.png)

1. Haga clic en **Instalar**.

    ![Botón de instalación](media/flows-teams/select-install.png)

1. Power Automate ya está instalado.

    ![Instalado](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Creación de un flujo en Teams

1. Inicie sesión en Microsoft Teams.

1. Seleccione el vínculo **Más aplicaciones agregadas** (...) en la barra de navegación y, a continuación, seleccione la aplicación **Flow**.

    ![Icono de aplicaciones agregadas](media/flows-teams/added-apps-icon.png)

1. Si no lo ha hecho antes, puede que tenga que iniciar sesión y conceder permisos.

    ![Iniciar sesión](media/flows-teams/grant-permissions-sign-in.png)


    Observe las pestañas siguientes:

    ![Página de aterrizaje de Flow](media/flows-teams/flow-landing-page.png)

    Nombre|Propósito
    ----|-----|
    Conversación|Interactúe con el bot de Flow.
    Flujos|Cree y administre flujos
    Aprobaciones|Enumera las solicitudes de aprobación enviadas y recibidas.
    Acerca de|Muestra la versión y otra información sobre Power Automate.


    Ahora verá todos los flujos que ha creado a partir del diseñador de Power Automate (si hay alguno). 

    También puede crear flujos a partir de una plantilla personalizada o de una plantilla en blanco, de la misma manera que lo hace desde el diseñador de Power Automate. 

## <a name="manage-approvals"></a>Administrar aprobaciones

Puede administrar las [aprobaciones](modern-approvals.md) en Microsoft Teams, de la misma forma que lo haría en Power Automate. Siga estos pasos para administrar las aprobaciones:

1. Inicie sesión en Microsoft Teams.
1. Seleccione la pestaña **Aprobaciones**.

    ![Pestaña de aprobaciones](media/flows-teams/approvals-tab.png)

    Observará las siguientes subpestañas:

    Pestaña|Propósito
    ----|-----|
    Recibidas|Muestra las solicitudes de aprobación que ha recibido y que están pendientes de acción por su parte.
    Enviadas|Muestra las solicitudes de aprobación que ha enviado y que están pendientes de acción por otros.
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

1. Inicie sesión en Microsoft Teams.
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
