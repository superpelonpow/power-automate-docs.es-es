---
title: Ejemplo compartir imagen para compartir fotos | Microsoft Docs
description: Obtenga información sobre cómo crear una tarjeta adaptable para compartir fotos.
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
ms.openlocfilehash: c804a65eee3b217dd2b6d66d54c7e39d87ef0eae
ms.sourcegitcommit: 3f582a1e462124d44f63cef7d450fc94be148f3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "3372793"
---
# <a name="image-share-sample"></a>Ejemplo de compartir imagen 

El ejemplo de formulario de **recursos compartidos de imágenes** consiste en una tarjeta adaptable diseñada para compartir fotos publicadas en SharePoint y que puede ser una dependencia para que un proceso se complete (por ejemplo, procesos relacionados con la inspección, el cumplimiento y las auditorías). Se trata de una tarjeta adaptable de solo visualización.

![Tarjeta adaptable de solo visualización](media/adaptive-cards/image-share.png)

*Entradas/Salidas y notas*

| Nombre del token dinámico (entradas) | Texto de marcador de posición   | Notas                                              |
|-----------------------------|--------------------|-----------------------------------------------------|
| acphotoTitle                | {acphotoTitle}     | Texto para mostrar                                        |
| acTimestamp                 | {acTimestamp}      | Fecha y hora de presentación                                   |
| acImageThumbnail            | {acImageThumbnail} | Imagen de presentación <br>Debe reemplazarse por una dirección URL válida|
| acAltText                   | {acAltText}        | Texto alternativo de accesibilidad                      |

``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "{acphotoTitle}",
            "id": "Title",
            "size": "Large"
        },
        {
            "type": "TextBlock",
            "text": "{acTimestamp}",
            "size": "Medium",
            "weight": "Lighter"
        },
        {
            "type": "Image",
            "altText": "{acAltText}",
            "url": "{acImageThumbnail}"
        }
    ],
    "spacing": "None"
}
```


