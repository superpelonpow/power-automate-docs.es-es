---
title: Administración de flujos desde un teléfono | Microsoft Docs
description: Vea una lista de sus flujos, habilítelos o deshabilítelos y vea todos los eventos y acciones del flujo, y ejecute el historial
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/11/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ce9a943f50ef5c8cc69e5dbf8fde796a75e4cdf9
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296755"
---
# <a name="manage-flows-in-power-automate-from-your-phone"></a>Administración de flujos en Power Automate desde un teléfono

Vea una lista de todos los flujos que ha creado y habilite o deshabilite cada uno de ellos, vea sus eventos y acciones, y explore su historial de ejecución.

**Requisitos previos**

* Instale la aplicación móvil Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows) en un [dispositivo compatible](getting-started.md#use-the-mobile-app). Los elementos gráficos de este tema reflejan la versión de iPhone de la aplicación, pero los elementos gráficos en las versiones Android y Windows Phone son similares.
* Si aún no tiene un flujo, cree uno en [el sitio web de Power Automate](https://flow.microsoft.com/). Para facilitar la realización de pruebas, utilice uno que pueda desencadenar, en lugar de tener que esperar a un evento externo.

El flujo de este tutorial se ejecuta cuando se recibe correo de una dirección específica:

![Desencadenar flujo al recibir correo de una dirección concreta](./media/mobile-manage-flows/create-trigger.png)

Puede configurar un flujo con su dirección de correo electrónico personal para las pruebas y otra (por ejemplo, la del administrador) cuando el flujo esté listo para su uso real.

Cuando se ejecuta el flujo, envía una notificación push personalizada, con esta sintaxis, a su teléfono:

![Enviar mensaje Slack](./media/mobile-manage-flows/create-event.png)

**Nota**: también puede [supervisar la actividad del flujo](mobile-monitor-activity.md) desde la aplicación móvil.

## <a name="manage-a-flow"></a>Administración de un flujo
1. Abra la aplicación móvil y pulse **My flows** (Mis flujos) en la parte inferior de la pantalla para enumerar todos los flujos.
   
    Cada entrada muestra el nombre del flujo, iconos de sus eventos y acciones, la hora en que se ejecutó por última vez y un icono que indica si la última ejecución fue satisfactoria.
   
    ![Lista de flujos](./media/mobile-manage-flows/flow-list.png)
2. Pulse un flujo para mostrar las opciones que puede usar para administrarlo.
   
    ![Opciones para administrar un flujo](./media/mobile-manage-flows/flow-details.png)
3. Pulse **Enable flow** (Habilitar flujo) para habilitar o deshabilitar el flujo.
4. Pulse **See flow** (Ver flujo) para mostrar los eventos y acciones de dicho flujo, pulse en cada evento o una acción para expandirlos y, luego, pulse **Back** (Atrás).
   
    ![Eventos y acciones de un flujo](./media/mobile-manage-flows/flow-event-action.png)
5. Pulse **Run history** (Historial de ejecuciones) para mostrar las ejecuciones satisfactorias, los errores, o ambos, del flujo.
   
    ![Lista de ejecuciones](./media/mobile-manage-flows/history-mixed.png)
6. Pulse una ejecución para mostrar si todos los eventos y acciones se han ejecutado correctamente y, en caso afirmativo, cuánto tiempo (en segundos) han tardado en ejecutarse.
   
    ![Detalles de ejecución](./media/mobile-manage-flows/flow-run.png)

