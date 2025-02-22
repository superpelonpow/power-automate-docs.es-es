---
title: Supervisión y administración de procesos de flujo de trabajo con Power Apps | Microsoft Docs
ms.custom: ''
ms.date: 05/06/2018
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
ms.assetid: a987a803-4674-4eb0-87de-caefa003b1eb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e4042b71e6913f1008f506697fa39291b3cbf59a
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298273"
---
# <a name="monitor-and-manage-workflow-processes"></a>Supervisión y administración de procesos de flujo de trabajo


Para supervisar y administrar los procesos, debe localizar el proceso, evaluar el estado y realizar las acciones necesarias para solucionar los problemas.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Supervisar flujos de trabajo en segundo plano  
 Los flujos de trabajo en segundo plano generan registros del trabajo del sistema para realizar un seguimiento de su estado. Puede obtener acceso a la información acerca de estos trabajos del sistema en varios lugares dentro de la aplicación:  
  
 **[Configuración](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Trabajos del sistema**  
 Se incluyen todos los tipos de trabajos del sistema. Necesitará filtrar los registros a aquellos donde **Tipo de trabajo del sistema** sea **Flujo de trabajo**.  
  
 **Desde el proceso de flujo de trabajo**  
 Abra la definición de flujo de trabajo en segundo plano y vaya a la pestaña **Sesión de proceso**. Esto le mostrará solo los trabajos del sistema de este flujo de trabajo en segundo plano.  
  
 **Desde el registro**  
 Puede modificar el formulario de la entidad para que la navegación incluya la relación **Procesos en segundo plano**. Esta acción le mostrará todos los trabajos del sistema que se han iniciado en el contexto del registro.  
  
> [!NOTE]
>  Si en un trabajo del sistema asincrónico (flujo de trabajo) se produce un error varias veces consecutivas, el sistema empieza a posponer la ejecución de ese trabajo en intervalos de tiempo cada vez más prolongados para que el administrador o el creador de la aplicación pueda investigar y resolver el problema. Cuando el trabajo vuelva a ser correcto, la ejecución se reanudará con normalidad.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Acciones para flujos de trabajo en segundo plano en ejecución  
 Mientras un flujo de trabajo en segundo plano se ejecuta, tiene opciones para **Cancelar**, **Pausa** o **Posponer** el flujo de trabajo. Si anteriormente pausó un flujo de trabajo, puede reanudarlo con **Reanudar**.  
  
<a name="BKMK_MonitorSyncWorkflows"></a>   
## <a name="monitoring-real-time-workflows-and-actions"></a>Controlar los flujos de trabajo y acciones en tiempo real  
 Los flujos de trabajo y las acciones en tiempo real no usan los registros del trabajo del sistema porque se producen inmediatamente. Los errores que se produzcan se mostrarán el usuario en la aplicación con el encabezado **Error de proceso empresarial**.  
  
 No hay ningún registro para las operaciones que se realizan correctamente. Puede habilitar el registro de errores activando la opción **Mantiene registros para las tareas del flujo de trabajo que encontraron errores** en el área **Retención de registro del flujo de trabajo** en la parte inferior de la ficha **Administración** del proceso.  
  
 Para ver el registro de errores de un proceso específico, abra la definición del flujo de trabajo o la acción en tiempo real y vaya a la ficha **Sesión de proceso**. Esta opción solo le mostrará los errores registrados del proceso.  
  
 Si desea una vista de todos los errores de cualquier proceso, vaya a **Búsqueda avanzada** y cree una vista que muestre los errores en la entidad de la sesión de proceso.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-workflow-processes"></a>Estado de los procesos de flujo de trabajo  
 Al ver una lista de los procesos de flujo de trabajo, cualquier proceso individual puede tener uno de los siguientes valores de **Estado** y **Razón para el estado**:  
  
|Estado|Razón para el estado|  
|-----------|-------------------|  
|Preparado|Esperando recursos|  
|Suspendida|En espera|  
|Bloqueado|En curso<br /><br /> Pausando<br /><br /> Cancelando|  
|Completada|Correcta<br /><br /> Con errores<br /><br /> Cancelada|  

## <a name="deleting-process-log-records"></a>Eliminación de entradas de registro de proceso

Si en la organización se usan flujos de trabajo en segundo plano o flujos de proceso de negocio que se ejecutan con frecuencia, la cantidad de entradas de registro de proceso puede ser lo suficientemente elevada como para causar problemas de rendimiento, además de consumir grandes cantidades de almacenamiento. Para borrar las entradas de registro de proceso que no se han podido quitar mediante uno de los trabajos estándar de eliminación de registros en masa, puede usar la característica de eliminación en masa de trabajos del sistema para crear un trabajo personalizado de eliminación de registros en masa.

1. Vaya a **Configuración** > **Administración de datos** > **Eliminación de registros en masa**.
2. En el área **Eliminación de registros en masa**. haga clic en **Nuevo**. 
3. En el página de inicio del **Asistente para eliminación en masa**, haga clic en **Siguiente**.
4. En la lista **Buscar**, seleccione **Trabajos del sistema**.
5. Las condiciones siguientes se usan para crear un trabajo de eliminación de registros en masa para eliminar entradas de registro de procesos. 
 - **Tipo de trabajo del sistema Es igual a Flujo de trabajo**. Esto selecciona como destino los registros de flujo de trabajo. 
 - **Estado Es igual a Completado**. Solo los flujos de trabajo completados son válidos para ejecutar el trabajo.
 - **Razón para el estado Es igual a Correcto**. Se eliminan los trabajos correctos, cancelados e incorrectos.
 - **Completado el Más antiguo de X días 30**. Use el campo Completado el solo para eliminar entradas de registro de proceso de flujo de trabajo que tengan más de 30 días.
 ![custom-bulk-record-deletion.png](media/custom-bulk-record-deletion.png)
6. Haga clic en **Siguiente**.
7. Establezca la frecuencia con la que se va a ejecutar el trabajo de eliminación en masa. Puede programar el trabajo para que se ejecute a intervalos establecidos o crear un trabajo de eliminación en masa de un solo uso [mediante la opción Inmediatamente](#using-the-immediately-option). En este ejemplo, se establece un trabajo periódico para que se ejecute el 21 de mayo de 2018 y cada 30 días a partir de entonces. 
![Opciones de eliminación de registros en masa](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Uso de la opción Inmediatamente

Observe que tiene la posibilidad de realizar una eliminación en masa sincrónica inmediata de los registros si selecciona la opción **Inmediatamente**. Esta eliminación se realiza con la ejecución directa de SQL Server en lugar de pasar cada registro a través de la canalización de eventos de eliminación, lo que puede reducir el impacto en el rendimiento del sistema. Es una buena opción si quiere limpiar con rapidez los registros de flujo de trabajo extra en lugar de que el trabajo de eliminación en masa espere en la cola asincrónica para el procesamiento. 

La opción **Inmediatamente** está habilitada cuando se cumplen las condiciones siguientes: 
- El trabajo de eliminación en masa es para la entidad Trabajos del sistema.
- Los criterios de búsqueda tienen la condición Tipo de trabajo del sistema es igual a flujo de trabajo. 
- El usuario que crea el trabajo de eliminación en masa tiene profundidad global para el privilegio de eliminación en la entidad AsyncOperation. El rol de seguridad de administrador del sistema tiene este privilegio.  

La eliminación en masa sincrónica solo eliminará los registros AsyncOperation con el estado Completado. En cada invocación se procesa un máximo de un millón de registros. Tendrá que ejecutar el trabajo varias veces si en el entorno hay más de un millón de registros para quitar.  
  
## <a name="next-steps"></a>Pasos siguientes   
 [Procedimientos recomendados para los procesos de flujo de trabajo](best-practices-workflow-processes.md) <br />

