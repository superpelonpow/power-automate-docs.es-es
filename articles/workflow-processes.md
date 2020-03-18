---
title: Flujos de trabajo clásicos de Common Data Service | MicrosoftDocs
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
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195759"
---
# <a name="classic-common-data-service-workflows"></a>Flujos de trabajo clásicos de Common Data Service 


Los flujos de trabajo automatizan los procesos de negocio sin una interfaz de usuario. Normalmente, los usuarios utilizan los procesos de flujo de trabajo para iniciar la automatización que no requiere ninguna interacción del usuario.

> [!IMPORTANT]
> Use flujos en lugar de flujos de trabajo clásicos para automatizar los procesos empresariales. Más información: [Reemplazo de flujos de trabajo clásicos de Common Data Service con flujos](replace-workflows-with-flows.md)  
  
 Cada proceso de flujo de trabajo está asociado con una sola entidad. Al configurar los flujos de trabajo hay cuatro áreas principales que tener en cuenta:  
  
-   ¿Cuándo se deben iniciar?  
  
-   ¿Se deben ejecutar como un flujo de trabajo en tiempo real o un flujo de trabajo en segundo plano?  
  
-   ¿Qué acciones deben realizar?  
  
-   ¿En qué condiciones se deben realizar las acciones?  
  
 En este tema se explica cómo buscar procesos de flujo de trabajo y se describe cuándo iniciarlos y si se deben ejecutar en tiempo real o en segundo plano. Para obtener información sobre las acciones que deben realizar, y las condiciones, vea [Configuración de procesos de flujo de trabajo](configure-workflow-steps.md).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>¿Dónde se personalizan los procesos de flujo de trabajo?  
 Puede ver los flujos de trabajo de la organización en el nodo **Procesos** de la **solución predeterminada** y filtrar por los procesos que tengan la **Categoría** **Flujo de trabajo**.  
  
 ![Procesos filtrados por flujo de trabajo en Dynamics 365](media/workflow-processes-filtered.PNG "Procesos filtrados por flujo de trabajo en Dynamics 365")  
  
 En función de cómo se compile la aplicación, los usuarios pueden crear o modificar sus flujos de trabajo en ella. 
 
Los desarrolladores pueden crear flujos de trabajo con la información de la [Guía para desarrolladores de Common Data Service](https://docs.microsoft.com/powerapps/developer/common-data-service/workflow/workflow-extensions), y las soluciones que compre pueden incluir flujos de trabajo que se pueden modificar.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Propiedades de flujo de trabajo  
 En el Explorador de soluciones, haga clic en **Procesos** y en **Nuevo**.  
  
 Cuando se crea un flujo de trabajo, el cuadro de diálogo **Crear proceso** requiere que se establezcan tres propiedades comunes a todos los procesos:  
  
 ![Creación de un flujo de trabajo en Dynamics 365](media/create-workflow.PNG "Creación de un flujo de trabajo en Dynamics 365")  
  
 **Nombre del proceso**  
 No es necesario que el nombre del proceso de flujo de trabajo sea único, pero si espera tener una gran cantidad de flujos de trabajo, es posible que quiera usar una convención de nomenclatura para diferenciar claramente los procesos. Es posible que quiera aplicar prefijos estándar al nombre del flujo de trabajo. El prefijo puede describir la función del flujo de trabajo o el departamento dentro de la empresa. Esto le permitirá agrupar elementos similares en la lista de flujos de trabajo.  
  
 **Categoría**  
 Esta propiedad establece que se trata de un proceso de flujo de trabajo.  
  
 **Entidad**  
 Cada proceso de flujo de trabajo se debe establecer en una sola entidad. Después de crear el proceso de flujo de trabajo, no se puede cambiar la entidad.  
  
 **Ejecutar este flujo de trabajo en segundo plano (recomendado)**  
 Esta opción aparece al seleccionar Flujo de trabajo como categoría. Esta opción determina si el flujo de trabajo es en tiempo real o en segundo plano. Los flujos de trabajo en tiempo real se ejecutan inmediatamente (de forma sincrónica) y los flujos de trabajo en segundo plano se ejecutan de forma asincrónica. Las opciones de configuración disponibles dependen de la elección de esta opción. Los flujos de trabajo en segundo plano permiten condiciones de espera que no están disponibles para los flujos de trabajo en tiempo real. Mientras esas condiciones de espera no se usen, los flujos de trabajo en segundo plano se pueden convertir posteriormente en flujos de trabajo en tiempo real y viceversa. Para obtener más información sobre las condiciones de espera, vea [Configurar las condiciones de las acciones de flujo de trabajo](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions).  
  
 También tiene la opción **Tipo** para especificar si quiere crear un flujo de trabajo desde cero o a partir de una plantilla existente. Si selecciona **Proceso nuevo a partir de una plantilla existente (seleccione desde la lista)** puede elegir entre los procesos Flujos de trabajo disponibles que se guardaron anteriormente como una plantilla de proceso.  
  
 Después de crear el flujo de trabajo, o de modificar uno existente, tendrá las propiedades adicionales siguientes:  
  
 ![Pestaña General de un flujo de trabajo](media/create-workflow-general-tab.PNG "Pestaña General de un flujo de trabajo")  
  
 **Activar como**  
 Puede elegir **Plantilla de procesos** para crear un punto de partida avanzado para otras plantillas. Si elige esta opción, después de activar el flujo de trabajo, este no se aplica, sino que está disponible para seleccionarse en el cuadro de diálogo **Crear proceso** al seleccionar **Tipo**: **Proceso nuevo a partir de una plantilla existente (seleccione desde la lista)**  
  
 Las plantillas de procesos resultan prácticas cuando tiene un número de procesos de flujo de trabajo similares y quiere definirlos sin duplicar la misma lógica.  
  
> [!NOTE]
>  Al modificar una plantilla de procesos no se cambian los comportamientos de los demás procesos de flujo de trabajo creados anteriormente para usarlos como una plantilla. Un flujo de trabajo que se crea mediante una plantilla es una copia del contenido de la plantilla.  
  
 **Disponible para ejecutarse**  
 Esta sección contiene las opciones que describen cómo está disponible el flujo de trabajo para ejecutarse.  
  
 **Ejecutar este flujo de trabajo en segundo plano (recomendado)**  
 Esta casilla refleja la opción que seleccionó al crear el flujo de trabajo. Esta opción está deshabilitada, pero puede cambiarla desde el menú **Acciones** si selecciona **Convertir en flujo de trabajo en segundo plano** o **Convertir en flujo de trabajo en tiempo real**.  
  
 **Como un proceso a petición**  
 Elija esta opción si quiere permitir que los usuarios ejecuten este flujo de trabajo desde el comando **Ejecutar flujo de trabajo**.  
  
 **Como un proceso secundario**  
 Elija esta opción si quiere permitir que el flujo de trabajo esté disponible para iniciarse desde otro flujo de trabajo.  
  
 **Retención de tareas de flujo de trabajo**  
 Esta sección contiene una opción para eliminar un flujo de trabajo una vez completada la ejecución.  
  
 **Eliminar automáticamente las tareas de flujo de trabajo completadas (para ahorrar espacio en disco)**  
 Elija esta opción si quiere que una tarea de flujo de trabajo completada se elimine de forma automática.  
  
> [!NOTE]
>  Las tareas de flujo de trabajo no se eliminan inmediatamente al finalizar, sino un poco después, mediante un proceso por lotes.  
  
 **Ámbito**  
 En las entidades propiedad del usuario, las opciones son **Organización**, **Elemento principal: unidades de negocio secundarias**, **Unidad de negocio** o **Usuario**. Para las entidades que pertenecen a la organización la única opción es **Organización**.  
  
 Si el ámbito es **Organización**, la lógica de flujo de trabajo se puede aplicar a cualquier registro de la organización. En caso contrario, el flujo de trabajo solo se puede aplicar a un subconjunto de los registros que se encuentren dentro del ámbito.  
  
> [!NOTE]
>  El valor de ámbito predeterminado es **Usuario**. Asegúrese de comprobar que el valor de ámbito es adecuado antes de activar el flujo de trabajo.  
  
 **Iniciar al**  
 Use las opciones de esta sección para especificar cuándo se debe iniciar un flujo de trabajo de forma automática. Puede configurar un flujo de trabajo en tiempo real para que se ejecute antes de determinados eventos. Se trata de una característica muy eficaz porque el flujo de trabajo puede detener la acción antes de que se produzca. Más información: [Uso de flujos de trabajo en tiempo real](configure-workflow-steps.md#BKMK_SynchronousWorkflows). Las opciones son:  
  
- **Registro creado**  
  
- **Cambios de estado de registro**  
  
- **Registro asignado**  
  
- **Cambios en los campos de registro**  
  
- **Registro eliminado**  
  
> [!NOTE]
>  Tenga en cuenta que las acciones y condiciones que defina para el flujo de trabajo no tienen en cuenta cuándo se ejecuta el flujo de trabajo. Por ejemplo, si define un flujo de trabajo para actualizar el registro, esta acción no se puede realizar mediante un flujo de trabajo en tiempo real antes de crear el registro. Un registro que no existe no se puede actualizar. De forma similar, un flujo de trabajo en segundo plano no puede actualizar un registro que se haya eliminado, aunque podría definir esta acción para el flujo de trabajo. Si configura un flujo de trabajo para realizar una acción que no se puede realizar, se producirá un error y se producirá un error en el flujo de trabajo completo.  
  
 **Ejecutar como**  
 Esta opción solo está disponible si ha desactivado la opción **Ejecutar este flujo de trabajo en segundo plano (recomendado)** al crear el flujo de trabajo, o bien si posteriormente ha convertido un flujo de trabajo en segundo en un flujo de trabajo en tiempo real.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>Contexto de seguridad de los procesos de flujo de trabajo  
 Cuando un flujo de trabajo en segundo plano se configura como un proceso a petición y un usuario lo inicia con el comando **Ejecutar flujo de trabajo**, las acciones que el flujo de trabajo puede realizar se limitan a las que el usuario podría realizar según los privilegios y niveles de acceso definidos por los roles de seguridad establecidos para su cuenta de usuario.  
  
 Cuando un flujo de trabajo en segundo plano se inicia en función de un evento, el flujo de trabajo opera en el contexto del usuario que lo posee, que normalmente es el que lo ha creado.  
  
 Para los flujos de trabajo en tiempo real, dispone de la opción **Ejecutar como** , y puede elegir si el flujo de trabajo debe aplicar el contexto de seguridad del propietario del flujo de trabajo o del usuario que ha modificado el registro. Si el flujo de trabajo incluye acciones que todos los usuarios no podrían realizar según las restricciones de seguridad, debe elegir que el flujo de trabajo se ejecute como el propietario del flujo de trabajo.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Activación de un flujo de trabajo  
 Los flujos de trabajo solo se pueden modificar mientras están desactivados. Antes de poder usar un flujo de trabajo de forma manual o de aplicarlo en función de eventos, es necesario activarlo. Antes de que se pueda activar un flujo de trabajo, debe contener al menos un paso. Para obtener información sobre la configuración de los pasos, vea [Configuración de procesos de flujo de trabajo](configure-workflow-steps.md)  
  
 Un flujo de trabajo solo lo puede activar o desactivar el propietario del flujo de trabajo, o bien un usuario que tenga el privilegio **Actuar en nombre de otro usuario**, como el administrador del sistema.  El motivo de esto es que un usuario malintencionado podría modificar el flujo de trabajo de un usuario sin que sea consciente del cambio. Puede reasignar un flujo de trabajo que le pertenezca si cambia el propietario. Este campo está en la pestaña **Administración**. Si no es el administrador del sistema y tiene que modificar un flujo de trabajo que pertenece a otro usuario, el usuario tendrá que desactivarlo y asignárselo a usted. Cuando termine de modificar el flujo de trabajo, puede volver a asignárselo al usuario para que lo pueda activar.  
  
 Los flujos de trabajo en tiempo real requieren que el usuario tenga el privilegio **Activar procesos en tiempo real**. Como los flujos de trabajo en tiempo real tienen un mayor riesgo de afectar al rendimiento del sistema, solo se debe asignar este privilegio a los usuarios que puedan evaluar el riesgo potencial.  
  
 Los flujos de trabajo se guardan cuando se activan, por lo que no es necesario guardarlos antes de activarlos.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Configuración de procesos de flujo de trabajo](configure-workflow-steps.md)  <br/>
[Adición de un flujo de trabajo a petición a un flujo de proceso de negocio](bpf-add-on-demand-workflow.md) 

