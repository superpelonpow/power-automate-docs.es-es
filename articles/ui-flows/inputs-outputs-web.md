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
ms.date: 03/30/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8ea8301c1b50502995cc5081d960df44859458eb
ms.sourcegitcommit: bba5bd4ae3879b6bf1521d8ed636374fe09709e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "3298713"
---
# <a name="use-inputs-and-outputs-in-web-ui-flows"></a>Uso de entradas y salidas en los flujos de la interfaz de usuario web

Puede definir entradas para pasar a las aplicaciones automatizadas durante la reproducción. También puede pasar la *salida* de las aplicaciones automatizadas al flujo.

## <a name="define-inputs-for-a-web-ui-flow"></a>Definición de entradas para un flujo de interfaz de usuario web

Las entradas de un flujo de interfaz de usuario permiten pasar información de un origen externo, como una base de datos u otro flujo de interfaz de usuario, al software heredado de destino que se automatizará.

Cualquier variable que se use (que se lea) antes de la inicialización (que habitualmente se hace a través de los comandos **store**) se tratará automáticamente como una variable de entrada y se mostrará en la tarjeta de acción **Ejecutar flujo de interfaz de usuario para la Web**.

Puede usar variables a través de la interpolación de cadenas; por ejemplo, cambie el campo de destino del comando click a "id=\${elementId}". O cambie el campo del valor del comando type a "\${inputText}".

El comando **establecer tamaño de ventana** y el comando **tipo** de las capturas de pantalla siguientes usan variables sin inicializar \${Width}, \${Height} y \${search}. Estas variables se convertirán en valores de entrada.

![Establecimiento del tipo y el tamaño de la ventana](../media/inputs-outputs-web/set-window-size.png "Establecimiento del tipo y el tamaño de la ventana")

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

