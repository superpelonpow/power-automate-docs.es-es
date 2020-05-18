---
title: Ejemplo de tarjeta de actualización de metadatos de tarjetas adaptables | Microsoft Docs
description: Envíe notificaciones a los miembros o canales de Teams y actualícelos con metadatos relacionados con un registro, un archivo o un tema.
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
ms.openlocfilehash: 902510ac5c2dd61fbcaae7c1dad771588e431873
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297657"
---
# <a name="metadata-update-card-sample"></a>Ejemplo de tarjeta de actualización de metadatos

El ejemplo de **actualización de metadatos** consiste en una tarjeta adaptable diseñada para permitir que los marcadores de Flow notifiquen o actualicen miembros o canales de Teams con metadatos relacionados con un registro, un archivo o un tema. Se trata de una tarjeta adaptable de solo de visualización. Aunque se pueden agregar campos de entrada si se usa una de las acciones *en espera de respuesta* para crearla.

Esta tarjeta consta de tres secciones:

1. Área del encabezado del tema con encabezado, subencabezado y descripción.
1. Área de la lista de hechos para los metadatos de registro pertinentes.
1.  Conjunto de columnas que admite una matriz de tablas de datos

![Ejemplo de metadatos](media/adaptive-cards/metadata-sample.png) 


*Entradas/Salidas y notas*

| Nombre del token dinámico (entradas) | Texto de marcador de posición    | Notas                                     |
|-----------------------------|---------------------|--------------------------------------------|
| acHeader                    | {Header}            | Texto para mostrar                               |
| acSubHeader                 | {SubHeader}         | Texto para mostrar                               |
| acDescription               | Texto latino          | Texto para mostrar                               |
| acFact1                     | {acFact1}           | Texto para mostrar                               |
| acFact2                     | {acFact2}           | Texto para mostrar                               |
| acFact3                     | {acFact3}           | Texto para mostrar                               |
| acColumnSetHeader           | Encabezados del 1 al 3 | Texto para mostrar <br>  Texto para mostrar del encabezado del conjunto de columnas                               |
| acColumnSet                 | Columnas de la 1 a la 3 | Se reemplazan por valores de matriz o de columna.       |


``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Metadata Update Card",
            "weight": "bolder",
            "size": "large",
            "id": "acTitle"
        },
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "width": "auto",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Sub Header Tag Line",
                            "weight": "Bolder",
                            "wrap": true,
                            "id": "acSubHeader"
                        }
                    ]
                }
            ]
        },
        {
            "type": "TextBlock",
            "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. In condimentum leo lorem, at facilisis augue hendrerit eget. Praesent ut malesuada ipsum. Vivamus semper faucibus felis quis sagittis. Nunc pellentesque metus at nunc gravida, vitae volutpat sapien vehicula. Nulla lorem nibh, porttitor vel semper ut, ornare nec erat.",
            "wrap": true,
            "id": "acDescriptionArea"
        },
        {
            "type": "FactSet",
            "facts": [
                {
                    "title": "Fact 1:",
                    "value": "{acFact1}"
                },
                {
                    "title": "Fact 2:",
                    "value": "{acFact2}"
                },
                {
                    "title": "Fact 3:",
                    "value": "{acFact3}"
                }
            ],
            "id": "acFactSet"
        },
        {
            "type": "Container",
            "spacing": "Large",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "weight": "Bolder",
                                    "text": "HEADER 1"
                                }
                            ],
                            "width": "stretch"
                        },
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "weight": "Bolder",
                                    "text": "HEADER 2"
                                }
                            ],
                            "width": "stretch"
                        },
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "weight": "Bolder",
                                    "text": "HEADER 3"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Column 1",
                            "wrap": true,
                            "id": "acCol1"
                        }
                    ],
                    "width": "stretch"
                },
                {
                    "type": "Column",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Column 2",
                            "wrap": true,
                            "id": "acCol2"
                        }
                    ],
                    "width": "stretch"
                },
                {
                    "type": "Column",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Column 3",
                            "wrap": true,
                            "id": "acCol4"
                        }
                    ],
                    "width": "stretch"
                }
            ],
            "$data": "acDataContext"
        }
    ],
    "bleed": true

}
```
