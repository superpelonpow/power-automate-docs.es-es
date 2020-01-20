---
title: Ejemplo de colección de clientes potenciales | Microsoft Docs
description: Cree una tarjeta adaptable para la recopilación de clientes potenciales a partir de personas interesadas en un conjunto de productos.
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
ms.openlocfilehash: 6ec875a8a3bf682b7a3d9b44a0cc1d3624bf7a70
ms.sourcegitcommit: 0761c15339ba3de6036f7fe5251aa8ad9173ee8b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902224"
---
# <a name="lead-collection-sample"></a>Ejemplo de colección de clientes potenciales

El ejemplo de **colección de clientes potenciales** consiste en una tarjeta adaptable diseñada para recopilar clientes potenciales de cualquier persona que pueda entrar en contacto con personas interesadas en un conjunto de productos. No dude en cambiar las opciones de los productos, recordar que cada opción puede tener texto para mostrar, así como un valor interno que se generará después de que alguien envíe la tarjeta (también puede ser el mismo que se muestra en el bloque de código de ejemplo).

![](media/adaptive-cards/lead-notification.png)

*Entradas/Salidas y notas:*

| Nombre del token dinámico    | Texto de marcador de posición       | Notas                                                                                       |
|-----------------------|------------------------|--------------------------------------|
| Título                 |                        | Display text                                                                                  |
| acInstructions        |                        | Display text                                                                                  |
| acLeadFName           | {firstName}            | **Salida** de respuesta                                                                           |
| acLeadLName           | {lastName}             | **Salida** de respuesta                                                                           |
| acLeadEmail           | {emailAddress}         | **Salida** de respuesta                                                                           |
| acLeadPrimaryPhone    | {primaryPhone10digits} | **Salida** de respuesta                                                                           |
| acLeadProductInterest | {productInterests}     | **Salida** de respuesta  <br>Como valores de selección múltiple, donde cada selección estará separada por una coma.                                                                         |

``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "width": 2,
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Lead Notification",
                            "weight": "Bolder",
                            "id": "Title",
                            "size": "ExtraLarge"
                        },
                        {
                            "type": "TextBlock",
                            "text": "Please fill out a single form for each individual expressing interest in our products. ",
                            "isSubtle": true,
                            "wrap": true,
                            "id": "acInstructions",
                            "size": "Large"
                        }
                    ]
                }
            ]
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "TextBlock",
                    "text": "Potential Customer FIRST NAME",
                    "wrap": true,
                    "size": "Medium"
                }
            ]
        },
        {
            "type": "Input.Text",
            "id": "acLeadFName",
            "placeholder": "{firstName}"
        },
        {
            "type": "TextBlock",
            "text": "Potential Customer LAST NAME",
            "wrap": true
        },
        {
            "type": "Input.Text",
            "id": "acLeadLName",
            "placeholder": "{lastName}"
        },
        {
            "type": "TextBlock",
            "text": "Corporate email",
            "wrap": true
        },
        {
            "type": "Input.Text",
            "id": "acLeadEmail",
            "placeholder": "{emailAddress}",
            "style": "Email"
        },
        {
            "type": "TextBlock",
            "text": "Business Phone Number"
        },
        {
            "type": "Input.Text",
            "id": "acLeadPrimaryPhone",
            "placeholder": "{primaryPhone10digits}",
            "style": "Tel"
        },
        {
            "type": "RichTextBlock",
            "inlines": [
                {
                    "type": "TextRun",
                    "text": "{productInterests}"
                }
            ]
        },
        {
            "type": "Input.ChoiceSet",
            "placeholder": "Placeholder text",
            "choices": [
                {
                    "title": "Office 365",
                    "value": "Office 365"
                },
                {
                    "title": "Dynamics 365",
                    "value": "Dynamics 365"
                },
                {
                    "title": "Azure Services",
                    "value": "Azure Services"
                },
                {
                    "title": "Power Platform",
                    "value": "Power Platform"
                }
            ],
            "style": "expanded",
            "id": "acLeadProductInterest",
            "isMultiSelect": true
        }
    ],
    "actions": [
        {
            "type": "Action.Submit",
            "title": "Submit"
        }
    ]
}
```


