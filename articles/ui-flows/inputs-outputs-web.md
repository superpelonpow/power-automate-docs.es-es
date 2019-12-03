---
title: Uso de entradas y salidas en los flujos de interfaz de usuario web | Microsoft Docs
description: Use entradas y salidas en los flujos de interfaz de usuario web.
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
ms.openlocfilehash: 38b6ba7f8fe3ab7a386229b6c9c5ccc300a147de
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74371420"
---
# <a name="use-inputs-and-outputs-in-web-ui-flows"></a>Uso de entradas y salidas en los flujos de la interfaz de usuario web

[Este tema es documentación preliminar y está sujeto a cambios].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs-for-a-web-ui-flow"></a>Definición de entradas para un flujo de interfaz de usuario web

Las entradas de un flujo de interfaz de usuario permiten pasar información de un origen externo, como una base de datos u otro flujo de interfaz de usuario, al software heredado de destino que se automatizará.

Cualquier variable que se use (lectura) antes de la inicialización (que habitualmente se hace a través de los comandos **store**) se tratará automáticamente como una variable de entrada y se mostrará en la tarjeta de acción **Run a UI Flow for web** (Ejecutar un flujo de interfaz de usuario para Web).

Puede usar variables a través de la interpolación de cadenas; por ejemplo, cambie el campo de destino del comando click a "id=\${elementId}". O cambie el campo del valor del comando type a "\${inputText}".

El comando **set window size** y el comando **type** de las capturas de pantalla siguientes usan variables sin inicializar \${Width}, \${Height} y \${search}. Estas variables se convertirán en valores de entrada.

![Establecimiento del tipo y el tamaño de la ventana](../media/inputs-outputs-web/f05cb445dad212aaf395b66ba969622c.png "Establecimiento del tipo y el tamaño de la ventana")

Puede usar variables directamente en algunos comandos; por ejemplo, los campos de destino o valor del comando forEach son variables, no es necesario que lo incluya con "\${}".

Consulte la referencia de [comandos de Selenium](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) para determinar qué comandos toman directamente el nombre de la variable.

## <a name="define-outputs-for-a-web-ui-flow"></a>Definición de salidas para un flujo de interfaz de usuario web

Cualquier variable definida en el script de Selenium se convierte automáticamente en un valor de salida. Use estos comandos para declarar variables:

[Store](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store)

[Store attribute](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-attribute)

[Store json](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-json)

[Store title](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-title)

[store value](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-value)

[Store window handle](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-window-handle)

[Store xpath count](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-xpath-count)

[Execute script](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#execute-script) (agregue la sintaxis "return" para devolver el objeto que quiere almacenar en el final del script)

## <a name="next-steps"></a>Pasos siguientes

- Aprenda a [crear flujos de interfaz de usuario web](create-web.md).
- Aprenda a [desencadenar flujos de interfaz de usuario](run-ui-flow.md).

