---
title: Uso de entradas y salidas en los flujos de la interfaz de usuario de escritorio | Microsoft Docs
description: Usar entradas y salidas en flujos de interfaz de usuario de escritorio.
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
ms.openlocfilehash: bf7f21915b63087911edbdbbe181bb5073ffbfb9
ms.sourcegitcommit: aefd1ebedfbd8c6cc3d08397ac171cb4ba5b5315
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2020
ms.locfileid: "3412943"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Usar entradas y salidas en flujos de interfaz de usuario de escritorio

Use las entradas para pasar información de un origen externo, como una base de datos o cualquier conector compatible, al software heredado que automatiza los flujos de interfaz de usuario.

Por ejemplo, puede usar la información de clientes de una lista de SharePoint como origen para la entrada en el software de contabilidad heredado. También puede pasar entradas confidenciales como un nombre de usuario o una contraseña que se requieren para iniciar sesión en una aplicación heredada utilizando **Entradas de texto de carácter reservado**.

## <a name="define-inputs-in-the-ui-flows"></a>Definir entradas en los flujos de interfaz de usuario

1. Seleccione **Texto** para definir una entrada o seleccione **Texto de carácter reservado** para definir una entrada de texto de carácter reservado. 

   ![Seleccione nuevo](../media/inputs-outputs-desktop/text-input.png)

1. Agregue un nombre, un ejemplo de datos y una descripción a la entrada.

    - Los datos de ejemplo se usan durante la grabación o la prueba.

    - La descripción será útil para diferenciar las entradas que ha creado.

    - Para entradas de texto confidenciales, el valor de la muestra se oscurecerá y no se mantendrá después de guardar

   ![Campos de entrada](../media/inputs-outputs-desktop/text-input.png)

1.  Una vez creadas las entradas, puede hacer clic en Siguiente para usarlas en una grabación.

>[!TIP]
>Puede usar la combinación de teclas **CTRL + ALT + L** para insertar texto que puede pasar desde o hacia la aplicación que se usa en el flujo de interfaz de usuario. Esta combinación de teclas funciona para texto confidencial, estático, de salida y de entrada. 

## <a name="use-inputs-to-pass-information-to-the-application"></a>Uso de las entradas para pasar información a la aplicación

1. Durante la grabación, puede usar una entrada en una aplicación si se selecciona **Usar entradas**.

1. En la lista, puede elegir entre tres opciones:

    - Seleccione una de las entradas que definió en el paso **Configuración de entradas**.

      >[!TIP]
      >Puede identificar entradas de texto confidenciales fácilmente porque tienen un icono diferente de las entradas de texto.

    - Use una salida definida previamente (consulte la sección Salidas). Esto es útil para pasar información entre distintas aplicaciones dentro del mismo flujo de interfaz de usuario.

    - Cree un nuevo texto o entrada de texto sensible mientras graba utilizando la opción **Nueva entrada**. La encontrará nuevamente en el paso **Configuración de entrada**.

   ![Seleccionar el tipo de entrada](../media/inputs-outputs-desktop/select-input-type.png)

1. Seleccione la ubicación en la que quiere usar la entrada. El valor de ejemplo que definió se usa automáticamente. En el ejemplo siguiente, "WingTip Toys" es el valor de ejemplo del nombre de la entrada "Cuenta de facturación" y se agrega a la aplicación.  
    
    ![Seleccionar la ubicación de la entrada](../media/inputs-outputs-desktop/select-location-for-input.png)

1. En **Registrar y editar pasos** de Power Automate, expanda las acciones que usan entradas para ver cuál está seleccionada.

    En el ejemplo que sigue, verá que se utiliza "Cuenta de facturación" como valor.

   ![Expandir acciones](../media/inputs-outputs-desktop/expand-actions.png)


   >[!NOTE]
   >Si también usó una entrada de texto confidencial, verá una acción con un icono de candado en la parte superior derecha para indicar que usó la entrada de texto confidencial.


   ![Expandir acciones](../media/inputs-outputs-desktop/lock-action.png)

1. Al desencadenar el flujo de interfaz de usuario, puede cambiar el valor de la entrada según su preferencia.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Uso de salidas para extraer información de la aplicación

Las salidas permiten pasar información del software heredado que los flujos de interfaz de usuario automatizan a un destino externo, como una base de datos o cualquier [conector compatible](https://flow.microsoft.com/connectors/).

Por ejemplo, puede extraer información de clientes del software de contabilidad heredado y agregarla a una lista de SharePoint.

Las salidas solo se pueden crear al grabar el flujo de la interfaz de usuario.

1. Durante una grabación, seleccione **Salida**.

   ![Obtener salida](../media/inputs-outputs-desktop/get-output.png)

1. Seleccione **Seleccionar texto**.

   ![Seleccionar texto](../media/inputs-outputs-desktop/select-text.png)

1. Seleccione un elemento de la interfaz de usuario para obtener el texto de la salida. El valor de texto se capturará automáticamente. Puede proporcionar un nombre y una descripción para la salida.

   ![Seleccione un elemento de interfaz de usuario](../media/inputs-outputs-desktop/select-ui-element.png)

1. Proporcione un nombre y una descripción para la salida.

1. Seleccione **Guardar**. 

La salida ya está disponible en el área dedicada del asistente.

   ![La salida está disponible](../media/inputs-outputs-desktop/output-available.png)

Cada salida tiene:

-  Un nombre de salida tal como se define durante la grabación.
-  Una descripción: este campo puede ser muy útil cuando se definen muchas salidas durante una grabación y se desea identificarlas más tarde.
-  Un nombre de acción: la acción en la que se definió la salida en el flujo de interfaz de usuario.

## <a name="use-clipboard-content-to-define-outputs"></a>Usar contenido del portapapeles para definir salidas 

Durante una grabación es posible copiar un texto en el portapapeles de su ordenador y definirlo como salida de su flujo de interfaz de usuario.

1. Durante su grabación, copie un valor de cadena  

1. Seleccione **Obtener texto del portapapeles**. El contenido de su portapapeles se muestra en el campo **Valor de la muestra** 

   ![Salida del portapapeles](../media/inputs-outputs-desktop/get-output-clipboard.png)

1. Defina un nombre y una descripción para su salida (como se describe arriba) y seleccione **Guardar.** 

    ![Salida del portapapeles](../media/inputs-outputs-desktop/get-output-clipboard-2.png)

## <a name="delete-an-output-from-a-ui-flow"></a>Eliminación de una salida de un flujo de interfaz de usuario

Para eliminar una salida que ya no necesita, vaya a la acción asociada y quite el nombre de la salida en el valor dinámico.

## <a name="test-your-ui-flow"></a>Probar el flujo de interfaz de usuario

La prueba de flujos de interfaz de usuario le permite validar los cambios y el comportamiento de reproducción adecuado.

1. (Opcional) Escriba un valor en el campo de entrada. 

   >[!NOTE]
   >Para cualquier entrada de texto confidencial que se cree en la grabadora, el valor de la muestra deberá especificarse nuevamente antes de la prueba.
    
    ![Nuevo valor de prueba](../media/inputs-outputs-desktop/new-test-value.png)

1. Seleccione **Probar ahora** para ver el software heredado que se está automatizando. Verá que la automatización del flujo de interfaz de usuario reproduce los pasos que grabó. **No interactúe con el dispositivo durante la reproducción**.

1. Una vez completada la reproducción, verá el estado de ejecución del flujo de interfaz de usuario:

    - Para cada acción, hay un indicador de estado que muestra las entradas asociadas y que la prueba se ha realizado correctamente.

      ![Ejecución correcta](../media/inputs-outputs-desktop/successful-run.png)

   - Para cada acción que usa una entrada de **Texto confidencial**, el valor de entrada no se mostrará.

      ![Otra imagen](../media/inputs-outputs-desktop/sensitive-text-not-displayed.png)

   - También verá el valor de los resultados obtenidos para esta prueba en la parte inferior del diseñador. 

      ![Otra imagen](../media/inputs-outputs-desktop/outputs-value.png)

   - Si se produce un error, verá qué paso ha causado el problema junto con una captura de pantalla del momento en que se ha producido el error.

## <a name="learn-more"></a>Más información

- Aprenda a [desencadenar flujos de interfaz de usuario](run-ui-flow.md).



