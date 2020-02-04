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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 391e977343617497328ff231d4808a0c78ceb154
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74371650"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Uso de entradas y salidas en los flujos de la interfaz de usuario de escritorio

[Este tema es documentación preliminar y está sujeto a cambios].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs"></a>Definición de las entradas

Las entradas permiten pasar información de un origen externo, como una base de datos o cualquier conector compatible, al software heredado que automatiza los flujos de interfaz de usuario.

Por ejemplo, puede usar la información de clientes de una lista de SharePoint como origen para la entrada en el software de contabilidad heredado.

### <a name="define-inputs-in-the-ui-flows-wizard"></a>Asistente para definir entradas en los flujos de interfaz de usuario

1. Seleccione "Nueva entrada".

   ![](../media/inputs-outputs-desktop/2eb6313a0e966f1fbfc352445b89ee39.png)

1. Agregue un nombre, un ejemplo de datos y una descripción a la entrada.

    - Los datos de ejemplo se usan durante la grabación o la prueba.

    - La descripción será útil para diferenciar las entradas que ha creado.

   ![](../media/inputs-outputs-desktop/e33d206bf2158228277a276261c49785.png)

1.  Una vez creadas las entradas, puede hacer clic en Siguiente para usarlas en una grabación.

### <a name="use-inputs-to-pass-information-to-the-application"></a>Uso de las entradas para pasar información a la aplicación

1. Durante la grabación, puede usar una entrada en una aplicación si se selecciona **Usar entrada**.

1. En la lista, puede elegir entre tres opciones:

    - Seleccione una de las entradas que definió en el paso **Set up input fields** (Configurar campos de entrada) de los flujos de interfaz de usuario.

    - Use una salida definida previamente (consulte la sección Salidas). Esto es útil para pasar información entre distintas aplicaciones dentro del mismo flujo de interfaz de usuario.

    - Cree una entrada nueva mientras está grabando. La encontrará nuevamente en el paso **Set up input fields** (Configurar campos de entrada) de los flujos de interfaz de usuario.

   ![](../media/inputs-outputs-desktop/de36baa0f85d5a19304e1606de25aa3e.png)

1. Seleccione la ubicación en la que quiere usar la entrada. El valor de ejemplo que definió se usa automáticamente. En el ejemplo siguiente, "Hola mundo" es el valor de ejemplo del nombre de la entrada "Mi entrada" y se agrega a la página dentro de Microsoft Word.  
    
    ![](../media/inputs-outputs-desktop/d6b74dc86f38c51cf1daa0582ff0cc33.png)

1. En los **pasos Grabar y Editar** de Power Automate, expanda las acciones que usan entradas para ver cuál está seleccionada.

   ![](../media/inputs-outputs-desktop/340aa71942b618431b0455b632f76f52.png)

1. Al desencadenar el flujo de interfaz de usuario, puede cambiar el valor de la entrada según su preferencia. Consulte Uso de entradas y salidas para más información.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Uso de salidas para extraer información de la aplicación

Las salidas permiten pasar información del software heredado que los flujos de interfaz de usuario automatizan a un destino externo, como una base de datos o cualquier [conector compatible](https://flow.microsoft.com/connectors/).

Por ejemplo, puede extraer información de clientes del software de contabilidad heredado y agregarla a una lista de SharePoint.

Las salidas solo se pueden crear al grabar el flujo de la interfaz de usuario.

1. Durante una grabación, seleccione en el botón "Get output" (Obtener salida) de la grabadora.

   ![](../media/inputs-outputs-desktop/13f8dfca19c0ed04ca2a0f87bf7055ea.png)

1. Seleccione el botón "Select text" (Seleccionar texto) (es el único tipo de salida disponible por ahora).

   ![](../media/inputs-outputs-desktop/2845b73ee807a5be747c1dc494570ab7.png)

1. Haga clic en un elemento de la interfaz de usuario para seleccionar el texto de la salida. El valor se capturará automáticamente.

   ![](../media/inputs-outputs-desktop/7df19b56aadcd0aef207c7372a04b3c6.png)

   ![](../media/inputs-outputs-desktop/af55a0bf39d805b154a783eff3de131b.png)

1. Defina el nombre y la descripción de la salida.

   ![](../media/inputs-outputs-desktop/a083579ee011dfb76aa21fac116796a3.png)

1. Seleccione **Guardar**. 

La salida ya está disponible en el área dedicada del asistente.

   ![](../media/inputs-outputs-desktop/b9f396de0b5893c5a3152b592911f67a.png)

Cada salida tiene:

-  Un nombre de salida tal como se define durante la grabación.
-  Una descripción: este campo puede ser muy útil cuando se definen muchas salidas durante una grabación y se desea identificarlas fácilmente.
-  Un nombre de acción: la acción en la que se definió la salida en el flujo de interfaz de usuario.

## <a name="delete-an-output-from-a-ui-flow"></a>Eliminación de una salida de un flujo de interfaz de usuario

Para eliminar una salida que ya no necesita, vuelva a la acción asociada y quite el nombre de la salida en el valor dinámico.

## <a name="test-your-ui-flow"></a>Prueba del flujo de interfaz de usuario

La prueba de flujos de interfaz de usuario le permite validar los cambios y el comportamiento de reproducción adecuado.

1. (Opcional) Escriba un valor nuevo en el campo de entrada. 
    
    ![](../media/inputs-outputs-desktop/0b4aef639c4ab30b93413e1e7a5e662d.png)

1. Haga clic en **Probar ahora** para ver el software heredado que se está automatizando. Verá que la automatización del flujo de interfaz de usuario reproduce los pasos que grabó. **No interactúe con el dispositivo durante la reproducción**.

1. Una vez que se complete la reproducción, verá el estado de ejecución del flujo de interfaz de usuario:

    - Para cada acción, hay un estado que indica que la prueba se realizó correctamente y las entradas asociadas.

    - El valor de las salidas obtenidas para esta prueba.

    - Si se generó un error y quiere ver en qué paso se produjo el problema, podrá hacerlo con una captura de pantalla del momento en que ocurrió.

   ![](../media/inputs-outputs-desktop/85056d7942d12a5408005f5b683d432b.png)

## <a name="learn-more"></a>Más información

- Obtenga información sobre cómo [desencadenar el flujo de interfaz de usuario](run-ui-flow.md) que acaba de crear.

- Si quiere hacer más cosas con los flujos de interfaz de usuario, también puede probar los flujos de interfaz de usuario con parámetros de [entrada y salida](inputs-outputs-web.md).


