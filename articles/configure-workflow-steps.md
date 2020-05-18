---
title: Configuración de fases y pasos de flujo de trabajo en Power Apps | Microsoft Docs
description: Obtenga información sobre cómo configurar pasos de flujo de trabajo
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 0b47dfd5-76db-464f-90c0-c64a0173dcdd
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5aa5d43617a0b60f02a0e8b7f58a597b2f0de5f3
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297261"
---
# <a name="configure-workflow-stages-and-steps"></a>Configuración de fases y pasos de flujo de trabajo


Al diseñar flujos de trabajo tiene la opción de que contengan la lógica que quiere realizar en fases y pasos.  
  
 **Fases**  
 Las fases simplifican la lectura de la lógica del flujo de trabajo y la explican. Sin embargo, las fases no afectan a la lógica ni al comportamiento de los flujos de trabajo. Si un proceso tiene fases, todos los pasos del proceso deben estar incluidos en una fase.  
  
 **Pasos**  
 Los pasos son una unidad de lógica de negocios en un flujo de trabajo. Los pasos pueden incluir condiciones, acciones, otros pasos o una combinación de estos elementos.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Acciones que los procesos del flujo de trabajo pueden realizar  

 Los procesos de flujo de trabajo pueden realizar las acciones que aparecen en la tabla siguiente.  
  
|Para|Descripción|  
|------------|-----------------|  
|**Crear registro**|Crea un nuevo registro de una entidad y asigna valores de su elección a los atributos.|  
|**Actualizar registro**|Puede actualizar el registro en el que se ejecuta el flujo de trabajo, cualquiera de los registros vinculados a ese registro en una relación N:1 o cualquier registro creado por pasos anteriores.|  
|**Asignar registro**|Puede asignar el registro en el que se ejecuta el flujo de trabajo, cualquiera de los registros vinculados a ese registro con una relación N:1 o cualquier registro creado por pasos anteriores.|  
|**Enviar correo electrónico**|Envía un mensaje de correo electrónico. Puede elegir crear un nuevo mensaje de correo electrónico o usar una plantilla de correo electrónico configurada para la entidad de registro en la que se ejecuta el flujo de trabajo o cualquier entidad que tenga una relación N:1 con la entidad o la entidad de los registros creados por pasos anteriores.|  
|**Iniciar flujo de trabajo secundario**|Inicia un proceso de flujo de trabajo que se ha configurado como un flujo de trabajo secundario.|  
|**Cambiar estado**|Cambia el estado del registro en el que se ejecuta el proceso, cualquiera de los registros vinculados a ese registro con una relación N:1 o cualquier registro creado por pasos anteriores.|  
|**Detener flujo de trabajo**|Detiene el flujo de trabajo actual. Puede establecer un estado **Correcto** o **Cancelado** y especificar un mensaje de estado.<br /><br /> Cuando los flujos de trabajo en tiempo real se configuran para un evento, detener un flujo de trabajo con el estado de cancelado impide que la acción de evento se complete. Consulte [Usar flujos de trabajo en tiempo real](configure-workflow-steps.md#BKMK_SynchronousWorkflows) para obtener más información.|  
|**Paso personalizado**|Los desarrolladores pueden crear pasos del flujo de trabajo personalizados que definan acciones. No hay pasos personalizados disponibles de forma predeterminada.|  
  
### <a name="setting-record-values"></a>Establecer valores de registro  

 Cuando se crea un registro se pueden establecer valores para el registro. Cuando se actualiza un registro, se pueden establecer, anexar, aumentar, disminuir, multiplicar o desactivar los valores.  
  
 Al seleccionar **Establecer propiedades**, se abre de un diálogo que muestra el formulario predeterminado para la entidad.  
  
 En la parte inferior del diálogo puede ver una lista de campos adicionales no presentes en el formulario.  
  
 Para un campo, puede establecer un valor estático y este será definido por el flujo de trabajo.  
  
 A la derecha del diálogo, el **Asistente de formulario** permite establecer o anexar valores dinámicos desde el contexto del registro actual. Se incluyen valores de registros relacionados a los que se puede acceder desde las relaciones N:1 (varios a uno) de la entidad.  
  
 Las opciones disponibles en el **Asistente de formulario** dependen del campo que ha seleccionado en el formulario. Cuando establezca un valor dinámico, verá un marcador de posición amarillo, llamado campo de datos dinámico, que muestra dónde se incluirán los datos dinámicos. Si desea quitar el valor, simplemente seleccione el campo de datos dinámico y elimínelo. Para los campos de texto, puede usar una combinación de datos estáticos y dinámicos.  
  
 Con los valores dinámicos, no se sabe con certeza si un campo o la entidad relacionada tienen el valor que se desea establecer. En realidad, puede establecer una serie de campos para intentar establecer el valor y colocarlos por orden usando las flechas verdes. Si el primer campo no tiene datos, se probará el segundo campo y así sucesivamente. Si ninguno de los campos tiene datos, puede especificar un valor predeterminado para usarlo.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Configurar las condiciones de las acciones de flujo de trabajo  

 Las acciones que se aplicarán a menudo dependen de condiciones. Los procesos de flujo de trabajo proporcionan varias maneras de definir condiciones y crear una lógica de bifurcación para obtener los resultados deseados. Puede comprobar los valores del registro con el que el proceso de flujo de trabajo se está ejecutando, los registros vinculados a dicho registro con una relación N:1 o los valores dentro del propio proceso  
  
|Tipo de condición|Descripción|  
|--------------------|-----------------|  
|**Condición de comprobación**|Una instrucción lógica "if-\<condition> then".<br /><br /> Puede comprobar los valores actuales del registro en el que se ejecuta el flujo de trabajo, cualquiera de los registros vinculados a ese registro en una relación N:1 o cualquier registro creado por pasos anteriores. Según esos valores puede definir pasos adicionales cuando la condición se cumpla.<br /><br /> En la instrucción "if-\<condition> then", se pueden usar los operadores siguientes: **Es igual a**, **No es igual a**, **Contiene datos**, **No contiene datos**, **Bajo** y **No menor que**. **Nota:** **Bajo** y **No menor que** son operadores jerárquicos. Se pueden usar solo en las entidades que tengan una relación jerárquica definida. Si está intentando utilizar estos operadores en las entidades que no tienen definida la relación jerárquica, verá el mensaje de error: "Está usando un operador jerárquico en una entidad que no tiene ninguna relación de jerarquía definida. Convierta la entidad en jerárquica (marcando una relación como jerárquica) o use un operador diferente". Para obtener más información sobre las relaciones jerárquicas, vea [Define and query hierarchically related data](/powerapps/maker/common-data-service/define-query-hierarchical-data) (Definición y consulta de datos relacionados jerárquicamente). Un captura de pantalla después de la tabla es un ejemplo de definición del proceso de flujo de trabajo que usa los operadores jerárquicos **Bajo** y **No menor que** .|  
|**Rama condicional**|Una instrucción lógica de tipo "else-if-then", el editor utiliza el texto "De lo contrario, si \<condición> entonces:"<br /><br /> Seleccione una condición de comprobación que haya definido anteriormente y podrá agregar una rama condicional para definir pasos adicionales cuando la condición de comprobación devuelva false.|  
|**Acción predeterminada**|Instrucción lógica "de lo contrario". el editor usa el texto "De lo contrario:"<br /><br /> Seleccione una condición de comprobación, rama condicional, condición de espera o rama de espera paralela que haya definido anteriormente y podrá usar una acción predeterminada para definir los pasos para todos los casos que no cumplan los criterios definidos en elementos de condición o de rama.|  
|**Condición de espera**|Permite que un flujo de trabajo en segundo plano se pause hasta que se cumplan los criterios definidos por la condición. El flujo de trabajo comienza de nuevo automáticamente cuando se han cumplido los criterios de la condición de espera.<br /><br /> Los flujos de trabajo en tiempo real no pueden usar condiciones de espera.|  
|**Rama de espera paralela**|Define una condición de espera alternativa para un flujo de trabajo en segundo plano con el conjunto correspondiente de pasos adicionales que solo se realizan cuando se cumple el criterio inicial. Puede usar ramas de espera paralelas para crear límites de tiempo en la lógica de flujo de trabajo. Ayudan a evitar que el flujo de trabajo espere indefinidamente hasta que se hayan cumplido los criterios definidos en una condición de espera.|  
|**Paso personalizado**|Los desarrolladores pueden crear pasos del flujo de trabajo personalizados que definan condiciones. No hay pasos personalizados disponibles de forma predeterminada.|  
  
 La captura de pantalla siguiente contiene un ejemplo de definición del proceso de flujo de trabajo con los operadores jerárquicos **Bajo** y **No menor que**. En nuestro ejemplo, aplicamos dos descuentos diferentes a dos grupos de cuentas. En **Agregar paso**, seleccionamos **Condición de comprobación** para especificar la condición **if-then** que contiene los operadores **Bajo** o **No menor que**. La primera condición **if-then** se aplica a todas las cuentas que están **Bajo** la cuenta Alpine Ski House. Estas cuentas reciben un descuento del 10% en productos y servicios comprados. La segunda condición **if-then** se aplica a todas las cuentas que son **No menor que** la cuenta Alpine Ski House y reciben un descuento del 5%. A continuación, seleccionamos **Actualizar registro** para definir la acción que se deben realizar basándose en la condición.  
  
 ![Proceso de flujo de trabajo con operadores Bajo o No menor que](media/wfp-under-not-under.PNG "Proceso de flujo de trabajo con operadores Bajo o No menor que")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Usar flujos de trabajo en tiempo real  

 Puede configurar flujos de trabajo en tiempo real pero debe usarlos con cuidado. Los flujos de trabajo en segundo plano se recomiendan normalmente porque permiten que el sistema los aplique a medida que los recursos están disponibles en el servidor. Esto ayuda a allanar el trabajo que el servidor debe realizar y ayuda a mantener el máximo rendimiento para todas aquellas personas que usen el sistema. La desventaja es que las acciones definidas por flujos de trabajo en segundo plano no son inmediatas. No puede predecir cuando se aplicarán, pero tardarán normalmente unos minutos. Para la mayoría de los procesos de automatización de negocios resulta adecuado porque las personas que usan el sistema no tienen que saber que el proceso se está ejecutando.  
  
 Use los flujos de trabajo en tiempo real cuando un proceso de negocio requiera que alguien vea inmediatamente los resultados del proceso o si desea poder cancelar una operación. Por ejemplo, es posible que desee establecer algunos valores predeterminados para un registro la primera vez que se guarde, o asegurarse de que algunos registros no se eliminarán.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Convertir entre los flujos de trabajo en tiempo real y en segundo plano  

 Para cambiar un flujo de trabajo en tiempo real a un flujo de trabajo en segundo plano, elija **Convertir en flujo de trabajo en segundo plano** en la barra de herramientas.  
  
 Para cambiar un flujo de trabajo en segundo plano a un flujo de trabajo en tiempo real, elija **Convertir en flujo de trabajo en tiempo real** en la barra de herramientas. Si el flujo de trabajo en segundo plano usa condiciones de espera se convertirá en no válido y no podrá activarlo hasta que quite la condición de espera.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Iniciar flujos de trabajo en tiempo real antes o después del cambio de estado  

 Cuando se configura **Opciones para procesos automáticos** para flujos de trabajo en tiempo real, las opciones **Iniciar al** para el evento de cambios de estado permiten seleccionar **Después** o **Antes** para cuando cambie el estado. La opción predeterminada es **Después**.  
  
 Al seleccionar **Antes** está diciendo que desea que la lógica del flujo de trabajo se aplique antes de que se guarden los datos que cambian el estado. Esto proporciona la capacidad de comprobar los valores antes de que otra lógica se aplique después de la operación e impide que se ejecute otra lógica. Por ejemplo, puede tener lógica adicional en una acción de complemento o de flujo de trabajo personalizado que podría emprender acciones en otro sistema. Al detener el procesamiento posterior puede evitar los casos en que los sistemas externos se vean afectados. La aplicación de flujos de trabajo en tiempo real antes de este evento también significa que otras acciones de flujo de trabajo o complemento que haya podido guardar datos no necesitan "revertirse" cuando la operación se cancela.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Usar la acción Detener flujo de trabajo con flujos de trabajo en tiempo real  

 Cuando aplica una acción **Detener flujo de trabajo** en un flujo de trabajo tiene la opción de especificar una condición de estado que puede ser **Correcto** o **Cancelado**. Cuando establece el estado en Cancelado, impide la operación. Un mensaje de error que contiene el texto del mensaje de estado de la acción de detención se muestra el usuario con el título **Error de proceso empresarial**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Creación de lógica de negocios personalizada mediante procesos](guide-staff-through-common-tasks-processes.md)   
 [Información general de los procesos de flujo de trabajo](workflow-processes.md)   
 [Supervisar y administrar procesos de flujo de trabajo](monitor-manage-processes.md)   
 [Prácticas recomendadas para los procesos de flujo de trabajo](best-practices-workflow-processes.md)
