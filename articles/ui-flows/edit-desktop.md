---
title: Información sobre editar crear flujos de interfaz de usuario de escritorio | Microsoft Docs
description: Obtenga información sobre cómo editar flujos de interfaz de usuario de escritorio.
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9c9da27098ca9114c0919d0fb6e70495f442a3c6
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74371719"
---
# <a name="edit-desktop-ui-flows"></a>Edición de los flujos de la interfaz de usuario de escritorio

[Este tema es documentación preliminar y está sujeto a cambios].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Los flujos de interfaz de usuario de escritorio automatizan las aplicaciones de escritorio de Windows. Consulte los [problemas conocidos](create-desktop.md#known-issues-and-solutions) para más información sobre los problemas que podría encontrar, soluciones alternativas para esos problemas y escenarios no admitidos en esta versión preliminar.

## <a name="prerequisites"></a>Requisitos previos
Un flujo de interfaz de usuario de escritorio. [Cree ahora un flujo de interfaz de usuario de escritorio](create-desktop.md#create-and-test-desktop-ui-flows) si no tiene ninguno para editarlo.

## <a name="edit-actions"></a>Acciones de edición

![Acciones de edición](../media/edit-desktop/edit-actions.png "Acciones de edición")

Puede editar la grabación para:

-   Modificar el valor de las acciones que la admiten.
-   Eliminar un paso.
-   Eliminar toda la grabación.
-   Cambiar el orden de las acciones con arrastrar y colocar. Tenga cuidado con esto, porque puede romper la coherencia de la grabación.

Los parámetros avanzados le permiten cambiar:

-  El retraso una vez que se realiza la acción. Por ejemplo, puede agregar un segundo retraso si cambia PT0S a PT1S. Esto puede ser útil cuando la aplicación de destino tiene un tiempo de respuesta lento que no se completa antes del paso siguiente del flujo de interfaz de usuario.
-   El [selector](edit-desktop.md#set-the-selector) del elemento de la interfaz de usuario de destino.

## <a name="add-a-recording"></a>Incorporación de una grabación

Es posible que quiera grabar el flujo de interfaz de usuario en varias sesiones. Una vez que complete la primera grabación, puede continuar de la manera siguiente:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com).
1. Seleccione **Mis flujos** > **Flujos de interfaz de usuario (versión preliminar)** .
1. Seleccione el flujo de interfaz de usuario que quiere editar.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Seleccione **Editar**. 
1. Seleccione **Nuevo paso**.

   ![Nuevo paso](../media/edit-desktop/new-step.png "Nuevo paso")

1. Seleccione **Record app** (Grabar aplicación) en la lista de acciones.

   ![Record app (Grabar aplicación)](../media/edit-desktop/select-record-ui-actions.png "Record app (Grabar aplicación)")

1. Seleccione **Launch recorder** (Iniciar grabadora).

   ![Seleccionar Launch recorder (Iniciar grabadora)](../media/create-windows-ui-flow/select-launch-recorder.png "Seleccionar Launch recorder (Iniciar grabadora)")

   El control de la grabadora aparece en la parte superior de la pantalla.

   ![El control de la grabadora](../media/create-windows-ui-flow/recorder-control.png "El control de la grabadora")

1. Inicie la aplicación que quiere grabar.

     >[!TIP]
     >Si mantiene el mouse sobre los controles de la aplicación, verá que cada control se resalta con un contorno azul. Espere siempre el resaltado azul antes de seleccionar un control.
     >
     >Si el resaltado azul no aparece alrededor del elemento, es posible que no se grabe correctamente.

1. Seleccione **Record** (Grabar) en el control de la grabadora.

1. Siga los pasos de la interfaz de usuario de la aplicación que está grabando y, luego, seleccione **Done** (Listo) en el control de la grabadora.
1. Seleccione **Guardar** y, luego, pruebe el flujo de interfaz de usuario.

## <a name="add-a-manual-action"></a>Incorporación de una acción manual

Una vez que haya grabado una aplicación con al menos una acción, puede agregar manualmente cualquier de estas acciones para esa aplicación.

| **Acción**          | **Comentario**                                                       |
|---------------------|-------------------------------------------------------------------|
| Cerrar aplicación   |                                                                   |
| Clic con el botón derecho         |                                                                   |
| Enviar teclas           | Enviar teclas y combinaciones de teclas, como CTRL + C.                             |
| Clic con el botón izquierdo          |                                                                   |
| Obtener texto            | Leer el texto desde un elemento de la interfaz de usuario y luego usarlo como salida. |
| Escribir texto          |                                                                   |
| Obtener un elemento habilitado | Comprobar si un elemento de la interfaz de usuario está habilitado o deshabilitado.         |
| Borrar un elemento       | Borrar el valor en un elemento de interfaz de usuario editable.             |
| Esperar unos segundos    | Esperar antes de ir al paso siguiente.                           |

Siga estos pasos para agregar una acción manual:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com).
1. Seleccione **Mis flujos** > **Flujos de interfaz de usuario (versión preliminar)** .
1. Seleccione el flujo de interfaz de usuario que quiere editar.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Seleccione **Editar**. 
1. Seleccione la tarjeta de grabación que contiene los pasos a los que quiere agregar un paso nuevo.
   La tarjeta se expande y muestra los pasos grabados.

   ![Selección de la tarjeta de grabación](../media/edit-desktop/manual-select-recording-card.png)

1. Seleccione **Add an action** (Agregar una acción) en la tarjeta de grabación, justo debajo del último paso grabado.
   Verá la lista de acciones manuales mencionadas anteriormente en el tutorial. 

1. Seleccione la acción que quiere agregar. Aquí se seleccionó **Obtener un elemento habilitado**, pero puede seleccionar cualquier acción adecuada para el escenario.

   ![Select action to add.png](../media/edit-desktop/select-action-to-add.png)

Una vez que se agrega la acción, deberá establecer el **Selector** en las opciones avanzadas de la acción.

![Opciones avanzadas de la acción](../media/edit-desktop/action-advanced-options.png "Opciones avanzadas de la acción")

### <a name="set-the-selector"></a>Establecimiento del selector

El selector identifica el elemento de la interfaz de usuario en el que se realiza la acción durante la reproducción. Se recomienda copiar y pegar esta información desde un paso independiente que tenga como destino el mismo elemento de la interfaz de usuario, si es posible.

El formato del selector es:

```json
{  
   "type":"WinUIA",
   "parameters":{  
      "elementStack":[  

      ],
      "elementXPath":""
   }
}
```

Debe proporcionar los datos para los campos **elemementStack** y **elementXPath** del elemento del selector.

Este es un ejemplo del aspecto que podría tener **elemementStack**.

![Pila de elemento](../media/edit-desktop/elementstack.png "Pila de elemento")

Puede capturar **elementXPath** con la [grabadora de la interfaz de usuario WinAppDriver](https://blogs.windows.com/windowsdeveloper/2018/06/20/introducing-winappdriver-ui-recorder/).

![Herramienta WAD](../media/edit-desktop/wad-tool.png "Herramienta WAD")

Quite el primer elemento (todo antes de /Windows) antes de usar el resultado en **elementXPath** del selector.

Pruebe el flujo de interfaz de usuario para confirmar que el selector funciona correctamente.

## <a name="next-steps"></a>Pasos siguientes

- Aprenda a [ejecutar el flujo de interfaz de usuario](run-ui-flow.md) que acaba de editar.

- Si quiere hacer más cosas con los flujos de interfaz de usuario, también puede probar los flujos de interfaz de usuario con parámetros de [entrada y salida](inputs-outputs-web.md).

