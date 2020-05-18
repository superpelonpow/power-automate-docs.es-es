---
title: Ejemplo de comentarios de candidatos | Microsoft Docs
description: Use este ejemplo para crear una tarjeta adaptable con el fin de recopilar comentarios de los candidatos para un puesto de trabajo.
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
ms.openlocfilehash: 0d0157c4e0d392dd8493e5aeca4e97531c95213d
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297283"
---
# <a name="candidate-feedback-sample"></a>Ejemplo de comentarios de candidatos

El **formulario de ejemplo de comentarios de candidatos** es un formulario de entrada de una tarjeta adaptable que está diseñado para recopilar comentarios durante un circuito de entrevistas. Se recomienda usar esto con un botón de flujo instantáneo compartido para permitir que cualquier persona del equipo proporcione comentarios sobre los candidatos durante un circuito de entrevistas. Amplíe esto registrando las respuestas en una base de datos u otros orígenes de datos deseados para admitir estas oportunidades adicionales:

-   Facilite la revisión de las sugerencias de seguimiento antes de la siguiente sesión con el candidato.
-   Facilite la revisión de los datos agregados después de que se registren todas las respuestas.
-   Notifique al representante de recursos humanos el recuento de votos de contratación o no contratación al final del proceso.

     ![Formulario de comentarios de candidatos](media/adaptive-cards/candidate-form.png)

*Entradas/Salidas y notas*

| Nombre del token dinámico | Texto de marcador de posición | Notas:              |
|--------------------|------------------|---------------------|
| {acFullName}       | {acFullName}     | Texto para mostrar        |
| {acComments}       | {acComments}     | Texto para mostrar        |
| {acDecision}       |                  | **Salida** de respuesta |
| {acFollowUp}       |                  | **Salida** de respuesta |

``` json
{
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.0",
  "body": [
    {
      "type": "TextBlock",
      "size": "Medium",
      "weight": "Bolder",      "id": "Title",
      "text": "CANDIDATE FEEDBACK FORM",
      "horizontalAlignment": "Left"
    },
    {
      "type": "Input.Text",
      "placeholder": "{acFullName}",
      "style": "text",
      "isMultiline": false,
      "maxLength": 75,
      "id": "acFullName"
    },
    {
      "type": "Input.Text",
      "placeholder": "{acComments}",
      "style": "text",
      "isMultiline": true,
      "maxLength": 200,
      "id": "acComments"
    },
    {
      "type": "TextBlock",
      "size": "Medium",
      "weight": "Bolder",
      "text": "Decision",
      "horizontalAlignment": "Left",
      "separator": true
    },
    {
      "type": "Input.ChoiceSet",
      "id": "acDecision",
      "value": "1",
      "choices": [
        {
          "title": "Hire",
          "value": "Hire"
        },
        {
          "title": "No Hire",
          "value": "No Hire"
        }
      ],
      "style": "expanded"
    },
    {
      "type": "TextBlock",
      "text": "Suggest follow-up discussion regarding:",
      "weight": "Bolder"
    },
    {
      "type": "Input.ChoiceSet",
      "id": "acFollowUp",
      "isMultiSelect": true,
      "value": "",
      "choices": [
        {
          "title": "Past experience in the topic area",
          "value": "Experience"
        },
        {
          "title": "Inclusive behaviors and work ethics",
          "value": "Inclusivity"
        },
        {
          "title": "Ability to work without supervision",
          "value": "Independent"
        }
      ]
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


