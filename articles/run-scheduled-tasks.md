---
title: Ejecución de flujos de forma programada | Microsoft Docs
description: Automatice tareas repetitivas mediante la ejecución de flujos de forma programada, por ejemplo cada día o cada hora.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/14/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4970554dee8e031a746cf604e2a628f41056b46c
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193689"
---
# <a name="run-flows-on-a-schedule"></a>Ejecución de flujos de forma programada

Cree un flujo que lleva a cabo una o varias tareas (como enviar un informe por correo electrónico):

* una vez al día, a la hora o al minuto
* en una fecha que especifique
* después del número de días, horas o minutos que especifique

## <a name="create-a-recurring-flow"></a>Creación de un flujo repetitivo
1. Inicie sesión en [Power Automate](https://flow.microsoft.com) y seleccione **Mis flujos** en la barra de navegación superior.
   
    ![Opción Mis flujos](./media/run-scheduled-tasks/create-flow.png)
2. Seleccione **Crear desde cero**.
   
    ![Crear un flujo desde cero](./media/run-scheduled-tasks/create-from-blank.png)
3. En el cuadro **Buscar todos los conectores y desencadenadores** , escriba **Periodicidad** y, después, seleccione **Programación - Periodicidad**.
   
    ![Buscar el desencadenador de periodicidad](./media/run-scheduled-tasks/select-recurrence.png)
4. En el cuadro de diálogo **Frecuencia**, especifique la frecuencia con que desea que se ejecute el flujo.
   
    Por ejemplo, especifique **2** en **Intervalo** y **Semana** en **Frecuencia** si desea que el flujo se ejecute cada dos semanas.
   
    ![Especificar periodicidad](./media/run-scheduled-tasks/specify-recurrence.png)

## <a name="specify-advanced-options"></a>Especificación de opciones avanzadas
1. Siga los pasos descritos en la sección anterior y, después, seleccione **Mostrar opciones avanzadas**.
   
    **Nota:** Estas opciones cambian en función de los valores de los campos **Intervalo** y **Frecuencia**. Si la pantalla no es la misma que la siguiente, asegúrese de los valores de **Intervalo** y **Frecuencia** son los mismos valores que se muestran en el gráfico.
2. Seleccione una **zona horaria** para especificar si la **hora de inicio** refleja una zona horaria local, hora universal coordinada (UTC), etc.
3. Especifique un **hora de inicio** en este formato:
   <br>AAAA-MM-DDTHH:MM:SSZ
4. Si especificó **Día** en **Frecuencia**, indique la hora del día en que se debe ejecutar el flujo.
5. Si especificó **Semana** en **Frecuencia**, especifique el día, o días, de la semana en que se debe ejecutar el flujo, así como la hora, u horas, del día en que debe ejecutarse.
   
    Por ejemplo, configure las opciones tal como se muestra para iniciar un flujo después de mediodía (hora del Pacífico) el lunes, 1 de enero de 2018, y ejecutarlo cada dos semanas los martes a las 5:30 p.m. (hora del Pacífico).
   
    ![Especificación de opciones avanzadas](./media/run-scheduled-tasks/advanced-options.png)
6. Agregue la acción, o acciones, que desea que realice el flujo, como se describe en [Create a flow in Microsoft Flow](get-started-logic-flow.md) (Crear un flujo en Microsoft Flow).

## <a name="delay-a-flow"></a>Retrasar un flujo
1. Inicie sesión en [Power Automate](https://flow.microsoft.com) y seleccione **Mis flujos** en la barra de navegación superior.
   
    ![Crear un flujo desde cero](./media/run-scheduled-tasks/create-flow.png)
2. Seleccione **Crear desde cero**.
   
    ![Crear un flujo desde cero](./media/run-scheduled-tasks/create-from-blank.png)
3. Especifique un evento como se describe en [Crear un flujo desde cero](get-started-logic-flow.md).
4. Seleccione **Nuevo paso** y, luego, **Agregar una acción**.
   
    ![Opción para agregar una acción a un flujo](./media/run-scheduled-tasks/add-action.png)
5. En la lista de acciones, realice cualquiera de estas acciones:
   
   * Seleccione **Retraso**, especifique un **recuento**y especifique un **unidad** de tiempo, como hora, minuto o segundo.
   * Seleccione **Retraso hasta** y, después, especifique una fecha con este formato.<br>AAAA-MM-DDTHH:MM:SSZ
     
     ![Agregar un retraso](./media/run-scheduled-tasks/add-delay.png)
     ![Especificar un retraso en unidades de tiempo](./media/run-scheduled-tasks/delay.png)
     ![Especificar retraso hasta](./media/run-scheduled-tasks/delay-until.png)

## <a name="learn-more"></a>Más información

Obtenga más información sobre las [opciones avanzadas](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) y cómo configurarlas.

