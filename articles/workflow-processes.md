---
title: Flujos de trabajo clásicos de Common Data Service | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2019
ms.reviewer: matp
ms.service: flow
ms.topic: article
ms.assetid: 1f3c9780-26ad-49ec-a3fb-fc226def19c5
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 53bc2b24da55c8700412b527c7f27934e5515bc4
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298339"
---
# <a name="classic-common-data-service-workflows"></a>Flujos de trabajo clásicos de Common Data Service 


Los flujos de trabajo automatizan los procesos de negocio sin una interfaz de usuario. Normalmente, los usuarios utilizan los procesos de flujo de trabajo para iniciar la automatización que no requiere ninguna interacción del usuario.

> [!IMPORTANT]
> Use flujos en lugar de flujos de trabajo clásicos para automatizar los procesos empresariales. Más información: [Reemplazar flujos de trabajo de Common Data Service clásicos con flujos](replace-workflows-with-flows.md)  
  
 Cada proceso de flujo de trabajo está asociado con una sola entidad. Al configurar los flujos de trabajo hay cuatro áreas principales que tener en cuenta:  
  
-   ¿Cuándo comenzarlos?  
  
-   ¿Deben ejecutarse como un flujo de trabajo en tiempo real o un flujo de trabajo en segundo plano?  
  
-   ¿Qué acciones deben realizar?  
  
-   ¿En qué condiciones deben llevarse a cabo las acciones?  
  
 Este tema introduce cómo buscar procesos de flujo de trabajo, y describe cuándo iniciarlos y si deben ejecutarse en tiempo real o en segundo plano. Para obtener más información acerca de las acciones que deben realizar y las condiciones, consulte [Configurar procesos de flujo de trabajo](configure-workflow-steps.md).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>¿Dónde se personalizan los procesos de flujo de trabajo?  
 Para ver los flujos de trabajo de su organización abra el nodo **Procesos** en la **solución predeterminada** y filtre por los procesos con la **Categoría** establecida en **Flujo de trabajo**.  
  
 ![Procesos filtrados por flujo de trabajo en Dynamics 365](media/workflow-processes-filtered.PNG "Procesos filtrados por flujo de trabajo en Dynamics 365")  
  
 En función de cómo se compile la aplicación, los usuarios pueden crear o modificar sus flujos de trabajo en ella. 
 
Los desarrolladores pueden crear flujos de trabajo con la información del [Manual del desarrollador de Common Data Service](https://docs.microsoft.com/powerapps/developer/common-data-service/workflow/workflow-extensions) y las soluciones que adquiera pueden incluir flujos de trabajo que se puedan modificar.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Propiedades de flujo de trabajo  
 En el explorador de soluciones, seleccione **Procesos** y haga clic en **Nuevo**.  
  
 Al crear un flujo de trabajo, el diálogo **Crear proceso** requiere que establezca tres propiedades que todos los procesos tienen:  
  
 ![Creación de un flujo de trabajo en Dynamics 365](media/create-workflow.PNG "Creación de un flujo de trabajo en Dynamics 365")  
  
 **Nombre del proceso**  
 No es necesario que el nombre del proceso de flujo de trabajo sea único, pero si espera tener una gran cantidad de flujos de trabajo, es posible que quiera usar una convención de nomenclatura para diferenciar claramente los procesos. Quizás desee aplicar prefijos estándar al nombre del flujo de trabajo. El prefijo puede describir la función del flujo de trabajo o del departamento de la empresa. Esto le ayudará a agrupar elementos similares en la lista de flujos de trabajo.  
  
 **Categoría**  
 Esta propiedad establece que se trata de un proceso de flujo de trabajo.  
  
 **Entidad**  
 Cada proceso de flujo de trabajo debe establecerse en una entidad única. No puede cambiar la entidad una vez creado el proceso de flujo de trabajo.  
  
 **Ejecutar este flujo de trabajo en segundo plano (recomendado)**  
 Esta opción aparece cuando se selecciona Flujo de trabajo como categoría. Determina si el flujo de trabajo se produce en tiempo real o en segundo plano. Los flujos de trabajo en tiempo real se ejecutan de inmediato (sincrónicamente) y los flujos de trabajo en segundo plano se ejecutan asincrónicamente. Las opciones de configuración disponibles dependen de lo que elija aquí. Los flujos de trabajo en segundo plano permiten condiciones de espera que no están disponibles para los flujos de trabajo en tiempo real. Aunque no use las condiciones de espera, posteriormente puede convertir los flujos de trabajo en segundo plano en flujos de trabajo en tiempo real y los flujos de trabajo en tiempo real en flujos de trabajo en segundo plano. Para obtener más información acerca de las condiciones de espera, consulte [Configurar las condiciones de las acciones de flujo de trabajo](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions).  
  
 También tiene la opción **Tipo** para especificar si desea crear un nuevo flujo de trabajo desde cero o comenzar a partir de una plantilla existente. Si elige **Proceso nuevo a partir de una plantilla existente (seleccione desde la lista)** puede elegir entre los procesos de flujo de trabajo disponibles que se guardaron anteriormente como una plantilla de proceso.  
  
 Después de crear el flujo de trabajo, o de modificar uno existente, tendrá las propiedades adicionales siguientes:  
  
 ![Pestaña General de un flujo de trabajo](media/create-workflow-general-tab.PNG "Pestaña General de un flujo de trabajo")  
  
 **Activar como**  
 Puede elegir **Plantilla de procesos** para crear un punto de partida avanzado para otras plantillas. Si selecciona esta opción, el flujo de trabajo no se aplicará después de activarlo, pero en su lugar, estará disponible seleccionar en el diálogo **Crear proceso** si selecciona **Tipo**: **Proceso nuevo a partir de una plantilla existente (seleccione desde la lista)**  
  
 Las plantillas de proceso son convenientes cuando tiene varios procesos similares de flujo de trabajo y desea definirlos sin duplicar la misma lógica.  
  
> [!NOTE]
>  Editar una plantilla de procesos no cambia los comportamientos de otras procesos de flujo de trabajo que ha creado previamente usando dicha plantilla. Un nuevo flujo de trabajo creado con una plantilla es una copia del contenido de la plantilla.  
  
 **Disponible para ejecutarse**  
 Esta sección contiene las opciones que describen la disponibilidad del flujo de trabajo para su ejecución.  
  
 **Ejecutar este flujo de trabajo en segundo plano (recomendado)**  
 Esta casilla refleja la opción seleccionada al crear el flujo de trabajo. Esta opción está deshabilitada, pero es posible cambiarla en el menú **Acciones** eligiendo **Convertir en flujo de trabajo en tiempo real** o **Convertir en flujo de trabajo en segundo plano**.  
  
 **Como un proceso a petición**  
 Seleccione esta opción si desea permitir que los usuarios ejecuten este flujo de trabajo desde el comando **Ejecutar flujo de trabajo**.  
  
 **Como un proceso secundario**  
 Seleccione esta opción si desea permitir que el flujo de trabajo esté disponible para iniciarse desde otro flujo de trabajo.  
  
 **Retención de la tarea del flujo de trabajo**  
 Esta sección incluye una opción para eliminar un flujo de trabajo después de que se haya completado la ejecución de flujos de trabajo.  
  
 **Eliminar automáticamente las tareas de flujo de trabajo completadas (para ahorrar espacio en disco)**  
 Seleccione esta opción si desea que se elimine automáticamente una tarea de flujo de trabajo completada.  
  
> [!NOTE]
>  Las tareas de flujo de trabajo no se eliminan de inmediato al finalizar, sino poco después, con un proceso por lotes.  
  
 **Ámbito**  
 Para entidades propiedad del usuario, las opciones son **Organización**, **Principal: Unidades de negocio secundarias**, **Unidad de negocio** o **Usuario**. Para entidades que pertenecen a la organización, la única opción es **Organización**.  
  
 Si el ámbito es **Organización**, la lógica del flujo de trabajo se puede aplicar a cualquier registro de la organización. De lo contrario, el flujo de trabajo solo se puede aplicar a un subconjunto de registros dentro de dicho ámbito.  
  
> [!NOTE]
>  El valor de ámbito predeterminado es **Usuario**. Asegúrese de comprobar que el valor de ámbito sea adecuado antes de activar el flujo de trabajo.  
  
 **Iniciar al**  
 Use las opciones de esta sección para especificar cuándo un flujo de trabajo debe iniciarse automáticamente. Puede configurar un flujo de trabajo en tiempo real para ejecutarse antes de determinados eventos. Se trata de una característica muy eficaz porque el flujo de trabajo puede detener la acción antes de que se produzca. Más información: [Usar flujos de trabajo en tiempo real](configure-workflow-steps.md#BKMK_SynchronousWorkflows). Las opciones son:  
  
- **Registro creado**  
  
- **Cambios de estado de registro**  
  
- **Registro asignado**  
  
- **Cambio en los campos de registro**  
  
- **Registro eliminado**  
  
> [!NOTE]
>  Tenga en cuenta que las acciones y las condiciones que se definen para el flujo de trabajo no se tienen en cuenta al ejecutar el flujo de trabajo. Por ejemplo, si define un flujo de trabajo para actualizar el registro, esta acción no la puede realizar un flujo de trabajo en tiempo real antes de crear el registro. Un registro que no existe no se puede actualizar. De forma similar, un flujo de trabajo en segundo plano no puede actualizar un registro que se ha eliminado, aunque podría definir esta acción para el flujo de trabajo. Si configura un flujo de trabajo para realizar una acción que no se puede realizar, se producirá un error y el flujo de trabajo completo generará un error.  
  
 **Ejecutar como**  
 Esta opción solo está disponible si deseleccionó la opción **Ejecutar este flujo de trabajo en segundo plano (recomendado)** al crear el flujo de trabajo o si convirtió posteriormente un flujo de trabajo en segundo plano en un flujo de trabajo en tiempo real.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>Contexto de seguridad de los procesos de flujo de trabajo  
 Cuando un flujo de trabajo en segundo plano se configura como un proceso a petición, y un usuario lo inicia mediante el comando **Ejecutar flujo de trabajo**, las acciones que el flujo de trabajo puede realizar se limitan a las que el usuario podía realizar en función de los privilegios y los niveles de acceso definidos por los roles de seguridad establecidos para su cuenta de usuario.  
  
 Cuando un flujo de trabajo en segundo plano se inicia en función de un evento, el flujo de trabajo opera en el contexto del usuario que es el propietario, normalmente la persona que creó el flujo de trabajo.  
  
 Para flujos de trabajo en tiempo real tiene la opción **Ejecutar como** y puede elegir si el flujo de trabajo debe aplicar el contexto de seguridad del propietario del flujo de trabajo o del usuario que realizó cambios en el registro. Si el flujo de trabajo incluye acciones que todos los usuarios no podrían realizar según las restricciones de seguridad, debe optar ejecutar el flujo de trabajo como propietario del flujo de trabajo.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Activar un flujo de trabajo  
 Los flujos de trabajo pueden editarse solo mientras están desactivados. Para que un flujo de trabajo pueda usarse manualmente o aplicarse debido a eventos, debe activarse. Antes de que un flujo de trabajo se pueda activar debe tener al menos un paso. Para obtener información sobre cómo configurar los pasos, consulte [Configurar procesos de flujo de trabajo](configure-workflow-steps.md)  
  
 Un flujo de trabajo solo lo puede activar o desactivar el propietario del flujo de trabajo o alguien con el privilegio **Actuar en nombre de otro usuario** como el administrador del sistema.  La razón de esto es que un usuario malintencionada podría modificar el flujo de trabajo de otro usuario sin que este estuviese al corriente del cambio. Puede volver a asignar un flujo de trabajo cambiando el propietario. Este campo está en la pestaña **Administración**. Si no es el administrador del sistema y es necesario editar un flujo de trabajo que pertenezca a otro usuario, necesita que lo desactiven y se lo asignen. Una vez que haya terminado de modificar el flujo de trabajo, puede volver a asignárselo para que pueda activarlo.  
  
 Los flujos de trabajo en tiempo real requieren que el usuario tenga el privilegio **Activar procesos en tiempo real**. Debido a que los flujos de trabajo en tiempo real tienen un mayor riesgo de afectar al rendimiento del sistema, solo los usuarios que puedan evaluar el riesgo potencial deben obtener este privilegio.  
  
 Los flujos de trabajo se guardan cuando se activan, por lo que no es necesario guardarlos antes de activarlos.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Configuración de procesos de flujo de trabajo](configure-workflow-steps.md)  <br/>
[Adición de un flujo de trabajo a petición a un flujo de proceso de negocio](bpf-add-on-demand-workflow.md) 

