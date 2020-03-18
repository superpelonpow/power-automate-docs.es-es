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
ms.date: 10/17/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3be9b2414a0f30581763622de0c7d49cb694e3b3
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "79224248"
---
# <a name="add-a-condition-to-a-flow"></a>Adición de una condición a un flujo


Especifique que un flujo realice una o varias tareas solo si el valor de una condición es true. Por ejemplo, especifique que recibirá un correo electrónico solo si se retwittea al menos diez veces un tweet que contenga una palabra clave.

## <a name="prerequisites"></a>Requisitos previos

* [Creación de un flujo](get-started-logic-template.md) desde una plantilla: en este tutorial se [utiliza esta plantilla](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) a modo de ejemplo

## <a name="add-a-condition"></a>Agregar una condición

1. En [Power Automate](https://flow.microsoft.com), seleccione **Mis flujos** en la barra de navegación superior.

    Si aún no ha iniciado sesión, es posible que necesite hacerlo.

1. En la lista de flujos, seleccione cualquiera de los que haya creado.

    Este tutorial usa un ejemplo con un desencadenador de Twitter y una acción de SharePoint.

1. Seleccione **Editar flujo**.

1. En la última acción, haga clic en **Nuevo paso**.

1. Seleccione **Agregar una condición**.

    ![Botón de condición](./media/add-condition/add-condition.png)

1. En la tarjeta **Condición** , seleccione un área vacía en el cuadro de la izquierda.

    Se abre la lista **Contenido dinámico**.

1. Seleccione el parámetro **Retweet count** para agregarlo al cuadro.

1. En el cuadro del medio de la tarjeta **Condición**, seleccione **es mayor o igual que**.

1. Escriba **10** en el cuadro de la derecha.

    ![El cuadro Nombre de objeto con un parámetro](./media/add-condition/specify-condition.png)

1. Seleccione el encabezado de la acción que desee usar dentro de la condición (como **Crear elemento**) y arrástrelo debajo del texto **En caso positivo**.

    Al soltar el cursor, la acción se mueve a ese cuadro.

    ![Acción Arrastrar](./media/add-condition/drag-action.png)

1. Configure la acción tanto como sea necesario.

1. Guarde el flujo.

## <a name="edit-in-advanced-mode"></a>Editar en modo avanzado

También puede seleccionar **Editar en modo avanzado** para escribir condiciones más avanzadas. En el modo avanzado puede usar cualquier expresión del *Lenguaje de definición de flujo de trabajo*. Aprenda todas las [expresiones](https://msdn.microsoft.com/library/azure/mt643789.aspx) disponibles.

## <a name="next-steps"></a>Pasos siguientes

Aprenda a [usar expresiones](use-expressions-in-conditions.md) en condiciones en el modo avanzado.