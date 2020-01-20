---
title: Ejemplo de informe meteorológico diario de tarjetas adaptables | Microsoft Docs
description: Ejemplo de creación de una tarjeta adaptable para publicar una actualización meteorológica diaria en un canal de Teams
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
ms.date: 01/04/2020
ms.author: deonhe
ms.openlocfilehash: 8f7128104d3cb8aae361b6dd574822f503893e35
ms.sourcegitcommit: e3543e32e4e8e8163bef0565e27b657eabbdc741
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2020
ms.locfileid: "75868190"
---
# <a name="daily-weather-report-sample"></a>Ejemplo de informe meteorológico diario

El ejemplo de **informe meteorológico diario** consiste en una tarjeta adaptable diseñada para usarse con MSN El Tiempo para publicar una actualización meteorológica diaria en un canal de Teams.

![](media/adaptive-cards/weather.png)

*Entradas/Salidas y notas*

| Nombre del token dinámico     | Texto de marcador de posición | Notas                                                                         |
|------------------------|------------------|--------------------------------------------------------------------------------|
| {acCityState}          | Ver plantilla     | Display text <br>  Se puede usar una variable para contener los valores de ciudad, estado o código postal.                                                                   |
| {acDailySummary}       | Ver plantilla     | Display text                                                                   |
| {acCurrentDateTime}    | Ver plantilla     | Display text                                                                   |
| {acUrlConditionsImage} | Ver plantilla     | Display text  <br> Consulte los comentarios de la plantilla Debe reemplazarse por una dirección URL válida.                                                                 |
| {acCurrentTemperature} | Ver plantilla     | Display text                                                                   |
| {actempHi}             | Ver plantilla     | Display text                                                                   |
| {actempLow}            | Ver plantilla     | Display text                                                                   |


``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "{acCity}, {acState}",
            "size": "Large",
            "isSubtle": true
        },
        {
            "type": "TextBlock",
            "text": "{acCurrentDateTime}",
            "spacing": "None"
        },
        {
            "type": "TextBlock",
            "text": "{acDailySummary}",
            "spacing": "None"
        },
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "width": "auto",
                    "items": [
                        {
                            "type": "Image",
                            "url": "{acUrlConditionsImage}",
                            "size": "Large"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "auto",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "{acCurrentTemperature}",
                            "size": "ExtraLarge",
                            "spacing": "None"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "stretch",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "°F",
                            "weight": "Bolder",
                            "spacing": "Small"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "stretch",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Hi {actempHi}",
                            "horizontalAlignment": "Left"
                        },
                        {
                            "type": "TextBlock",
                            "text": "Lo {actempLow}",
                            "horizontalAlignment": "Left",
                            "spacing": "None"
                        }
                    ]
                }
            ]
        }
    ]
}
```
