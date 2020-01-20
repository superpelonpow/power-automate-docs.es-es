---
title: Ejemplo de formulario de acrónimos de tarjetas adaptables | Microsoft Docs
description: Cree una tarjeta adaptable que recopile acrónimos y los almacene en Common Data Service.
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
ms.openlocfilehash: b1ecc0240dba1866ea3468647d06637397d73170
ms.sourcegitcommit: e3543e32e4e8e8163bef0565e27b657eabbdc741
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2020
ms.locfileid: "75868305"
---
# <a name="acronyms-form-sample"></a>Ejemplo de formulario de acrónimos

El ejemplo de **formulario de acrónimos** consiste en una tarjeta adaptable diseñada para recopilar acrónimos y almacenarlos en Common Data Service. Estos acrónimos se pueden consultar desde cualquier lugar gracias a esta recopilación continua de datos.

![Registrador de acrónimos](media/adaptive-cards/acronym-logger.png)

*Entradas/Salidas y notas*

| Nombre del token dinámico | Texto de marcador de posición                        | Notas:              |
|--------------------|-----------------------------------------|---------------------|
| {acAcronym}        | Escriba la abreviatura del acrónimo.  | **Salida** de respuesta |
| {acDefinition}     | Escriba una definición del acrónimo anterior. | **Salida** de respuesta |

``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Acronym Logger",
            "id": "Title",
            "spacing": "Medium",
            "horizontalAlignment": "Center",
            "size": "ExtraLarge",
            "weight": "Bolder",
            "color": "Accent"
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "TextBlock",
                    "text": "Acronym",
                    "wrap": true,
                    "spacing": "Medium"
                },
                {
                    "type": "Input.Text",
                    "id": "acAcronym",
                    "placeholder": "Enter the abbreviation for the acronym"
                },
                {
                    "type": "TextBlock",
                    "text": "Definition",
                    "wrap": true
                },
                {
                    "type": "Input.Text",
                    "placeholder": "Enter a definition of the acronym above",
                    "id": "acDefinition",
                    "isMultiline": true
                }
            ]
        }
    ],
    "actions": [
        {
            "type": "Action.Submit",
            "title": "Submit",            "id": "btnSubmit"
        }
    ]
}

```