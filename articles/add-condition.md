---
title: Adición de una condición a un flujo | Microsoft Docs
description: Especifique que un flujo realice una o varias tareas solo si el valor de una condición es true.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/08/2020
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c717bfcb10fdae3da5d1a3642ece503ad3de4389
ms.sourcegitcommit: 549224cf13fc761f473c880e8d0d8f2741cc7b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "3435001"
---
# <a name="add-a-condition-to-a-flow"></a>Adición de una condición a un flujo


Especifique que un flujo realice una o varias tareas solo si el valor de una condición es true. Por ejemplo, especifique que recibirá un correo electrónico solo si se retwittea al menos diez veces un tweet que contenga una palabra clave.

## <a name="prerequisites"></a>Requisitos previos

* [Creación de un flujo](get-started-logic-template.md) desde una plantilla: en este tutorial se [utiliza esta plantilla](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) a modo de ejemplo

## <a name="add-a-condition"></a>Agrega una condición

1. En [Power Automate](https://flow.microsoft.com), seleccione **Mis flujos**.

    Si aún no ha iniciado sesión, es posible que necesite hacerlo.

1. Seleccione uno de los flujos de **Mis flujos** y, a continuación, seleccione **Más comandos** (los tres puntos).

   ![Seleccione Editar](./media/add-condition/select-edit.png)

    Este tutorial usa un ejemplo con un desencadenador de Twitter y una acción de SharePoint.

1. Seleccione **Editar**.

1. En la última acción, seleccione **Nuevo paso** > **Condición**.

1. En la tarjeta **Condición**, seleccione un área vacía en el cuadro de la izquierda.

    Se abre la lista **Contenido dinámico**.

1. Seleccione el parámetro **Retweet count** para agregarlo al cuadro.

1. En el cuadro del medio de la tarjeta **Condición**, seleccione **es mayor o igual que**.

1. Escriba **10** en el cuadro de la derecha.

    ![El cuadro Nombre de objeto con un parámetro](./media/add-condition/specify-condition.png)

    Ahora que ha configurado la condición, continúe con los siguientes pasos para enviar un correo electrónico si el valor de **Retweet count** es mayor que 10.

1. Seleccione **Agregar una acción** en el lado **En caso afirmativo** de la condición. 
1. Escriba **Enviar un correo electrónico** en el cuadro de búsqueda y seleccione **Enviar un correo electrónico (V2)**.

   ![Buscar para enviar un mensaje de correo electrónico](./media/add-condition/if-yes-condition.png)

1. Configurar la tarjeta **Enviar un correo electrónico (V2)** a su gusto, indicando el contenido del correo electrónico que el flujo envía si el valor de **Retweet count** es mayor que 10.

   También puede configurar el lado **En caso negativo** de la condición si desea realizar una acción cuando el valor de **Retweet count** es menos de 10.

1. Guarde el flujo.

>[!TIP]
>Puede crear condiciones complejas mediante el botón **Agregar** de la tarjeta de condición.

![Agregar condiciones complejas](./media/add-condition/add-complex-condition.png)

En el modo avanzado puede usar cualquier expresión del *Lenguaje de definición de flujo de trabajo*. Obtenga información sobre todas las [expresiones](https://msdn.microsoft.com/library/azure/mt643789.aspx) disponibles.

## <a name="next-steps"></a>Pasos siguientes

Aprenda a [usar expresiones](use-expressions-in-conditions.md) en las condiciones en modo avanzado.
