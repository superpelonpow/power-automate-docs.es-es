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
ms.date: 03/24/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8b0aebaa0e61758d6bc6ebeb3de7b71bde665edc
ms.sourcegitcommit: bba5bd4ae3879b6bf1521d8ed636374fe09709e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "80525093"
---
# <a name="edit-desktop-ui-flows"></a>Edición de los flujos de la interfaz de usuario de escritorio

Los flujos de interfaz de usuario de escritorio automatizan las aplicaciones de escritorio de Windows. Consulte los [problemas conocidos](create-desktop.md#known-issues-and-solutions) para obtener más información sobre los problemas que podría encontrar, soluciones alternativas para esos problemas y escenarios no admitidos en esta versión.

## <a name="prerequisites"></a>Requisitos previos
Un flujo de interfaz de usuario de escritorio. [Cree ahora un flujo de interfaz de usuario de escritorio](create-desktop.md#create-and-test-desktop-ui-flows) si no tiene ninguno para editarlo.

## <a name="edit-actions"></a>Acciones de edición

![Acciones de edición](../media/edit-desktop/edit-actions.png "Acciones de edición")

Puede editar la grabación para:

-   Modificar el valor de las acciones que la admiten.
-   Eliminar un paso.
-   Eliminar la grabación.
-   Cambiar el orden de las acciones con arrastrar y colocar. Tenga cuidado con esto, porque puede romper la coherencia de la grabación.

Los parámetros avanzados le permiten cambiar:

-  El retraso una vez que se realiza la acción. Por ejemplo, puede agregar un segundo retraso si cambia PT0S a PT1S. Esto puede ser útil cuando la aplicación de destino tiene un tiempo de respuesta lento que no se completa antes del paso siguiente del flujo de interfaz de usuario.
-   El [selector](edit-desktop.md#set-the-selector) del elemento de la interfaz de usuario de destino.


## <a name="add-a-recording"></a>Incorporación de una grabación

Es posible que quiera grabar el flujo de interfaz de usuario en varias sesiones. Una vez que complete la primera grabación, puede continuar de la manera siguiente:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com).
1. Seleccione **Mis flujos** > **Flujos de interfaz de usuario**.
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
1. Seleccione **Mis flujos** > **Flujos de interfaz de usuario**.
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

## <a name="use-advanced-controls"></a>Uso de controles avanzados

Puede incorporar controles avanzados, como **condiciones**, **switch cases** y **finalizar** las acciones en los flujos de interfaz de usuario.

Para realizar estas operaciones avanzadas, realice los pasos siguientes en un flujo de interfaz de usuario existente.

1. Seleccione el flujo de interfaz de usuario que ha creado > **Más comandos** (...) > **Editar**.

1. Seleccione **+**  > **Agregar una acción** en la flecha hacia abajo del paso de flujo de interfaz de usuario al que desea agregar la lógica.

   ![Agregar una acción](../media/edit-desktop/add-action.png)

1. Seleccione **Integrado** y, después, seleccione una de las acciones de control disponibles.

   ![Integrada](../media/edit-desktop/select-built-in.png)

1. Complete la expresión que debe evaluarse. Puede utilizar contenido dinámico y expresiones para evaluar los controles de condición y modificador. Además, puede usar cualquier salida generada a partir de los pasos anteriores del flujo de interfaz de usuario.

   ![Tarjeta de condición](../media/edit-desktop/condition-card.png)


## <a name="handle-error-conditions"></a>Control de condiciones de error

Durante la reproducción pueden surgir condiciones inesperadas y provocar errores en los flujos de interfaz de usuario. Puede usar características avanzadas de control de errores para crear pasos alternativos cuando surjan condiciones inesperadas. 

Estos son los pasos que debe seguir.

1. Inicie sesión en [Power Automate](https://powerautomate.microsoft.com) con su cuenta profesional o educativa.
1. Seleccione **Mis flujos** > **Flujos de interfaz de usuario** para mostrar los flujos de la interfaz de usuario.
1. Seleccione **Más comandos**, los tres puntos verticales correspondientes al flujo de la interfaz de usuario que quiera editar.
1. Seleccione **Editar**.
1. Seleccione la flecha abajo que se encuentra inmediatamente antes del paso de flujo de la interfaz de usuario al que quiere agregar el control de errores y, luego, elija **+** (Insertar nuevo paso).
   
   En la imagen siguiente, vamos a insertar el nuevo paso antes del paso **PostElementText 1**. Esto significa que, si **PostElementText 1** produce un error, se ejecutarán los pasos alternativos que defina a continuación.

      ![Inserción de imagen de nuevo paso](../media/edit-desktop/insert-new-step.png) 

1. Seleccione **Add a parallel branch** (Agregar una rama paralela).

    ![Imagen que muestra la adición de una rama paralela y otras opciones](../media/edit-desktop/add-parallel-branch.png)

1. Seleccione la acción que quiere realizar en la rama paralela si se produce un error al ejecutar el flujo de la interfaz de usuario.

   Puede seleccionar **Grabar aplicación** para realizar una nueva grabación para la rama paralela, o bien seleccionar **Terminar** en las acciones **integradas** para salir de la salida del flujo de la interfaz de usuario correctamente si se produce un error.

    ![Imagen que muestra las opciones de rama paralela](../media/edit-desktop/add-parallel-branch.png)

   >[!NOTE]
   >De forma predeterminada, la acción que se agrega en la rama paralela solo se ejecuta si se produce un error en el paso anterior. Puede seleccionar **...** en la rama paralela > **Configurar ejecución posterior** para cambiar el comportamiento predeterminado. 

      ![Imagen que muestra las opciones, incluida Configurar ejecución posterior](../media/edit-desktop/configure-run-after.png)

1.  En esta pantalla, puede seleccionar la condición sobre la que quiere que se ejecute la rama paralela. Puede seleccionar una de las cuatro opciones disponibles.

    ![Imagen que muestra las opciones de ejecución posterior](../media/edit-desktop/run-after-options.png)

    Nota: No podrá guardar un flujo de la interfaz de usuario cuya rama principal y conjunto de ramas paralelas se establezcan para ejecutarse en la misma condición.



## <a name="enable-coordinate-based-playback"></a>Habilitación de la reproducción basada en coordenadas

La reproducción basada en coordenadas usa el desplazamiento de coordenadas de pantalla relativo al modo de reserva para ayudar a los flujos de la interfaz de usuario a encontrar los objetos de destino que el marco de automatización de la interfaz de usuario de Windows predeterminado no puede encontrar durante la reproducción. 

Estos son algunos de los motivos por los que el marco predeterminado de la automatización de la interfaz de usuario de Windows podría no encontrar objetos de destino durante la reproducción:

- Es posible que la aplicación heredada que está automatizando no use tecnologías de programación que admitan el marco de automatización de la interfaz de usuario de Windows.
- Es posible que la aplicación o sus controles no tengan un elemento XPath, nombre o identificador de automatización de la interfaz de usuario únicos. 
- La aplicación tiene controles dinámicos cuyos nombres o identificadores pueden cambiar. 
- La aplicación tiene controles sin nombre, identificador, identificador único, etc.

>[!TIP]
>Para mejorar la precisión de la reproducción basada en coordenadas, use la misma escala y resolución, además de maximizar la aplicación de destino durante la grabación.

Siga estos pasos después de haber grabado un script de flujo de interfaz de usuario:

1. Expanda el paso que inicia o adjunta la aplicación.
   
   Suele ser el primer paso del script de grabación.
1. Seleccione **Mostrar opciones avanzadas**.
1. Busque las propiedades de **Usar reproducción de coordenadas**.
1. Seleccione **Sí** en la lista para habilitar la reproducción basada en coordenadas.

>[!TIP]
> Puede habilitar o deshabilitar **Usar reproducción de coordenadas** para que cada aplicación aplique la configuración a todos los pasos realizados en esa aplicación.  


>[!WARNING]
>Con la reproducción basada en coordenadas, la automatización puede seleccionar controles que no forman parte de la aplicación de destino debido a una serie de motivos, por ejemplo, que la interfaz de usuario de las aplicaciones de destino cambie drásticamente.




## <a name="next-steps"></a>Pasos siguientes

- Aprenda a [ejecutar el flujo de interfaz de usuario](run-ui-flow.md) que acaba de editar.

- Si quiere hacer más cosas con los flujos de interfaz de usuario, también puede probar los flujos de interfaz de usuario con parámetros de [entrada y salida](inputs-outputs-web.md).

