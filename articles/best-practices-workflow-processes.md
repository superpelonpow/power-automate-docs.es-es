---
title: Procedimientos recomendados para la administración de procesos de flujo de trabajo | Microsoft Docs
description: Descripción de los métodos recomendados para usar flujos de trabajo
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
author: Mattp123
ms.assetid: 34e34c33-003a-494f-858c-3d34aacb308c
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f3d02ca92b94752a8bbe6e3458fa8639de917dd8
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194011"
---
# <a name="best-practices-for-workflow-processes"></a>Procedimientos recomendados para los procesos de flujo de trabajo


Este tema contiene los procedimientos recomendados para la creación y administración de procesos de flujo de trabajo.  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>Evitar los bucles infinitos  
 Es posible crear lógica en un flujo de trabajo que inicie un bucle infinito, lo que consume recursos del servidor y afecta al rendimiento. La situación típica donde se podría producir un bucle infinito es si tiene un flujo de trabajo configurado para que se inicie al actualizar un atributo y, después, actualiza ese atributo en la lógica del flujo de trabajo. La acción de actualización desencadena el mismo flujo de trabajo que actualiza el registro y lo hace forma repetida.  
  
 Los flujos de trabajo que cree incluyen lógica para detectar y detener los bucles infinitos. Si un proceso de flujo de trabajo se ejecuta más de un número determinado de veces en un registro específico en un breve período de tiempo, se produce el siguiente error en el proceso: **Esta tarea de flujo de trabajo se ha cancelado porque el flujo de trabajo que la ha iniciado incluía un bucle infinito. Corrija la lógica del flujo de trabajo e inténtelo de nuevo**. El límite de veces es 16.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-workflow-templates"></a>Uso de plantillas de flujo de trabajo  
 Si tiene flujos de trabajo que son similares y tiene pensado crear más que siguen el mismo patrón, guarde el flujo de trabajo como una plantilla de flujo de trabajo. De este modo, la próxima vez que tenga que crear un flujo de trabajo similar, créelo mediante la plantilla y evite escribir todas las condiciones y acciones desde cero.  
  
 En el cuadro de diálogo **Crear proceso**, elija **Proceso nuevo a partir de una plantilla existente (seleccione desde la lista)** .  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>Uso de flujos de trabajo secundarios  
 Si aplica la misma lógica en otros flujos de trabajo o en ramas condicionales, defina esa lógica como un flujo de trabajo secundario para que no tenga que replicarla de forma manual en todos los flujos de trabajo o ramas condicionales. Esto facilita el mantenimiento de los flujos de trabajo. En lugar de examinar muchos flujos de trabajo que puedan aplicar la misma lógica, solo tendrá que actualizar uno.  
  
## <a name="automatically-delete-completed-workflow-jobs"></a>Eliminación automática de las tareas de flujo de trabajo completadas
Para los flujos de trabajo (asincrónicos) en segundo plano, se recomienda seleccionar la opción **Eliminar automáticamente las tareas de flujo de trabajo completadas (para ahorrar espacio en disco)** en la definición de flujo de trabajo. Al activar esta casilla se permite que el sistema elimine los registros de flujo de trabajo para las ejecuciones correctas para ahorrar espacio. Tenga en cuenta que los registros de las ejecuciones de flujo de trabajo con errores siempre se guardarán para la solución de problemas.  

![Retención de tareas de flujo de trabajo](media/workflow-job-retention.png)

<a name="BKMK_AutoDeleteCompletedWorkflowJobs"></a>   
## <a name="keep-logs-for-workflow-jobs-that-encountered-errors"></a>Mantiene registros para las tareas de flujo de trabajo que encontraron errores  
Para los flujos de trabajo que no se ejecutan en segundo plano (sincrónicos), se recomienda seleccionar la opción **Mantiene registros para las tareas de flujo de trabajo que encontraron errores** en la definición de flujo de trabajo. Al seleccionar esta opción, se permite que se guarden los registros de las ejecuciones de flujo de trabajo con errores para la solución de problemas. Los registros de las ejecuciones de flujo de trabajo sincrónicas correctas siempre se eliminarán para ahorrar espacio.   

![Conservación de registros para la opción de flujos de trabajo con errores](media/keep-logs-for-workflows.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>Límite del número de flujos de trabajo que actualizan la misma entidad
La ejecución de más de un flujo de trabajo que actualiza la misma entidad puede causar problemas de bloqueo de recursos. Imagine varios flujos de trabajo en ejecución donde todas las actualizaciones de oportunidad desencadenan una actualización de la cuenta asociada. Si varias instancias de estos flujos de trabajo ejecutan e intentan actualizar el mismo registro de cuenta al mismo tiempo, pueden provocar problemas de bloqueo de recursos. Se producen errores de flujo de trabajo y se registra un mensaje de error, como **Tiempo de espera de SQL: No se puede obtener el bloqueo en el recurso _nombre de recurso_** . 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>Uso de Notas para realizar el seguimiento de los cambios  
 Cuando modifique los flujos de trabajo, debe usar la pestaña Notas y escribir lo que ha hecho y por qué. Esto permite que otro usuario entienda los cambios realizados.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Información general de los procesos de flujo de trabajo](workflow-processes.md)   
 [Configuración de procesos de flujo de trabajo](configure-workflow-steps.md)   
 [Supervisión y administración de procesos de flujo de trabajo](monitor-manage-processes.md)
   
