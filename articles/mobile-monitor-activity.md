---
title: Supervisión de la actividad desde un teléfono | Microsoft Docs
description: Vea el número de veces que cada flujo se ha ejecutado correctamente o con errores, cuándo se ha producido cada ejecución y cuánto tiempo tardó
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
ms.openlocfilehash: 2c02b50289988a6462ed33df92350e9e4286b785
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74376825"
---
# <a name="monitor-activity-in-power-automate-from-your-phone"></a>Supervisión de la actividad en Power Automate desde un teléfono
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Vea el número de veces que cada flujo se ha ejecutado correctamente o con errores hoy, ayer y en los días anteriores. Explore los detalles relativos a cada ejecución, como cuándo se ejecutó, cuánto tardó en realizarse cada paso y, si se produjo un error, los motivos para ello.

**Requisitos previos**

<iframe width="560" height="315" src="https://www.youtube.com/embed/vZuYZ64K3tI?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

* Instale la aplicación móvil de Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows) en un [dispositivo compatible](getting-started.md#use-the-mobile-app). Los elementos gráficos de este tema reflejan la versión para iPhone de la aplicación, pero los elementos gráficos en las versiones para Android y Windows Phone son similares.
* Si todavía no tiene un flujo, cree uno en [el sitio web de Power Automate](https://flow.microsoft.com/). Para facilitar la realización de pruebas, utilice uno que pueda desencadenar, en lugar de tener que esperar a un evento externo.

El flujo de este tutorial se ejecuta cuando se recibe correo de una dirección específica:

![Desencadenar flujo al recibir correo de una dirección concreta](./media/mobile-monitor-activity/create-trigger.png)

Puede configurar un flujo con su dirección de correo electrónico personal para las pruebas y otra (por ejemplo, la del administrador) cuando el flujo esté listo para su uso real.

Cuando se ejecuta el flujo, envía una notificación push personalizada, con esta sintaxis, a su teléfono:

![Enviar notificaciones push](./media/mobile-monitor-activity/create-event.png)

**Nota:** también puede [administrar sus flujos](mobile-manage-flows.md) desde la aplicación móvil.

## <a name="display-a-summary-of-activity"></a>Visualización de un resumen de la actividad
<iframe width="560" height="315" src="https://www.youtube.com/embed/nVCGJamOw6s?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Si el flujo no se ha ejecutado antes, desencadene una ejecución para generar datos.
   
    Los datos pueden tardar un tiempo en aparecer en la aplicación.
2. Abra la aplicación móvil, que muestra la pestaña **Activity** (Actividad) de manera predeterminada.
   
    Esta pestaña organiza los datos por día, empezando por los de hoy.
   
    ![Actividad organizada por día](./media/mobile-monitor-activity/activity-day2.png)
   
    Cada entrada muestra el nombre de un flujo con iconos que corresponden a sus eventos desencadenantes y acciones.
   
    ![Nombre e iconos de cada flujo.](./media/mobile-monitor-activity/activity-flow-name.png)
   
    Si al menos una ejecución de un flujo se ha realizado correctamente en un día, una entrada muestra el número de veces que se ha ejecutado correctamente y la última hora en que se ha ejecutado. Una entrada diferente muestra información similar si se ha producido un error en un flujo.
   
    ![Resumen de ejecuciones correctas o con errores](./media/mobile-monitor-activity/activity-summary.png)
   
    Si un flujo envía una notificación push, el texto de la notificación más reciente aparece en la parte inferior de la entrada de ejecuciones con resultado satisfactorio.
   
    ![Ejemplo de notificación push](./media/mobile-monitor-activity/activity-notification.png)
3. Si se han enviado varias notificaciones push en un día, deslice el dedo hacia la izquierda para ver las notificaciones de hasta tres ejecuciones anteriores. Si han enviado más de cuatro notificaciones en un día, deslice el dedo hacia izquierda hasta que aparezca **See more** (Ver más) y, luego, púlselo para ver una lista de todas las notificaciones.
   
    ![Ejemplo de notificación push](./media/mobile-monitor-activity/activity-notification-list.png)
4. Pulse en **Back** (Atrás) para volver al resumen de la actividad.
5. Para filtrar el resumen de la actividad, pulse el icono en la esquina superior derecha.
   
    Puede mostrar todas las entradas, solo entradas con error o solo las entradas que incluyen notificaciones push.
   
    ![Mostrar todas las ejecuciones,: solo los errores o solo las notificaciones](./media/mobile-monitor-activity/activity-filter.png)

## <a name="show-details-of-a-run"></a>Presentación de los detalles de una ejecución
1. En el resumen de la actividad, pulse una entrada para mostrar los detalles de la última ejecución.
   
     Todos los eventos y acciones aparecen con un icono que indica si el evento o la acción se ejecutó correctamente, o no. Si se ejecutó correctamente, también aparece la cantidad de tiempo que tardó (en segundos).
   
    ![Detalles de una ejecución](./media/mobile-monitor-activity/activity-icons.png)
2. En la parte inferior de la pantalla, pulse **See previous runs** (Ver ejecuciones anteriores) para enumerar todas las ejecuciones del flujo y, luego, pulse una ejecución para mostrar sus detalles.
   
    ![Historial ejecuciones satisfactorias o con errores](./media/mobile-monitor-activity/history-mixed.png)

