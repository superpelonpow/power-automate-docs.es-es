---
title: Configuración de las fases y los pasos de flujo de trabajo en Power Apps | Microsoft Docs
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
ms.openlocfilehash: 0380509b2677e2229ecd2a98a5f3b8dde4f9732c
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74361438"
---
# <a name="configure-workflow-stages-and-steps"></a>Configuración de fases y pasos de flujo de trabajo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Al diseñar flujos de trabajo tiene la opción de que contengan la lógica que quiere realizar en fases y pasos.  
  
 **Fases**  
 Las fases facilitan la lectura de la lógica de flujo de trabajo y la explican. Pero las fases no afectan a la lógica ni al comportamiento de los flujos de trabajo. Si un proceso tiene fases, todos los pasos del proceso se deben incluir en una fase.  
  
 **Pasos**  
 Los pasos son una unidad de lógica de negocios dentro de un flujo de trabajo. Los pasos pueden incluir condiciones, acciones, otros pasos o una combinación de estos elementos.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Acciones que los procesos de flujo de trabajo pueden realizar  

 Los procesos de flujo de trabajo pueden realizar las acciones que se enumeran en la tabla siguiente.  
  
|Acción|Descripción|  
|------------|-----------------|  
|**Crear registro**|Crea un registro para una entidad y asigna los valores que elija a los atributos.|  
|**Actualizar registro**|Puede actualizar el registro en el que se ejecuta el flujo de trabajo, cualquiera de los registros vinculados a ese registro en una relación de varios a uno, o bien todos los registros creados por los pasos anteriores.|  
|**Asignar registro**|Puede asignar el registro en el que se ejecuta el flujo de trabajo, cualquiera de los registros vinculados a ese registro con una relación de varios a uno, o bien todos los registros creados por los pasos anteriores.|  
|**Enviar correo electrónico**|Envía un correo electrónico. Puede elegir crear un mensaje de correo electrónico o usar una plantilla de correo electrónico configurada para la entidad del registro en el que se ejecuta el flujo de trabajo, todas las entidades que tienen una relación de varios a uno con la entidad, o bien la entidad para los registros creados por los pasos anteriores.|  
|**Iniciar flujo de trabajo secundario**|Inicia un proceso de flujo de trabajo que se ha configurado como un flujo de trabajo secundario.|  
|**Cambiar estado**|Cambia el estado del registro en el que se ejecuta el flujo de trabajo, cualquiera de los registros vinculados a ese registro con una relación de varios a uno, o bien todos los registros creados por los pasos anteriores.|  
|**Detener flujo de trabajo**|Detiene el flujo de trabajo actual. Puede establecer un estado de **Correcto** o **Cancelado**, y especificar un mensaje de estado.<br /><br /> Cuando se configuran flujos de trabajo en tiempo real para un evento, detener un flujo de trabajo con el estado de Cancelado impedirá que se complete la acción del evento. Vea [Uso de flujos de trabajo en tiempo real](configure-workflow-steps.md#BKMK_SynchronousWorkflows) para obtener más información.|  
|**Paso personalizado**|Los desarrolladores pueden crear pasos de flujo de trabajo personalizados que definan acciones. De forma predeterminada, no hay ningún paso personalizado disponible.|  
  
### <a name="setting-record-values"></a>Establecimiento de valores de registro  

 Cuando se crea un registro, se pueden establecer valores para el registro. Cuando se actualiza un registro, se pueden establecer, anexar, incrementar, reducir, multiplicar o borrar los valores.  
  
 Al hacer clic en **Establecer propiedades**, se abre un cuadro de diálogo en el que se muestra el formulario predeterminado de la entidad.  
  
 En la parte inferior del cuadro de diálogo puede ver una lista de campos adicionales que no está presentes en el formulario.  
  
 En cualquiera de los campos, puede establecer un valor estático que se establecerá por el flujo de trabajo.  
  
 En el lado derecho del cuadro de diálogo **Asistente de formulario** puede establecer o anexar valores dinámicos desde el contexto del registro actual. Esto incluye los valores de los registros relacionados a los que se puede acceder desde las relaciones N:1 (varios a uno) para la entidad.  
  
 Las opciones disponibles en el **Asistente de formulario** dependen del campo que haya seleccionado en el formulario. Al establecer un valor dinámico, verá un marcador de posición de color amarillo conocido como un "slug" que muestra dónde se van a incluir los datos dinámicos. Si quiere quitar el valor, simplemente seleccione el campo de datos dinámico y elimínelo. Para los campos de texto, puede usar una combinación de datos estáticos y dinámicos.  
  
 Con los valores dinámicos, no se sabe con certeza que un campo o entidad relacionada tenga el valor que se quiere establecer. Puede establecer un número de campos para intentar establecer el valor y ordenarlos mediante las flechas de color verde. Si el primer campo no tiene datos, se intentará con el segundo y así sucesivamente. Si ninguno de los campos tiene datos, puede especificar un valor predeterminado para que se use.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Establecimiento de condiciones para las acciones de flujo de trabajo  

 Las acciones que se aplican a menudo dependen de las condiciones. Los procesos de flujo de trabajo proporcionan varias maneras de establecer las condiciones y crear la lógica de creación de ramas para obtener los resultados que se pretenden. Puede comprobar los valores del registro sobre el que se ejecuta el proceso de flujo de trabajo, de cualquiera de los registros vinculados a ese registro con una relación N:1 (de varios a uno), o bien los valores dentro del propio proceso.  
  
|Tipo de condición|Descripción|  
|--------------------|-----------------|  
|**Condición de comprobación**|Una instrucción "si \<condición> entonces" lógica.<br /><br /> Puede comprobar los valores actuales del registro en el que se ejecuta el flujo de trabajo, cualquiera de los registros vinculados a ese registro en una relación de varios a uno, o bien todos los registros creados por los pasos anteriores. En función de estos valores, puede definir pasos adicionales cuando la condición es true.<br /><br /> En la instrucción "si \<condición> entonces", puede usar los operadores siguientes: **Es igual a**, **No es igual a**, **Contiene datos**, **No contiene datos**, **Menor que** y **No menor que**. **Nota:** **Menor que** y **No menor que** son operadores jerárquicos. Solo se pueden usar en las entidades que tengan una relación jerárquica definida. Si intenta usar estos operadores en las entidades que no tienen definida la relación jerárquica, verá el mensaje de error: "Está usando un operador jerárquico en una entidad que no tiene ninguna relación de jerarquía definida. Convierta la entidad en jerárquica (marcando una relación como jerárquica) o use un operador diferente". Para obtener más información sobre las relaciones jerárquicas, vea [Define and query hierarchically related data](/powerapps/maker/common-data-service/define-query-hierarchical-data) (Definición y consulta de datos relacionados jerárquicamente). La captura de pantalla que aparece después de la tabla es un ejemplo de la definición del proceso de flujo de trabajo en el que se usan los operadores jerárquicos **Menor que** y **No menor que**.|  
|**Rama condicional**|Una instrucción "else-if-then" lógica, el editor usa el texto "De lo contrario, si \<condición> entonces:"<br /><br /> Seleccione una condición de comprobación que haya definido previamente y puede agregar una rama condicional para definir pasos adicionales cuando la condición de comprobación devuelve false.|  
|**Acción predeterminada**|Una instrucción "else" lógica. El editor usa el texto "De lo contrario:"<br /><br /> Seleccione una condición de comprobación, una rama condicional, una condición de espera o una rama de espera paralela que haya definido previamente y puede usar una acción predeterminada para definir pasos para todos los casos que no coincidan con los criterios definidos en los elementos de la condición o la rama.|  
|**Condición de espera**|Permite que un flujo de trabajo en segundo plano se detenga hasta que se cumplan los criterios definidos por la condición. El flujo de trabajo se inicia de nuevo de forma automática cuando se han cumplido los criterios de la condición de espera.<br /><br /> Los flujos de trabajo en tiempo real no pueden usar condiciones de espera.|  
|**Rama de espera paralela**|Define una condición de espera alternativa para un flujo de trabajo en segundo plano con un conjunto correspondiente de pasos adicionales que solo se ejecutan cuando se cumple el criterio inicial. Puede usar las ramas de espera paralelas para crear límites de tiempo en la lógica del flujo de trabajo. Ayudan a evitar que el flujo de trabajo espere de forma indefinida hasta que se cumplan los criterios definidos en una condición de espera.|  
|**Paso personalizado**|Los desarrolladores pueden crear pasos de flujo de trabajo personalizados que definan condiciones. De forma predeterminada, no hay ningún paso personalizado disponible.|  
  
 La captura de pantalla siguiente contiene un ejemplo de la definición del proceso de flujo de trabajo con los operadores jerárquicos **Menor que** y **No menor que**. En el ejemplo, se aplican dos descuentos diferentes a dos grupos de cuentas. En **Agregar paso**, se selecciona la **Condición de comprobación** para especificar la condición **if-then** que contiene los operadores **Menor que** o **No menor que**. La primera condición **si-entonces** se aplica a todas las cuentas que son **Menor que** la cuenta de Alpine Ski House. Estas cuentas reciben un 10 % de descuento en los bienes y servicios adquirida. La segunda condición **si-entonces** se aplica a todas las cuentas que son **No menor que** la cuenta de Alpine Ski House y reciben un descuento del 5 %. Después, se hace clic en **Actualizar registro** para definir la acción que se va a realizar en función de la condición.  
  
 ![Proceso de flujo de trabajo con los operadores Under&#47;No Under](media/wfp-under-not-under.PNG "Proceso de flujo de trabajo con los operadores Under/Not Under")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Uso de flujos de trabajo en tiempo real  

 Puede configurar flujos de trabajo en tiempo real, pero los debe usar con cuidado. Por lo general se recomiendan los flujos de trabajo en segundo plano, porque permiten que el sistema los aplique a medida que haya recursos disponibles en el servidor. Esto ayuda a facilitar el trabajo que tiene que hacer el servidor y a mantener el mejor rendimiento para todos los usuarios del sistema. El inconveniente es que las acciones definidas por los flujos de trabajo en segundo plano no son inmediatas. No se puede predecir cuándo se van a aplicar, pero generalmente se tardará unos minutos. Esto es correcto para la automatización de la mayoría de los procesos de negocio, porque no es necesario que los usuarios del sistema sean conscientes de que el proceso se está ejecutando.  
  
 Use flujos de trabajo en tiempo real cuando un proceso de negocio requiera que un usuario vea inmediatamente los resultados del proceso o si quiere tener la posibilidad de cancelar una operación. Por ejemplo, es posible que le interese establecer valores predeterminados concretos para un registro la primera vez que se guarde, o bien asegurarse de que algunos registros no se eliminen.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Conversión entre flujos de trabajo en tiempo real y flujos de trabajo en segundo plano  

 Puede cambiar un flujo de trabajo en tiempo real a un flujo de trabajo en segundo plano si hace clic en **Convertir en flujo de trabajo en segundo plano** en la barra de herramientas.  
  
 Puede cambiar un flujo de trabajo en segundo plano a un flujo de trabajo en tiempo real si hace clic en **Convertir en flujo de trabajo en tiempo real** en la barra de herramientas. Si el flujo de trabajo en segundo plano usa condiciones de espera, dejará de ser válido y no podrá activarlo hasta que quite la condición de espera.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Inicio de flujos de trabajo en tiempo real antes o después de los cambios de estado  

 Al configurar **Opciones para procesos automáticos** para flujos de trabajo en tiempo real, las opciones **Iniciar al** del evento de cambios estado le permiten seleccionar **Después de** o **Antes** para cuando cambie el estado. La opción predeterminada es **Después de**.  
  
 Si selecciona **Antes**, quiere que la lógica del flujo de trabajo se aplique antes de que se guarden los datos que cambian el estado. Esto le brinda la capacidad de comprobar los valores antes de que se aplique otra lógica después de la operación y evitar que se ejecute lógica adicional. Por ejemplo, puede tener lógica adicional en un complemento o una acción de flujo de trabajo personalizado que podría iniciar acciones en otro sistema. Al detener el procesamiento adicional, puede evitar casos en los que se vean afectados los sistemas externos. La aplicación de flujos de trabajo en tiempo real antes de este evento también significa que no es necesario "revertir" otras acciones de flujo de trabajo o complemento que es posible que hayan guardado datos cuando se cancela la operación.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Uso de la acción Detener flujo de trabajo con flujos de trabajo en tiempo real  

 Al aplicar una acción **Detener flujo de trabajo** en un flujo de trabajo tiene la opción de especificar una condición de estado que puede ser **Correcto** o **Cancelado**. Al establecer el estado en Cancelado, se evita la operación. Se mostrará un mensaje de error al usuario con el texto del mensaje de estado de la acción de detención con el encabezado **Error de proceso de negocio**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Creación de lógica de negocios personalizada mediante procesos](guide-staff-through-common-tasks-processes.md)   
 [Información general de los procesos de flujo de trabajo](workflow-processes.md)   
 [Supervisión y administración de procesos de flujo de trabajo](monitor-manage-processes.md)   
 [Procedimientos recomendados para los procesos de flujo de trabajo](best-practices-workflow-processes.md)
