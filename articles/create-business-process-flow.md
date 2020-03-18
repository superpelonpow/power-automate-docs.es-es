---
title: Creación de un flujo de proceso de negocio en Power Apps | Microsoft Docs
description: Aprenda a crear un flujo de proceso de negocio
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: efe86ab3-430f-485a-b924-6ed82cfbb449
caps.latest.revision: 39
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ad075ec6c4b00d46f000b86aaa9166e40adda640
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194057"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Tutorial: Creación de un flujo de proceso de negocio para estandarizar procesos


En este tutorial se explica cómo crear un flujo de proceso de negocio con Power Apps. Para saber más sobre por qué se usan flujos de proceso de negocio, vea [Información general sobre flujos de proceso de negocio](business-process-flows-overview.md). Para más información sobre cómo crear un flujo de tareas móviles, vea [Crear un flujo de tareas móviles](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow).  
  
 Cuando un usuario inicia un flujo de proceso de negocio, las fases y los pasos del proceso se muestran en la barra de proceso en la parte superior de un formulario:  
  
 ![Proceso de negocio con fases](media/business-process-stages.png "Proceso de negocio con fases")  
  
 > [!TIP]
 >  Después de crear una definición de flujo de proceso de negocio, puede proporcionar control sobre quién puede crear, leer, actualizar o eliminar la instancia del flujo de proceso de negocio. Por ejemplo, para los procesos relacionados con el servicio, podría proporcionar acceso completo a los representantes de servicio al cliente para que cambien la instancia del flujo de proceso de negocio, pero proporcionar acceso de solo lectura a la instancia para los representantes de ventas, de modo que puedan supervisar las actividades posventa de sus clientes. Para establecer la seguridad de una definición de flujo de proceso de negocio que ha creado, seleccione **Habilitar roles de seguridad** en la barra de acciones.  
  
<a name="BKMK_Createbusinessprocessflows"></a>

## <a name="prerequisites"></a>Requisitos previos

Necesita [Flow Plan 2](https://preview.flow.microsoft.com/pricing/) para crear flujos de procesos de negocio. Algunos planes de licencias de Dynamics 365 incluyen Flow Plan 2.

## <a name="create-a-business-process-flow"></a>Crear un flujo de proceso de negocio  
  
1. Abra el [explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer).
  
2. En el panel de navegación izquierdo, seleccione **Procesos**. 
  
3.  En la barra de herramientas **Acciones**, seleccione **Nuevo**.  
  
4.  En el cuadro de diálogo **Crear proceso**, rellene los campos obligatorios:  
  
    -   Escriba un nombre de proceso. El nombre de proceso no tiene que ser único, pero debe ser significativo para las personas que deben elegir un proceso. Puede cambiarlo más adelante.  
  
    -   En la lista **Categoría**, seleccione **Flujo de proceso de negocio**.  
  
         No se puede cambiar la categoría después de crear el proceso.  
  
    -   En la lista **Entidad**, seleccione la entidad en la que quiere basar el proceso.  
  
         La entidad seleccionada afectará a los campos disponibles para los pasos que se pueden agregar a la primera fase del flujo de proceso. Si no encuentra la entidad que quiere, asegúrese de que la entidad tiene la opción Business process flows (fields will be created) [Flujos de proceso de negocio (se crearán los campos)] establecida en la definición de entidad. No se puede cambiar esto después de guardar el proceso.  
  
5. Seleccione **Aceptar**.  
  
     Se crea el nuevo proceso y se abre el diseñador de flujo de proceso de negocio con una sola fase creada automáticamente.  
  
 ![Ventana del flujo de proceso de negocio con los elementos principales](media/business-process-flow-window-showing-main-elements.png "Ventana del flujo de proceso de negocio con los elementos principales")  
  
6. **Agregue las fases.** Si los usuarios van a avanzar de una fase de negocio a otra en el proceso:  
  
    1.  Arrastre un componente **Fase** desde la pestaña **Componentes** y suéltelo en un signo + en el diseñador.  
  
        ![Arrastrar una fase de proceso de negocio](media/drag-business-process-stage.png "Arrastrar una fase de proceso de negocio")  
  
    2.  Para establecer las propiedades de una fase, seleccione la fase y establezca las propiedades en la pestaña **Propiedades** en la parte derecha de la pantalla:  
  
        -   Escriba un nombre para mostrar.  
  
        -   Si quiere, puede seleccionar una categoría para la fase.  La categoría (como **Calificar** o **Desarrollar**) aparece como un botón de contenido adicional en la barra de proceso.  
  
            ![Botón de contenido adicional de la barra de procesos de negocio](media/business-process-bar-chevron.png "Botón de contenido adicional de la barra de procesos de negocio")  
  
        -   Cuando haya terminado de cambiar las propiedades, haga clic en **Aplicar**.  
  
7. **Agregue pasos a una fase.** Para ver los pasos de una fase, seleccione **Detalles** en la esquina inferior derecha de la fase. Para agregar más pasos:  
  
    1.  Arrastre el componente **Paso** a la fase de la pestaña **Componentes**.  
  
        ![Adición de un paso a una fase de un proceso de negocio](media/add-step-stage-business-process.png "Adición de un paso a una fase de un proceso de negocio")  
  
    2.  Seleccione el paso y establezca las propiedades en la pestaña **Propiedades**:  
  
        1.  Debe especificar un nombre para mostrar para el paso.  
  
        2.  Si quiere que los usuarios escriban datos para completar un paso, seleccione el campo correspondiente en la lista desplegable.  
  
        3.  Seleccione **Obligatorio** si los usuarios deben rellenar el campo para completar el paso antes de pasar a la siguiente fase del proceso.  
  
        4.  Seleccione **Aplicar** cuando haya terminado.  
  
8. **Agregue una rama (condición) al proceso.** Para agregar una condición de rama:  
  
    1.  Arrastre el componente **Condición** desde la pestaña **Componentes** hasta un signo + entre dos fases.  
  
        ![Adición de una condición a un flujo de proceso de negocio](media/add-condition-business-process-flow.png "Adición de una condición a un flujo de proceso de negocio")  
  
    2.  Seleccione la condición y establezca las propiedades en la pestaña **Propiedades**. Para más información sobre las propiedades de creación de ramas, vea [Enhance business process flows with branching](enhance-business-process-flows-branching.md) (Mejorar los flujos de proceso de negocio con creación de ramas). Cuando haya terminado de establecer las propiedades para la condición, seleccione **Aplicar**.  
  
9. **Agregue un flujo de trabajo.** Para invocar un flujo de trabajo:  
  
    1.  Arrastre un componente **Flujo de trabajo** desde la pestaña **Componentes** hasta una fase, o vaya al elemento **Flujo de trabajo global** en el diseñador.   Decidir cuál debe agregar dependerá de lo siguiente:  
  
       - **Arrástrelo a una fase** cuando quiera desencadenar el flujo de trabajo al entrar o salir de la fase. El componente de flujo de trabajo debe basarse en la misma entidad principal que la fase.  
  
       - **Arrástrelo hasta el elemento Flujo de trabajo global** cuando quiera desencadenar el flujo de trabajo cuando se active el proceso o cuando se archive el proceso (cuando el estado cambia a **Completado** o **Abandonado**). El componente de flujo de trabajo debe basarse en la misma entidad principal que el proceso.  
  
    2.  Seleccione el flujo de trabajo y establezca las propiedades en la pestaña **Propiedades**:  
  
       1.  Escriba un nombre para mostrar.  
  
       2.  Seleccione cuándo debe activarse el flujo de trabajo.  
  
       3.  Busque un flujo de trabajo activo a petición que coincida con la entidad de la fase o cree un nuevo flujo de trabajo mediante **Nuevo**.  
  
       4.  Seleccione **Aplicar** cuando haya terminado.  
  
       Para más información sobre flujos de trabajo, vea [Procesos de flujo de trabajo](../common-data-service/workflow-processes.md).  
  
10. Para validar el flujo de proceso de negocio, seleccione **Validar** en la barra de acciones.  
  
11. Para guardar el proceso como un borrador mientras sigue trabajando en él, seleccione **Guardar** en la barra de acciones.  
  
    > [!IMPORTANT]
    >  Mientras un proceso sea un borrador, los demás no podrán usarlo.  
  
12. Para activar el proceso y que esté disponible para el resto del equipo, seleccione **Activar** en la barra de acciones.  

13. Para proporcionar control sobre quién puede crear, leer, actualizar o eliminar la instancia del flujo de proceso de negocio, seleccione **Editar roles de seguridad** en la barra de comandos del diseñador. Por ejemplo, para los procesos relacionados con el servicio, podría proporcionar acceso completo a los representantes de servicio al cliente para que cambien la instancia del flujo de proceso de negocio, pero proporcionar acceso de solo lectura a la instancia para los representantes de ventas, de modo que puedan supervisar las actividades posventa de sus clientes.

  En la pantalla **Roles de seguridad**, seleccione el nombre de un rol para abrir la página de información del rol de seguridad. Seleccione la pestaña Flujos de proceso de negocio y, después, asigne los privilegios adecuados en el flujo de proceso de negocio para un rol de seguridad.

  > [!NOTE]
  > Los roles de seguridad Administrador del sistema y Personalizador del sistema tienen acceso a nuevos flujos de procesos de negocio de forma predeterminada.

   ![Asignar privilegios a un flujo de proceso de negocio](media/bpf-assign-privileges.png)

  Para especificar los privilegios, seleccione los botones de radio correspondientes y haga clic en Guardar. Para más información sobre privilegios, vea [Business process flow privileges](business-process-flows-overview.md#BKMK_MultipleBPF) (Privilegios de flujos de proceso de negocio).

  Después, no olvide asignar el rol de seguridad a los usuarios adecuados de la organización.

> [!TIP] 
>  Estas son algunas sugerencias que debe tener en cuenta cuando trabaje con el flujo de tareas en la ventana del diseñador:  
>   
> - Realice una instantánea de todo en la ventana del flujo de proceso de negocio. Para ello, seleccione **Instantánea** en la barra de acciones. Esto resulta útil, por ejemplo, si quiere compartir el proceso con un miembro del equipo y recibir comentarios de él.  
> - Use el minimapa para desplazarse rápidamente a diferentes partes del proceso. Esto es útil cuando tiene un proceso complicado que se desplaza fuera de la pantalla.  
> - Para agregar una descripción al proceso de negocio, seleccione **Detalles** bajo el nombre de proceso en la esquina izquierda de la ventana del flujo de proceso de negocio. Puede usar hasta 2000 caracteres.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>Editar un flujo de proceso de negocio  
 Para editar flujos de procesos de negocio, abra el explorador de soluciones, seleccione **Procesos** y, después, seleccione el **Flujo de proceso de negocio** en la lista de procesos que quiere editar.  
  
 Cuando selecciona el nombre del flujo de proceso de negocio que quiere editar en la lista de procesos, este se abre en el diseñador, donde puede realizar las actualizaciones que quiera. Expanda **Detalles** bajo el nombre de proceso para cambiar su nombre o agregue una descripción y vea información adicional.  
  
 ![Sección de detalles expandida de un flujo de proceso de negocio](media/business-process-flow-details.png "Sección de detalles expandida de un flujo de proceso de negocio")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>Otros aspectos que debe conocer sobre flujos de procesos de negocio
 **Editar fases**  
Los flujos de procesos de negocio pueden tener hasta 30 fases.    
  
Puede agregar o cambiar las siguientes propiedades de una fase:  
  
- **Nombre de fase**  
  
- **Entidad**. Puede cambiar la entidad de cualquier fase, excepto la primera.  
  
- **Categoría de fases**. Una categoría permite agrupar las fases por un tipo de acción. Es útil para los informes que agrupan los registros según la fase en la que se encuentran. Las opciones para la categoría de fases proceden del conjunto de opciones globales Categoría de fase. Puede agregar opciones adicionales a este conjunto de opciones globales y cambiar las etiquetas de las opciones existentes, si lo prefiere. También puede eliminar estas opciones si quiere, pero se recomienda que mantenga las opciones existentes. No podrá volver a agregar exactamente la misma opción si la elimina. Si no quiere que la usen, cambie la etiqueta a "No usar".  
  
- **Relación**. Indique una relación cuando la fase anterior del proceso esté basada en una entidad diferente. Para la fase que se está definiendo actualmente, elija **Seleccionar relaciones** para señalar que se use una relación al cambiar entre dos fases. Se recomienda que seleccione una relación por estos buenos motivos:  
  
    -   A menudo, las relaciones tienen asignaciones de atributos definidas que transmiten automáticamente datos entre los registros, lo que reduce la entrada de datos.  
  
    -   Al seleccionar **Siguiente fase** en la barra de proceso para un registro, se mostrará cualquier registro que use la relación en el flujo de proceso, con lo que se promueve la reutilización de registros en el proceso. Además, puede usar flujos de trabajo para automatizar la creación de registros para que el usuario solo tenga que seleccionarlo en lugar de crear uno para optimizar aún más el proceso.  
  
**Editar pasos**  
 Cada fase puede tener hasta 30 pasos.    
  
**Agregar rama**  
Para saber más sobre cómo agregar una rama a una fase, vea [Enhance business process flows with branching](enhance-business-process-flows-branching.md) (Mejorar los flujos de proceso de negocio con creación de ramas).  
  
Para hacer que un flujo de proceso de negocio esté disponible para que lo usen otros usuarios, debe ordenar el flujo de proceso, habilitar los roles de seguridad y activarlo.  
  
**Establecer el orden del flujo de proceso**  
 Cuando tenga más de un flujo de proceso de negocio para una entidad (tipo de registro), tendrá que establecer qué proceso se asigna automáticamente a los nuevos registros. En la barra de comandos, seleccione **Ordenar flujo de proceso**. Para los nuevos registros o los registros que aún no tienen un flujo de proceso asociado a ellos, se usará el primer flujo de proceso de negocio al que acceda un usuario.  
  
**Habilitar roles de seguridad**  
Los usuarios tienen acceso a un flujo de proceso de negocio según el privilegio definido en el flujo de proceso de negocio en el rol de seguridad asignado al usuario. 

De manera predeterminada, los roles de seguridad **Administrador del sistema** y **Personalizador del sistema** son los únicos que pueden ver un nuevo flujo de proceso de negocio. 

Para especificar los privilegios en un flujo de proceso de negocio, abra el flujo del proceso de negocio para su edición y seleccione **Editar roles de seguridad** en la barra de comandos del diseñador de flujo de proceso de negocio. Vea el paso 13 en [Crear un flujo de proceso de negocio](#create-a-business-process-flow) mencionado antes en este tema.
  
**Activar**  
Antes de que los demás puedan usar el flujo de proceso de negocio, primero debe activarlo. En la barra de comandos, seleccione **Activar**. Después de confirmar la activación, el flujo de proceso de negocio estará listo para usarse. Si un flujo de proceso de negocio tiene errores, no podrá activarlo hasta que se corrijan los errores.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>Agregar una acción a petición a un flujo de proceso de negocio
La actualización de Dynamics 365 (en línea), versión 9.0 introduce una característica de flujo de proceso de negocio: la automatización de flujos de procesos de negocio con los pasos de acción. Puede agregar un botón a un flujo de proceso de negocio que desencadenará una acción o un flujo de trabajo.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Agregar flujos de trabajo a petición o acciones mediante un paso de acción
Supongamos que, como parte del proceso de calificación de oportunidades, la organización Contoso exige que un revisor designado se encargue de revisar todas las oportunidades. Por este motivo, la organización Contoso creó una acción que: 

- Crea un registro de tarea que está asignado al revisor de oportunidades. 
- Anexa "Listo para revisión" al tema de oportunidad. 

Además, Contoso necesita poder ejecutar estas acciones a petición. Para integrar estas tareas en el proceso de calificación de oportunidades, las acciones deben aparecer en el flujo del proceso de negocio de la oportunidad. Para habilitar esta función, seleccione **As a Business Process Flow action step** (Paso de acción como flujo de proceso de negocio).
![Disponible para ejecutarse como un flujo de proceso de negocio.](media/action-available-to-run.png)

Después, se agrega el paso de acción al flujo de proceso de negocio de la oportunidad de Contoso. Luego se valida y se actualiza el flujo del proceso.

![Acción que se agrega al flujo de proceso de negocio de la oportunidad.](media/add-action-to-bpf.png)

Ahora, los empleados de Contoso pueden iniciar la acción desde el paso de proceso de negocio **Calificar oportunidad**, a petición, con solo seleccionar **Ejecutar**.

![Ejecutar acción.](media/action-execute.png)

> [!IMPORTANT]
> - Para poder ejecutar una acción o un flujo de trabajo a petición, el flujo de proceso de negocio debe incluir un paso de acción. Si el paso de acción ejecuta un flujo de trabajo, el flujo de trabajo debe configurarse para ejecutarse a petición.
> - La entidad asociada con la acción o el flujo de trabajo debe ser la misma que la entidad asociada con el flujo de proceso de negocio.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Limitación del uso de los pasos de acción en un flujo de proceso de negocio

- Las acciones no están disponibles como pasos de acción si los parámetros de entrada o de salida son los tipos Entity, EntityCollection u OptionSet (Picklist). Las acciones con más de un parámetro de salida EntityReference o cualquier número de parámetros de entrada EntityReference no están disponibles como pasos de acción. Las acciones que no están asociadas con una entidad principal (acción global) no están disponibles como pasos de acción.

## <a name="instant-flows-in-business-process-flows"></a>Flujos instantáneos en flujos de proceso de negocio

Puede ejecutar un **flujo instantáneo** para automatizar tareas repetitivas, generar documentos, realizar el seguimiento de aprobaciones, etc., desde una fase de un proceso de negocio.

### <a name="add-an-instant-flow-as-a-step-in-a-business-process"></a>Adición de un flujo instantáneo como paso de un proceso de negocio

Supongamos que vende impresoras y que usa el **Proceso de cliente potencial a ventas de la oportunidad** para cerrar las ventas. Como parte de este proceso, le gustaría que el jefe de equipo revisara y aprobara las propuestas que el equipo de ventas elabora en una fase anterior del flujo de proceso de negocio antes de compartirlas con el cliente.

Para ello, deberá hacer dos cosas:
1. Crear un flujo instantáneo que solicite la revisión y la aprobación de la propuesta del equipo.
1. Agregar el flujo instantáneo como un paso en el **Proceso de cliente potencial a ventas de la oportunidad**.

> [!TIP]
> Solo los [flujos compatibles con la solución](https://docs.microsoft.com/flow/overview-solution-flows) se pueden agregar como paso de un proceso de negocio. 

### <a name="build-an-instant-flow"></a>Creación de un flujo instantáneo

1. En Power Automate, seleccione **Soluciones** en el menú de navegación.
1. Seleccione **Default Solution** (Solución predeterminada)en la lista de soluciones que aparece. 
1. Seleccione el menú **+ Nueva** y, luego, **Flujo** en la lista que aparece.
1. Busque y seleccione el conector **Common Data Service**.
1. Busque y seleccione el desencadenador **Cuando se selecciona un registro** en la lista de desencadenadores de **Common Data Service**.
1. Establezca **Entorno** en **Default** (Predeterminado) y, luego, establezca **Nombre de entidad** en **Proceso de cliente potencial a ventas de la oportunidad**.
1. Agregue un campo de entrada de texto para que el usuario escriba el vínculo a la propuesta.

   ![Desencadenador de flujo instantáneo](media/instant-flow-trigger.png "Desencadenador de flujo instantáneo")

   Necesitaremos información de la instancia de flujo de proceso de negocio para proporcionar el contexto de la solicitud de aprobación, de modo que siga estos pasos.

1. Agregue la acción **Analizar JSON**. 
1. Establezca **Contenido** en **entidad**; para ello, selecciónela en la lista de valores dinámicos del desencadenador **Cuando se selecciona un registro**.
1. Pegue el siguiente contenido en el campo **Esquema**.

    ```json
    {
        "type": "object",
        "properties": {
        "entity": {
            "type": "object",
            "properties": {
                "FlowsWorkflowLogId": {
                    "type": "string"
                },
                "BPFInstanceId": {
                    "type": "string"
                },
                "BPFInstanceEntityName": {
                    "type": "string"
                },
                "BPFDefinitionId": {
                    "type": "string"
                },
                "BPFDefinitionEntityName": {
                    "type": "string"
                },
                "StepId": {
                    "type": "string"
                },
                "BPFDefinitionName": {
                    "type": "string"
                },
                "BPFInstanceName": {
                    "type": "string"
                },
                "BPFFlowStageLocalizedName": {
                    "type": "string"
                },
                "BPFFlowStageEntityName": {
                    "type": "string"
                },
                "BPFFlowStageEntityCollectionName": {
                    "type": "string"
                },
                "BPFFlowStageEntityRecordId": {
                    "type": "string"
                },
                "BPFActiveStageId": {
                    "type": "string"
                },
                "BPFActiveStageEntityName": {
                    "type": "string"
                },
                "BPFActiveStageLocalizedName": {
                    "type": "string"
                }
            }
          }
        }
   }
   ```

   El resultado debería ser similar a este:

   ![Analizar JSON](media/instant-flow-json-date.png "Analizar JSON")

  1. Agregue la acción **Obtener registro** del conector **Common Data Service**.
  1. Establezca **Entorno** en **(Current)** (Actual), **Nombre de entidad** en **Proceso de cliente potencial a ventas de la oportunidad** e **Identificador de artículo** en **BPFFlowStageEntityRecordID**.

     ![Adición de un registro](media/instant-flow-add-record.png)

     Ahora que tenemos los datos, agregue la acción **Aprobaciones - Iniciar y esperar una aprobación (V2)** y rellene la información pertinente para definir el proceso de aprobación. Aprenda más sobre las [aprobaciones]( sequential-modern-approvals.md) si no está familiarizado con ellas.

     > [!TIP]
     > - Use el selector de contenido dinámico para agregar campos de la acción **Obtener registro** a fin de agregar información pertinente a la solicitud de aprobación, de modo que los aprobadores puedan saber con facilidad de qué trata la solicitud. 
     > - Para proporcionar contexto adicional respecto a la fase activa en la que se encuentra el proceso de negocio, agregue el campo **BPFActiveStageLocalizedName** de la lista de valores dinámicos.

     La tarjeta **Iniciar y esperar una aprobación (V2)** podría parecerse a esta:

      ![Tarjeta de aprobación](media/instant-flow-add-approval-action.png)

1. Por último, guarde el flujo y actívelo.

### <a name="add-this-flow-as-a-step-in-the-lead-to-opportunity-sales-process"></a>Agregue este flujo como un paso del proceso de cliente potencial a ventas de la oportunidad.

Ahora que ha creado el flujo instantáneo, lo único que hace falta es agregarlo al flujo de procesos de negocio. 

1. Abra el **Proceso de cliente potencial a ventas de la oportunidad** en el diseñador de flujos de procesos de negocio. 
1. Arrastre **Paso de flujo (vista previa)** de la lista de **Componentes** a la fase **Proponer**.
1. A continuación, seleccione el icono de búsqueda en el campo **Seleccione un flujo** para mostrar todos los flujos que se pueden agregar a un flujo de proceso de negocio.
1. Seleccione un flujo de la lista y, luego, seleccione el botón **Aplicar** situado en la parte inferior del panel de propiedades para guardar los cambios.
1. Por último, seleccione el botón **Actualizar** para que este flujo de proceso de negocio con su nuevo paso de flujo instantáneo esté disponible para los usuarios.


## <a name="the-action-center"></a>Centro de actividades

Cuando necesite ver la lista de flujos de proceso de negocio en los que participa, consulte el centro de actividades unificado. 

![Vista de flujos de proceso de negocio del centro de actividades unificado](media/approvals-center.png "Vista de los flujos de proceso de negocio del centro de actividades unificado")

![Vista de flujos de aprobación del centro de actividades unificado](media/action-center-bpf.png "Vista de flujos de aprobación del centro de actividades unificado")

En el centro de actividades unificado, verá todos los procesos de negocio en los que se le asigna al menos un registro de entidad de Common Data Service que utiliza el proceso. Por ejemplo, si un proceso de negocio usa las entidades **Cliente potencial** y **Oportunidad** de Common Data Service, verá todas las instancias de este proceso en las que se le ha asignado el registro de cliente potencial o de oportunidad.

Puede ver todas las instancias en las que se está trabajando actualmente en la pestaña **Activa**. En esta pestaña, puede ver los detalles siguientes:

- El nombre del proceso.
- La fase actual de cada proceso.
- El propietario del registro de Common Data Service asociado a la fase activa.
- El tiempo transcurrido desde que se creó la instancia.

Para ver una instancia:

Seleccione una instancia para abrirla en una nueva pestaña o selecciónela para copiar un vínculo, compartirlo por correo electrónico, abandonar la instancia o eliminarla.
  
## <a name="next-steps"></a>Pasos siguientes

 - [Business process flows overview](business-process-flows-overview.md) (Introducción a los flujos de procesos de negocio)  
 - [Enhance business process flows with branching](enhance-business-process-flows-branching.md) (Mejorar los flujos de proceso de negocio con creación de ramas).
 - [Introducción a las aprobaciones](sequential-modern-approvals.md)
 - [Pasos detallados para agregar un flujo instantáneo a un flujo de proceso de negocio](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/instant-steps-business-process-flows)


