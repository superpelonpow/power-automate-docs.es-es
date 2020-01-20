---
title: Ejemplo de recurso compartido de imágenes para compartir fotos | Microsoft Docs
description: Obtenga información sobre cómo crear una tarjeta adaptable de uso compartido de fotografías.
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
ms.openlocfilehash: 0d310eb96a69f66b8f45718554f36ba8b2a51989
ms.sourcegitcommit: e3543e32e4e8e8163bef0565e27b657eabbdc741
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2020
ms.locfileid: "75868742"
---
# <a name="image-share-sample"></a>Ejemplo de recurso compartido de imágenes 

El ejemplo de **formulario de recursos compartidos de imágenes** consiste en una tarjeta adaptable diseñada para compartir fotos publicadas en SharePoint y que puede ser una dependencia para que un proceso se complete (por ejemplo, procesos relacionados con la inspección, el cumplimiento y las auditorías). Se trata de una tarjeta adaptable de solo de visualización.

![Tarjeta adaptable de solo de visualización](media/adaptive-cards/image-share.png)

*Entradas/Salidas y notas*

| Nombre del token dinámico (entradas) | Texto de marcador de posición   | Notas                                              |
|-----------------------------|--------------------|-----------------------------------------------------|
| acphotoTitle                | {acphotoTitle}     | Display text                                        |
| acTimestamp                 | {acTimestamp]      | Fecha y hora de presentación                                   |
| acImageThumbnail            | {acImageThumbnail} | Imagen de presentación <br>Debe reemplazarse por una dirección URL válida.|
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


