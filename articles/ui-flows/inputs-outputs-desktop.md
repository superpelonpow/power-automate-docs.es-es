---
title: Uso de entradas y salidas en los flujos de la interfaz de usuario de escritorio | Microsoft Docs
description: Use entradas y salidas en los flujos de la interfaz de usuario de escritorio.
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
ms.openlocfilehash: fd4200c98df4a60318b5d95ab590d4ec59e6bef3
ms.sourcegitcommit: bba5bd4ae3879b6bf1521d8ed636374fe09709e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "80524844"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Uso de entradas y salidas en los flujos de la interfaz de usuario de escritorio

Use las entradas para pasar información de un origen externo, como una base de datos o cualquier conector compatible, al software heredado que automatiza los flujos de interfaz de usuario.

Por ejemplo, puede usar la información de clientes de una lista de SharePoint como origen para la entrada en el software de contabilidad heredado.

## <a name="define-inputs-in-the-ui-flows-wizard"></a>Asistente para definir entradas en los flujos de interfaz de usuario

1. Seleccione **Nueva entrada**.

   ![Seleccionar Nuevo](../media/inputs-outputs-desktop/select-new.png)

1. Agregue un nombre, un ejemplo de datos y una descripción a la entrada.

    - Los datos de ejemplo se usan durante la grabación o la prueba.

    - La descripción será útil para diferenciar las entradas que ha creado.

   ![Campos de entrada](../media/inputs-outputs-desktop/input-fields.png)

1.  Una vez creadas las entradas, puede hacer clic en Siguiente para usarlas en una grabación.

>[!TIP]
>Puede usar la combinación de teclas **CRTL + ALT + L** para insertar texto que puede pasar desde o hacia la aplicación que se usa en el flujo de interfaz de usuario. Esta combinación de teclas funciona para texto confidencial, estático, de salida y de entrada. 

## <a name="use-inputs-to-pass-information-to-the-application"></a>Uso de las entradas para pasar información a la aplicación

1. Durante la grabación, puede usar una entrada en una aplicación si se selecciona **Usar entrada**.

1. En la lista, puede elegir entre tres opciones:

    - Seleccione una de las entradas que definió en el paso **Configuración de campos de entrada**.

    - Use una salida definida previamente (consulte la sección Salidas). Esto es útil para pasar información entre distintas aplicaciones dentro del mismo flujo de interfaz de usuario.

    - Cree una entrada nueva mientras está grabando. La encontrará nuevamente en el paso **Configuración de campos de entrada**.

   ![Seleccionar el tipo de entrada](../media/inputs-outputs-desktop/select-input-type.png)

1. Seleccione la ubicación en la que quiere usar la entrada. El valor de ejemplo que definió se usa automáticamente. En el ejemplo siguiente, "Hola mundo" es el valor de ejemplo del nombre de la entrada "Mi entrada" y se agrega a la página dentro de Microsoft Word.  
    
    ![Seleccionar la ubicación de la entrada](../media/inputs-outputs-desktop/select-location-for-input.png)

1. En la sección **Grabar y editar pasos** de Power Automate, expanda las acciones que usan entradas para ver cuál está seleccionada.

   ![Expandir acciones](../media/inputs-outputs-desktop/expand-actions.png)

1. Al desencadenar el flujo de interfaz de usuario, puede cambiar el valor de la entrada según su preferencia.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Uso de salidas para extraer información de la aplicación

Las salidas permiten pasar información del software heredado que los flujos de interfaz de usuario automatizan a un destino externo, como una base de datos o cualquier [conector compatible](https://flow.microsoft.com/connectors/).

Por ejemplo, puede extraer información de clientes del software de contabilidad heredado y agregarla a una lista de SharePoint.

Las salidas solo se pueden crear al grabar el flujo de la interfaz de usuario.

1. Durante una grabación, seleccione **Obtener salida**.

   ![Obtener salida](../media/inputs-outputs-desktop/get-output.png)

1. Seleccione **Seleccionar texto**.

   ![Seleccionar texto](../media/inputs-outputs-desktop/select-text.png)

1. Seleccione un elemento de la interfaz de usuario para obtener el texto de la salida. El valor de texto se capturará automáticamente.

   <!-- ![Get element output](../media/inputs-outputs-desktop/get-element-output.png) -->

   ![Seleccione un elemento de interfaz de usuario](../media/inputs-outputs-desktop/select-ui-element.png)

1. Proporcione un nombre y una descripción para la salida.

   ![Proporcione un nombre y una descripción](../media/inputs-outputs-desktop/name-description.png)

1. Seleccione **Guardar**. 

La salida ya está disponible en el área dedicada del asistente.

   ![La salida está disponible](../media/inputs-outputs-desktop/output-available.png)

Cada salida tiene:

-  Un nombre de salida tal como se define durante la grabación.
-  Una descripción: Este campo puede ser muy útil cuando se definen muchas salidas durante una grabación y se quiere identificarlas fácilmente en un momento posterior.
-  Un nombre de acción: la acción en la que se definió la salida en el flujo de interfaz de usuario.

## <a name="delete-an-output-from-a-ui-flow"></a>Eliminación de una salida de un flujo de interfaz de usuario

Para eliminar una salida que ya no necesita, vaya a la acción asociada y quite el nombre de la salida en el valor dinámico.

## <a name="test-your-ui-flow"></a>Prueba del flujo de interfaz de usuario

La prueba de flujos de interfaz de usuario le permite validar los cambios y el comportamiento de reproducción adecuado.

1. (Opcional) Escriba un valor nuevo en el campo de entrada. 
    
    ![Nuevo valor de prueba](../media/inputs-outputs-desktop/new-test-value.png)

1. Haga clic en **Probar ahora** para ver el software heredado que se está automatizando. Verá que la automatización del flujo de interfaz de usuario reproduce los pasos que grabó. **No interactúe con el dispositivo durante la reproducción**.

1. Una vez completada la reproducción, verá el estado de ejecución del flujo de interfaz de usuario:

    - Para cada acción, hay un indicador de estado que muestra las entradas asociadas y que la prueba se ha realizado correctamente.

    - El valor de las salidas obtenidas para esta prueba.

    - Si se produce un error, verá qué paso ha causado el problema con una captura de pantalla del momento en que se ha producido el error.

   ![Ejecución correcta](../media/inputs-outputs-desktop/successful-run.png)

## <a name="learn-more"></a>Más información

- Aprenda a [desencadenar flujos de interfaz de usuario](run-ui-flow.md).



