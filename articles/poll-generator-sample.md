---
title: Ejemplo de generador de sondeo | Microsoft Docs
description: Formulario de entrada de tarjeta adaptable diseñado para enviar sondeos a Microsoft Teams.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/01/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b19a5b58db4680786ade089731846f0f8000d164
ms.sourcegitcommit: e3543e32e4e8e8163bef0565e27b657eabbdc741
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2020
ms.locfileid: "75868236"
---
# <a name="create-a-poll-sample"></a>Ejemplo de creación de un sondeo

El ejemplo de **creación de un sondeo** consiste en un formulario de entrada de tarjeta adaptable diseñado para enviar sondeos a Microsoft Teams. Reemplace el texto para mostrar de esta tarjeta para personalizar el sondeo. Esta tarjeta adaptable le permite tomar diferentes rutas de decisiones según las respuestas proporcionadas en los valores de sondeo, o recuentos de votos, de los consumidores de la tarjeta.

![Ejemplo de sondeo](media/adaptive-cards/poll.png)

*Entradas/Salidas y notas*

| Nombre del token dinámico | Texto de marcador de posición | Notas:                                            |
|--------------------|------------------|---------------------------------------------------|
| Título              |                  | Display text                                      |
| acHeaderTagLine    |                  | Display text                                      |
| acHeader           |                  | Display text                                      |
| acPollQuestion     |                  | Display text                                      |
| acPollChoices      |                  | **Salida** de respuesta  <br> Selección simple como botones de radio|

``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Poll Request",
            "id": "Title",
            "spacing": "Medium",
            "horizontalAlignment": "Center",
            "size": "ExtraLarge",
            "weight": "Bolder",
            "color": "Accent"
        },
        {
            "type": "TextBlock",
            "text": "Header Tagline Text",
            "id": "acHeaderTagLine",
            "separator": true
        },
        {
            "type": "TextBlock",
            "text": "Poll Header",
            "weight": "Bolder",
            "size": "ExtraLarge",
            "spacing": "None",
            "id": "acHeader"
        },
        {
            "type": "TextBlock",
            "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer vestibulum lorem eget neque sollicitudin, quis malesuada felis ultrices. ",
            "id": "acInstructions",
            "wrap": true
        },
        {
            "type": "TextBlock",
            "text": "Poll Question",
            "id": "acPollQuestion"
        },
        {
            "type": "Input.ChoiceSet",
            "placeholder": "Select from these choices",
            "choices": [
                {
                    "title": "Choice 1",
                    "value": "Choice 1"
                },
                {
                    "title": "Choice 2",
                    "value": "Choice 2"
                },
                {
                    "title": "Choice 3",
                    "value": "Choice 3"
                }
            ],
            "id": "acPollChoices",
            "style": "expanded"
        }
    ],
    "actions": [
        {
            "type": "Action.Submit",
            "title": "Submit",
            "id": "btnSubmit"
        }
    ]
}
```


