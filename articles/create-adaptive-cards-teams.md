---
title: Creación de flujos que publiquen tarjetas adaptables en Microsoft Teams | Microsoft Docs
description: Aprenda a crear flujos que publiquen contenido con formato enriquecido mediante tarjetas adaptables en Microsoft Teams.
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
ms.openlocfilehash: 3813b32ea50c9f91ff3ac3b620796983926d365e
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74362956"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Uso de tarjetas adaptables en Microsoft Teams
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Puede crear un flujo que publique [tarjetas adaptables](https://adaptivecards.io) en un canal de Microsoft Teams. Con las tarjetas adaptables, puede usar formato enriquecido para que sus publicaciones sean más claras, interactivas y atractivas. Las tarjetas adaptables pueden contener componentes como imágenes, gráficos, texto con formato enriquecido, etc.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Creación de un flujo que publique tarjetas adaptables en un equipo

Siga estos pasos para crear un flujo que publique una tarjeta adaptable en el canal general del equipo de estrategia y planeamiento. El flujo que creamos usa la acción **Muestre su propia tarjeta adaptable como el bot de Flow en un canal (versión preliminar)** para publicar el contenido de la tarjeta adaptable en el canal semanal del equipo.

1. Inicie sesión en Microsoft Teams.
1. Seleccione el icono de **Teams** en la barra de navegación izquierda y, luego, seleccione el equipo **Strategy and Planning** (Estrategia y planeamiento).

    ![Selección de equipos](media/create-adaptive-cards-teams/select-teams-team.png)

1. Seleccione la pestaña **Flujo** en la parte superior de la pantalla.
1. Seleccione el icono **+** (Crear desde cero).
1. Busque **periodicidad** y, después, seleccione el desencadenador **Periodicidad**.

    ![Tarjeta de periodicidad](media/create-adaptive-cards-teams/select-recurrence.png)

1. Establezca la programación como se indica a continuación para que se repita cada semana, a una hora y en una zona horaria de su elección:
    
    ![Tarjeta de periodicidad](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. Seleccione **Nuevo paso**.
1. Busque **adaptable**, seleccione **Microsoft Teams** y, luego, elija la acción **Muestre su propia tarjeta adaptable como el bot de Flow en un canal (versión preliminar)** .

   ![Tarjeta adaptable](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. Proporcione la información para **Equipo**, **Canal** y **Mensaje** en la tarjeta **Muestre su propia tarjeta adaptable como el bot de Flow en un canal (versión preliminar)** para indicar el equipo y el canal en los que se publicará el **mensaje** de la tarjeta adaptable.

   ![Tarjeta adaptable](media/create-adaptive-cards-teams/adaptive-card-message.png)

   Puede usar este contenido JSON de ejemplo en el **mensaje**:

    ````
        {
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "speak": "Our team meeting is starting soon. Do you want to snooze  or do you want to send a late notification to the attendees?",
    "body": [
        {
        "type": "TextBlock",
        "text": "Strategy and Planning Weekly Team meeting",
        "size": "large",
        "weight": "bolder"
        },
        {
        "type": "TextBlock",
        "text": "Conf Room 112/3377 (10)",
        "isSubtle": true
        },
        {
        "type": "TextBlock",
        "text": "12:30 PM - 1:30 PM",
        "isSubtle": true,
        "spacing": "none"
        },
        {
        "type": "TextBlock",
        "text": "Snooze for"
        },
        {
        "type": "Input.ChoiceSet",
        "id": "snooze",
        "style": "compact",
        "value": "5",
        "choices": [
            {
            "title": "5 minutes",
            "value": "5",
            "isSelected": true
            },
            {
            "title": "15 minutes",
            "value": "15"
            },
            {
            "title": "30 minutes",
            "value": "30"
            }
        ]
        }
    ],
    "actions": [
        {
        "type": "Action.Submit",
        "title": "Snooze",
        "data": {
            "x": "snooze"
        }
        },
        {
        "type": "Action.Submit",
        "title": "I'll be late",
        "data": {
            "x": "late"
        }
        }
    ]
    }
    ````


1. Asigne un nombre al flujo y guárdelo.


## <a name="run-the-flow"></a>Ejecución del flujo

Observe que, una vez transcurrido el tiempo de periodicidad, el flujo envía el contenido de la tarjeta adaptable al canal del equipo que ha definido.

![Ejecución del flujo](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>Más información

- Comience con los [ejemplos de tarjeta adaptable](https://adaptivecards.io/samples/).
- Cree [contenido de tarjeta adaptable](https://adaptivecards.io) de la manera más sencilla.



