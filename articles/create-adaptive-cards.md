---
title: Crear flujos que publiquen tarjetas adaptables en Microsoft Teams | Microsoft Docs
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
ms.date: 01/04/2020
ms.author: deonhe
ms.openlocfilehash: 186526427d8de7ee05dd6860e302faae5ac1d97f
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297437"
---
# <a name="create-your-first-adaptive-card"></a>Creación de su primera tarjeta adaptable

Las tarjetas adaptables incluidas en Power Automate pueden compartir bloques de información o recopilar datos mediante un formulario para un origen de datos determinado. 

En cualquier caso, tendrá que esbozar los conjuntos de datos que va a compartir y los datos que el formulario tendrá que recopilar. 

>[!TIP]
>Use bloques de datos sencillos en lugar de matrices de tabla complejas.

## <a name="prerequisites"></a>Requisitos previos

<!-- Is it still called Flow App? -->
- Microsoft Teams con la aplicación Flow instalada.

## <a name="add-an-action"></a>Agrega una acción

En este procedimiento, agregará una acción que usará los datos de las acciones anteriores en el flujo para publicar información en un canal de Microsoft Teams.

1. Iniciar sesión en Power Automate.
1. Seleccione **Mis flujos** en la barra de navegación superior.
1. Seleccione **Nueva** > **Instant from blank** (Instantánea desde cero).
1. Asígnele un nombre al flujo.
1. Seleccione **Desencadenar un flujo manualmente** como desencadenador.
1. Seleccione **Crear**.

    <!-- | [./media/image5.png](./media/image5.png) | [./media/image6.png](./media/image6.png) | -->

1. Seleccione **Nuevo paso**.
1. Busque **Microsoft Teams** y seleccione **Publique una tarjeta adaptable en un canal de Teams y espere respuesta** como acción.
1. Seleccione **Teams** y el **canal** al que quiere enviar la tarjeta.
1. Pegue este archivo JSON en el cuadro **Mensaje**.

    ``` JSON
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

1. Realice los reemplazos siguientes en el archivo JSON.

    >[!IMPORTANT]
    >No quite las comillas al realizar los reemplazos. Puede revisar las opciones de automóvil para ajustarlas a sus necesidades:

    Texto que se va a cambiar | Nuevo texto
    ------|------
    Texto de subtítulo del encabezado|Sondeo de Power Automate
    Encabezado de sondeo| Modelo de automóvil preferido
    | Pregunta de sondeo   | Vote por el modelo de automóvil preferido entre las opciones que se muestran aquí. 
    Reemplace el texto latino por una razón, o contexto empresarial, relacionado con el motivo por el que realiza la encuesta.      |  Estamos sondeando a nuestros empleados para determinar si debemos proporcionar plazas de aparcamiento personalizadas que se ajusten al tamaño de los coches más populares. 
    | Opción 1 (reemplazar en ambos lugares)  | Tesla   |
    | Opción 2 (reemplazar en ambos lugares) | Lexus |
    | Opción 3 (reemplazar en ambos lugares) | Honda |

1. Seleccione **Nuevo paso** y luego busque y seleccione una de las acciones de **enviar un correo electrónico** a las que tenga acceso. 
1. Indique el destinatario de correo electrónico como la persona que seleccionó el botón instantáneo (use la etiqueta de **correo electrónico** del contenido dinámico del **desencadenador**).
1. Configure el **cuerpo** del correo electrónico de la manera siguiente: Reemplace las palabras entre llaves "{}" por tokens dinámicos:  
    **Su respuesta al sondeo fue {acPollChoices}** (acPollChoices consiste en contenido dinámico de la espera de una acción de respuesta).  **Lo envió {Nombre de usuario}** (el nombre de usuario es contenido dinámico del desencadenador)

## <a name="test-your-adaptive-card"></a>Prueba de la tarjeta adaptable

Para probar su trabajo, ejecute el flujo que creó anteriormente y confirme lo siguiente:

- La ejecución de flujo no tiene errores y espera la respuesta, y muestra el indicador de espera para la acción de tarjeta adaptable en la pantalla de ejecución. 

- El canal de Teams tiene la nueva tarjeta adaptable publicada.

- Cuando responda a la tarjeta seleccionando un modelo de automóvil y seleccionando después el botón **Enviar** de la sección inferior de la tarjeta adaptable:

    - No deben producirse errores en la tarjeta adaptable.

    - La ejecución de flujo se completa correctamente.

- El reemplazo de la tarjeta es pertinente después del envío si se ha configurado el área **Actualizar mensaje** en la parte inferior de las acciones **en espera de respuesta** (que se muestran a continuación con la tarjeta de reemplazo correspondiente). De lo contrario, todos los envíos simplemente restablecerán el formulario.

    ![Tarjeta de reemplazo](./media/adaptive-cards/update-message-2.png)

- La notificación por correo electrónico contiene el cuerpo que muestra quién envió la respuesta y qué automóvil se seleccionó.

Enhorabuena. acaba de crear su primera tarjeta interactiva adaptable.

![Primera tarjeta finalizada](media/adaptive-cards/finished-first-card.png) 


## <a name="troubleshooting-tips-for-adaptive-cards"></a>Sugerencias para la solución de problemas de tarjetas adaptables

Los problemas más habituales que encontrará al crear tarjetas adaptables son:

-   Los errores de ejecución de flujo suelen deberse a uno de los siguientes factores:

    -  La aplicación Flow no está instalada en Microsoft Teams: [Instale la aplicación Flow en Teams](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams). 
    
    En este caso, el error puede ser similar a esta captura de pantalla:  

    ![Mensaje de error](media/adaptive-cards/error-message.png)

    -  JSON con formato incorrecto: no suele ser tan complejo como cabría esperar. Normalmente, se trata de situaciones en las que:

        - Hay comillas tipográficas, o faltan comillas, alrededor de los valores dentro del JSON. Compruebe siempre el archivo JSON para asegurarse de que todos los valores de texto estén entre comillas dobles y que los números estén entre comillas. Todas las comillas deben ser rectas y no tipográficas.

        - Puede validar el formato del archivo JSON pegando el archivo JSON en el [editor de carga de tarjeta](https://adaptivecards.io/designer/).

    - Direcciones URL de imagen que faltan: todos los valores de imagen dentro de las tarjetas adaptables deben hacer referencia a una dirección URL válida. El contenido completo de la imagen no se admite directamente en una tarjeta adaptable. Pruebe los vínculos de imagen pegando la dirección URL en el explorador para ver si se muestra una imagen.

- Puede que las tarjetas adaptables no se parezcan a lo que se espera durante la aplicación de estilos y las restricciones de esquema:

    - Compruebe que los valores de marcadores de posición, estilos de texto y cualquier lenguaje de marcado se alinean con los requisitos del esquema de tarjeta adaptada (revise los **procedimientos recomendados para el esquema de tarjeta adaptable** [aquí](https://adaptivecards.io/explorer/)).

    - Aproveche el validador de tarjeta adaptable de **Visual Studio Code**. Para instalarlo desde la aplicación de Visual Studio Code, abra el Marketplace de extensiones y busque **Visor de tarjetas adaptables**.

      ![Extensión de Visual Studio Code](media/adaptive-cards/visual-studio-code-extension.png)
  
Captura de pantalla truncada de la extensión del visor de tarjetas adaptables instalada en Visual Studio Code (acceso directo: Ctrl+V+A una vez esté habilitado).

- Los errores siguientes al envío de tarjeta adaptable suelen deberse a:

    - Uso de una acción que no incluye "en espera de respuesta" en el nombre  
        
        ![Intentar de nuevo](media/adaptive-cards/try-again.png)

    - Se intenta enviar la tarjeta más de una vez. Cada tarjeta adaptable solo se puede enviar una vez, tras lo cual se omitirán todos los envíos posteriores.
