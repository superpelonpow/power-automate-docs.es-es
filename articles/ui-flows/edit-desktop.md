---
title: Aprenda a editar crear flujos de interfaz de usuario de escritorio | Microsoft Docs
description: Aprenda a editar flujos de interfaz de usuario de escritorio.
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
ms.openlocfilehash: a6b34a58dc028d6d0df9bf03f66a04666998ac69
ms.sourcegitcommit: aefd1ebedfbd8c6cc3d08397ac171cb4ba5b5315
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2020
ms.locfileid: "3412991"
---
# <a name="edit-desktop-ui-flows"></a>Editar flujos de interfaz de usuario de escritorio

Los flujos de interfaz de usuario de escritorio automatizan las aplicaciones de escritorio de Windows. Consulte los [problemas conocidos](create-desktop.md#known-issues-and-solutions) para obtener más información sobre los problemas que podría encontrar, soluciones alternativas para esos problemas y escenarios no admitidos en esta versión.

## <a name="prerequisites"></a>Requisitos previos
Un flujo de interfaz de usuario de escritorio. [Cree ahora un flujo de interfaz de usuario de escritorio](create-desktop.md#create-and-test-desktop-ui-flows) si no tiene ninguno para editarlo.

## <a name="edit-actions"></a>Editar acciones

![Editar acciones](../media/edit-desktop/edit-actions.png "Editar acciones")

Puede editar la grabación para:

-   Modificar el valor de las acciones que la admiten.
-   Eliminar un paso.
-   Eliminar la grabación.
-   Cambiar el orden de las acciones con arrastrar y colocar. Tenga cuidado con esto, porque puede romper la coherencia de la grabación.

Los parámetros avanzados le permiten cambiar:

-  El retraso una vez que se realiza la acción. Por ejemplo, puede agregar un segundo retraso si cambia PT0S a PT1S. Esto puede ser útil cuando la aplicación de destino tiene un tiempo de respuesta lento que no se completa antes del paso siguiente del flujo de interfaz de usuario.
-   El [selector](edit-desktop.md#set-the-selector) del elemento de la interfaz de usuario de destino.


## <a name="add-a-recording"></a>Agregar una grabación

Es posible que quiera grabar el flujo de interfaz de usuario en varias sesiones. Una vez que complete la primera grabación, puede continuar de la manera siguiente:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com).
1. Seleccione **Mis flujos** > **Flujos de interfaz de usuario**.
1. Seleccione el flujo de interfaz de usuario que quiere editar.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Seleccione **Editar**. 
1. Seleccione **Nuevo paso**.

   ![Nuevo paso](../media/edit-desktop/new-step.png "Nuevo paso")

1. Seleccione **Grabar aplicación** en la lista de acciones.

   ![Grabar aplicación](../media/edit-desktop/select-record-ui-actions.png "Grabar aplicación")

1. Seleccione **Iniciar grabadora**.

   ![Seleccione Iniciar grabadora](../media/create-windows-ui-flow/select-launch-recorder.png "Seleccione Iniciar grabadora")

   El control de la grabadora aparece en la parte superior de la pantalla.

   ![El control de la grabadora](../media/create-windows-ui-flow/recorder-control.png "El control de la grabadora")

1. Inicie la aplicación que quiere grabar.

     >[!TIP]
     >Si mantiene el ratón sobre los controles de la aplicación, verá que cada control se resalta con un contorno azul. Espere siempre el resaltado azul antes de seleccionar un control.
     >
     >Si el resaltado azul no aparece alrededor del elemento, es posible que no se grabe correctamente.

1. Seleccione **Grabar** en el control de la grabadora.

1. Siga los pasos de la interfaz de usuario de la aplicación que está grabando y, luego, seleccione **Listo** en el control de la grabadora.
1. Seleccione **Guardar** y, luego, pruebe el flujo de interfaz de usuario.

## <a name="add-a-manual-action"></a>Agregar una acción manual

Una vez que haya grabado una aplicación con al menos una acción, puede agregar manualmente cualquier de estas acciones para esa aplicación.

| **Action**          | **Comentario**                                                       |
|---------------------|-------------------------------------------------------------------|
| Cerrar aplicación   |                                                                   |
| Clic con el botón derecho         |                                                                   |
| Enviar teclas           | Enviar teclas y combinaciones de teclas, como CTRL + C.                             |
| Clic con el botón izquierdo          |                                                                   |
| Obtener texto            | Leer el texto desde un elemento de la interfaz de usuario y luego lo usa como salida. |
| Escribir texto          |                                                                   |
| Obtener un elemento habilitado | Comprueba si un elemento de la interfaz de usuario está habilitado o deshabilitado.         |
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

1. Seleccione **Agregar una acción** en la tarjeta de grabación, justo debajo del último paso grabado.
   Verá la lista de acciones manuales mencionadas anteriormente en el tutorial. 

1. Seleccione la acción que quiere agregar. Aquí seleccionó **Obtener un elemento habilitado**, pero puede seleccionar cualquier acción adecuada para el escenario.

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

Debe proporcionar los datos para los campos **elementStack** y **elementXPath** del elemento del selector.

Este es un ejemplo del aspecto que podría tener **elementStack**.

![Pila de elemento](../media/edit-desktop/elementstack.png "Pila de elemento")

Puede capturar **elementXPath** con la [grabadora de la interfaz de usuario WinAppDriver](https://blogs.windows.com/windowsdeveloper/2018/06/20/introducing-winappdriver-ui-recorder/).

![Herramienta WAD](../media/edit-desktop/wad-tool.png "Herramienta WAD")

Quite el primer elemento (todo antes de /Windows) antes de usar el resultado en **elementXPath** del selector.

Pruebe el flujo de interfaz de usuario para confirmar que el selector funciona correctamente.

## <a name="use-advanced-controls"></a>Uso de controles avanzados

Puede incorporar controles avanzados, como **condiciones**, **switch cases** y **finalizar** las acciones en los flujos de interfaz de usuario.

Para realizar estas operaciones avanzadas, realice los pasos siguientes en un flujo de interfaz de usuario existente.

1. Seleccione el flujo de interfaz de usuario que ha creado > **Más comandos** (...) > **Editar**.

1. Seleccione **+** > **Agregar una acción** en la flecha hacia abajo del paso de flujo de interfaz de usuario al que desea agregar la lógica.

   ![Agregar una acción](../media/edit-desktop/add-action.png)

1. Seleccione **Integrado** y, después, seleccione una de las acciones de control disponibles.

   ![Integrado](../media/edit-desktop/select-built-in.png)

1. Complete la expresión que debe evaluarse. Puede utilizar contenido dinámico y expresiones para evaluar los controles de condición y modificador. Además, puede usar cualquier salida generada a partir de los pasos anteriores del flujo de interfaz de usuario.

   ![Tarjeta de condición](../media/edit-desktop/condition-card.png)


## <a name="add-a-recording-of-a-remote-computer-using-image-recognition-preview"></a>Agregar una grabación de una computadora remota utilizando el reconocimiento de imagen (Vista previa)

[!INCLUDE[cc-beta-prerelease-disclaimer](../includes/cc-preview-features-expect-changes.md)]

El reconocimiento de imagen en los flujos de la interfaz de usuario es una función de vista previa y actualmente está disponible al grabar una computadora remota a través de la aplicación Remote Desktop Connection (RDC).
 

### <a name="what-is-image-recognition"></a>¿Qué es el reconocimiento de imagen?

Actualmente, los flujos de IU de escritorio se registran principalmente mediante API de accesibilidad (UI Automation y WinAppDriver) para detectar los controles en el árbol de interfaz de usuario de Microsoft Windows. A veces, el árbol de la IU no está disponible, como ocurre con las aplicaciones basadas en web o Java. El árbol de la interfaz de usuario puede no ser fiable, como cuando las ID de un control cambian con frecuencia o entre sesiones. 

Con el reconocimiento de imágenes, las ubicaciones de los clics y otros detalles coinciden visualmente durante la reproducción, ampliando enormemente la gama de aplicaciones que pueden automatizarse. 

### <a name="use-image-recognition-to-record-a-remote-computer"></a>Use el reconocimiento de imagen para grabar una computadora remota

 
1. En un flujo de interfaz de usuario nuevo o existente, vaya a la pestaña Entradas y cree dos entradas nuevas de **texto de carácter reservado**, una para el nombre de usuario y otra para la contraseña que se utilizará para iniciar sesión en el dispositivo remoto. Las entradas de texto de carácter reservado le permiten pasar los valores dinámicamente al probar o llamar al flujo de la interfaz de usuario desde otro flujo, sin que el flujo de la interfaz de usuario los almacene o registre.

   ![Texto de carácter reservado ](../media/create-remote-desktop/ir-sensitive-text.png)

1. Sigue los pasos en **Agregar una grabación** para iniciar el control de la grabadora para un flujo de interfaz de usuario nuevo o existente.

1. Use la aplicación Escritorio remoto para conectarse a la computadora remota.

1. Expanda la ventana Escritorio remoto a pantalla completa.

1. Seleccione **Grabar** desde el control de la grabadora y seleccione **Entendido** en la alerta que aparece.

   ![Ventana emergente](../media/create-remote-desktop/popup.png)

1. Realice los pasos en el ordenador remoto y luego seleccione **Listo** en el control de la grabadora.

1. Localice la acción **Iniciar Escritorio remoto** dentro de su grabación, y luego introduzca las entradas de texto de carácter reservado para el nombre de usuario y la contraseña.

![Texto de carácter reservado para el nombre de usuario y la contraseña](../media/create-remote-desktop/ir-launch-emote_desktop-session.png)

1. Seleccione **Guardar** y, luego, pruebe el flujo de interfaz de usuario.

>[!IMPORTANT]
>Cuando llama a este flujo de interfaz de usuario desde un flujo automatizado, se recomienda utilizar una solución de administración de claves como [Azure Key Vault](https://azure.microsoft.com/services/key-vault/) para recuperar el nombre de usuario y la contraseña y luego pasarlos a las entradas de **texto de carácter reservado** en la interfaz de usuario que fluyen dinámicamente, en lugar de almacenarlas en el flujo mismo. 

>[!TIP]
> Habilite **Entradas seguras** en el menú **Configuración** para la acción **Ejecutar un flujo de interfaz de usuario para escritorio** en el flujo que llama al flujo de la interfaz de usuario. Esto garantiza que las entradas no se almacenen en el historial de ejecución.

### <a name="use-the-extract-text-from-image-action-while-recording-to-retrieve-an-output-from-a-remote-computer"></a>Use la acción Extraer texto de imagen mientras graba para recuperar una salida de una computadora remota.

1. Mientras graba sus pasos, navegue hasta la ubicación del texto que desea capturar.

1. Seleccione **Salidas** > **Extraer texto de imagen** desde el control de la grabadora.

1. Siga las indicaciones para seleccionar un **área de anclaje** (una sección de la pantalla que no se espera que cambie, como la etiqueta al lado de un campo).

    ![Área de anclaje](../media/create-remote-desktop/ir-anchors.png)

1.  Seleccione el **área objetivo** (el área de la que se extraerá el texto usando OCR).

    ![Área objetivo](../media/create-remote-desktop/ir-targets.png)

1.  Introduzca un nombre para la salida.

1.  Seleccione **Listo** en el control de la grabadora.

1.  Seleccione **Guardar** y, luego, pruebe el flujo de interfaz de usuario.


### <a name="known-issues-for-remote-desktop-recordings"></a>Problemas conocidos para grabaciones de escritorio remoto

1. Asegúrese de que todas las entradas requeridas (nombre de la computadora, nombre de usuario y contraseña) se completen y guarden antes de registrar más pasos en el mismo flujo de interfaz de usuario.

1. Para adjuntar a una sesión de escritorio remoto existente, la sesión debe haberse iniciado antes en el mismo flujo de interfaz de usuario.

1. La forma recomendada de iniciar la Conexión a Escritorio remoto (RDC) al grabar es desde la aplicación Conexión a Escritorio remoto (mstc.exe) desde el menú Inicio. Si se registran acciones de seguridad de Windows además de la acción **Iniciar Escritorio remoto**, deben eliminarse del diseñador para que la reproducción no se interrumpa (esto puede suceder cuando la sesión de Escritorio remoto se inicia desde un acceso directo).

1. La reproducción puede fallar si el flujo de la interfaz de usuario se registró en una pantalla con escala de pantalla (Configuración de Windows> Pantalla> Escala de pantalla) establecida en un valor diferente al 100%. Como solución alternativa, asegúrese de que la escala de la pantalla esté configurada al 100% antes de la grabación.


## <a name="handle-error-conditions"></a>Control de condiciones de error

Pueden surgir condiciones inesperadas durante la reproducción. Estas condiciones pueden hacer que sus flujos de interfaz de usuario fallen. Puede usar características avanzadas de control de errores para crear pasos alternativos cuando surjan condiciones inesperadas. 

Estos son los pasos que debe seguir.

1. Inicie sesión con una cuenta profesional o educativa en [Power Automate](https://powerautomate.microsoft.com).
1. Seleccione **Mis flujos** > **Flujos de interfaz de usuario**.
1. Seleccione **Más comandos**, los tres puntos verticales correspondientes al flujo de la interfaz de usuario que quiera editar.
1. Seleccione **Editar**.
1. Seleccione la flecha abajo que se encuentra inmediatamente antes del paso de flujo de la interfaz de usuario al que quiere agregar el control de errores y, luego, elija **+** (Insertar nuevo paso).
   
   En la imagen siguiente, vamos a insertar el nuevo paso antes del paso **PostElementText 1**. Esto significa que, si **PostElementText 1** produce un error, se ejecutarán los pasos alternativos que defina a continuación.

      ![Inserción de imagen de nuevo paso](../media/edit-desktop/insert-new-step.png) 

1. Seleccione **Agregar una rama paralela**.

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

