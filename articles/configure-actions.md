---
title: Configuración de acciones para flujos de trabajo de Power Apps | Microsoft Docs
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
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
caps.latest.revision: 19
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9157159a263bb2b8be41445aebb478fc6aa2ddb3
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74360564"
---
# <a name="configure-custom-actions-from-a-workflow"></a>Configuración de acciones personalizadas desde un flujo de trabajo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Se puede habilitar una acción personalizada desde un flujo de trabajo sin escribir código. Más información: [Invocación de acciones personalizadas desde un flujo de trabajo](invoke-custom-actions-workflow-dialog.md).  
  
 También puede crear una acción para que un desarrollador la use en el código, o puede que tenga que modificar una acción que se haya definido previamente. Como sucede con los procesos de flujo de trabajo, tenga en cuenta lo siguiente:  
  
-   ¿Qué debe hacer la acción?  
  
-   ¿En qué condiciones se debe realizar la acción?  
  
 
A diferencia de los procesos de flujo de trabajo, no es necesario establecer las opciones siguientes:  
  
- **Iniciar al**: las acciones se inician cuando el código llama al mensaje generado para ellas.  
  
- **Ámbito**: las acciones siempre se ejecutan en el contexto del usuario que realiza la llamada.  
  
- **Ejecutar en segundo plano**: las acciones siempre son flujos de trabajo en tiempo real.  
  
Las acciones también tienen algo de lo que carecen los procesos de flujo de trabajo: argumentos de entrada y salida. Más información: [Definición de argumentos de proceso](configure-actions.md#BKMK_DefineProcessArgs)  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Creación de una acción  
  
> [!IMPORTANT]
>  Si va a crear una acción para incluirla como parte de una solución que se va a distribuir, puede crearla en el contexto de la solución. Vaya a **[Configuración](/powerapps/maker/model-driven-apps/advanced-navigation#settings)**  > **Soluciones** y busque la solución no administrada de la que esta acción va a formar parte. Después, en la barra de menús, seleccione **Nuevo** > **Proceso**. Esto garantiza que el prefijo de personalización asociado con el nombre de la acción será coherente con otros componentes de la solución. Después de crear la acción, no se puede cambiar el prefijo.  
  
 Como sucede con los procesos de flujo de trabajo, las acciones tienen las propiedades siguientes en el cuadro de diálogo **Crear proceso**.  
  
 **Nombre del proceso**  
 Después de escribir un nombre para el proceso, se eliminan los espacios y caracteres especiales del nombre del proceso para crear un nombre único para él.  
  
 **Categoría**  
 Esta propiedad establece que se trata de un proceso de acción. No se puede cambiar después de guardar el proceso.  
  
 **Entidad**  
 Con los procesos de acciones, puede seleccionar una entidad para proporcionar contexto para el flujo de trabajo como con otros tipos de procesos, pero también tiene la opción de elegir **Ninguno (global)** . Úsela si la acción no requiere el contexto de una entidad específica. No se puede cambiar después de guardar el proceso.  
  
 **Tipo**  
 Use esta propiedad para elegir si va a crear una acción desde cero o a iniciarla a partir de una plantilla existente.  
  
<a name="edit"></a>   
## <a name="edit-an-action"></a>Edición de una acción  
 Antes de poder modificar los procesos, tendrá que desactivarlos.  
  
 Se puede modificar una acción creada como parte de una solución no administrada o incluida en una solución instalada en la organización. Si la solución es una solución administrada, es posible que no pueda modificarla. El editor de la solución tiene la opción de modificar las propiedades administradas para que la acción instalada con una solución administrada no se pueda modificar.  
  
 Cuando se guarda una acción, se genera un nombre único basado en el nombre del proceso. A este nombre único se le agrega el prefijo de personalización del editor de la solución. Este es el nombre del mensaje que el desarrollador usará en el código.  
  
 Al editar una acción dispone de las opciones siguientes:  
  
 **Nombre del proceso**  
 Después de crear el proceso y de que se genere el nombre único a partir del nombre del proceso, puede editar el nombre del proceso. Es posible que quiera aplicar una convención de nomenclatura para facilitar la búsqueda de procesos específicos.  
  
 **Nombre único**  
 Cuando se guarda una acción, se genera un nombre único basado en el nombre del proceso. A este nombre único se le agrega el prefijo de personalización del editor de la solución. Este es el nombre del mensaje que el desarrollador usará en el código. No cambie este nombre único si el proceso se ha activado y existe código que espera llamar a la acción con este nombre.  
  
> [!IMPORTANT]
>  Después de activar la acción y de escribir código para usar un nombre único, no se debe cambiar el nombre único sin cambiar también el código en el que se le hace referencia.  
  
 **Habilitar reversión**  
 Por lo general, los procesos que admiten las transacciones "deshacen" (o revierten) toda la operación si se produce un error en cualquier parte de ellos. Existen algunas excepciones a este comportamiento. Es posible que algunas acciones que los desarrolladores pueden realizar en el código iniciado por la acción no admitan las transacciones. Por ejemplo, si el código realiza acciones en otros sistemas que están fuera del ámbito de la transacción. La acción que se ejecuta en una aplicación no podrá revertir esas acciones. Algunos mensajes de la plataforma no admiten las transacciones. Pero todo lo que se puede hacer con la interfaz de usuario de la acción admitirá las transacciones. Todas las acciones que forman parte de un flujo de trabajo en tiempo real se tienen en cuenta en la transacción, pero con las acciones tiene la opción de rechazarlo.  
  
 Debe consultar con el desarrollador que va a usar este mensaje para determinar si se debe incluir o no en la transacción. Por lo general, una acción se debe incluir en la transacción si las acciones realizadas por el proceso de negocio no tienen sentido a menos que todas ellas se completen correctamente. El ejemplo clásico es la transferencia de fondos entre dos cuentas bancarias. Si retira fondos de una cuenta, tendrá que ingresarlos en la otra. Si se produce un error en una de ellas, se producirá en las dos.  
  
> [!NOTE]
>  La reversión no se puede habilitar si una acción personalizada se invoca directamente desde dentro de un flujo de trabajo. Se puede habilitar la reversión si un mensaje de los servicios web de Power Apps desencadena una acción.  
  
 **Activar como**  
 Al igual que todos los procesos, se puede activar el proceso como una plantilla y usarla como un punto de partida avanzado para los procesos que siguen un patrón similar.  
  
 **Definición de argumentos de proceso**  
 En este área, se especifican los datos que la acción espera iniciar y los datos que se transferirán fuera de la acción. Más información: [Definición de argumentos de proceso](configure-actions.md#BKMK_DefineProcessArgs)  
  
 **Adición de fases, condiciones y acciones**  
 Al igual que otros procesos, se especifican qué acciones se van a realizar y cuándo. Más información: [Adición de fases, condiciones y acciones](configure-actions.md#BKMK_AddStagesConditionsAndActions)

<a name="BKMK_DefineProcessArgs"></a>   
### <a name="define-process-arguments"></a>Definición de argumentos de proceso  
 Cuando un desarrollador usa un mensaje, puede comenzar con algunos datos que puede pasar al mensaje. Por ejemplo, para crear un registro de caso, es posible que el valor de título del caso se pase como un argumento de entrada.  
  
 Cuando finalice el mensaje, es posible que el desarrollador tenga que pasar datos que se han modificado o que el mensaje ha generado para otra operación en el código. Estos datos son el argumento de salida.  
  
 Los argumentos de entrada y salida deben tener un nombre, un tipo y cierta información sobre si el argumento siempre es necesario. También se puede proporcionar una descripción.  
  
 El nombre del mensaje y la información sobre todos los argumentos de proceso representan la "firma" del mensaje. Después de activar una acción y de que se use en el código, no se debe cambiar la firma. Si esta firma cambia, se producirá un error en cualquier código que use el mensaje. La única excepción podría ser cambiar uno de los parámetros para que no sea necesario siempre.  
  
 Los argumentos se pueden ordenar o mover hacia arriba o hacia abajo para cambiar el orden, porque los argumentos se identifican por el nombre, no por el orden. Además, cambiar la descripción no interrumpe el código en el que se usa el mensaje.  
  
#### <a name="action-process-argument-types"></a>Tipos de argumento de procesos de acción  
 En la tabla siguiente se describen los tipos de argumento de los procesos de acción.  
  
|Tipo|Descripción|  
|----------|-----------------|  
|Booleano|Un valor `true` o `false`.|  
|DateTime|Un valor que almacena información de fecha y hora.|  
|Decimal|Un valor numérico con precisión decimal. Se usa cuando la precisión es extremadamente importante.|  
|Entity|Un registro de la entidad especificada. Cuando se selecciona Entity, se habilita la lista desplegable y se puede seleccionar el tipo de entidad.|  
|EntityCollection|Una colección de registros de entidad.|  
|EntityReference|Un objeto que contiene el nombre, el identificador y el tipo de un registro de entidad que la identifica de forma única. Cuando se selecciona EntityReference, se habilita la lista desplegable y se puede seleccionar el tipo de entidad.|  
|Float|Un valor numérico con precisión decimal. Se usa cuando los datos proceden de una medida que no es totalmente precisa.|  
|Integer|Un número entero.|  
|Money|Un valor que almacena datos sobre una cantidad de dinero.|  
|Picklist|Un valor que representa una opción para un atributo OptionSet.|  
|String|Un valor de texto.|  
  
> [!NOTE]
> Los valores del argumento **EntityCollection** no se pueden establecer en la interfaz de usuario para condiciones o acciones. Se proporcionan para que los desarrolladores los usen en código personalizado. Más información: [Crear acciones propias](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Adición de fases y pasos  
 Las acciones son un tipo de proceso muy similar a los flujos de trabajo en tiempo real. Todos los pasos que se pueden usar en los flujos de trabajo en tiempo real se pueden usar en las acciones. Para obtener información sobre los pasos que se pueden usar para los flujos de trabajo en tiempo real y las acciones, vea [Fases y pasos de flujo de trabajo](configure-workflow-steps.md).  
  
 Además de los pasos que se pueden usar para los flujos de trabajo en tiempo real, las acciones también tienen el paso **Asignar valor**.  En las acciones, solo se pueden usar para definir argumentos de salida. Puede usar al Asistente de formulario para establecer los argumentos de salida en valores específicos o, más probablemente, en valores del registro sobre el que se ejecuta la acción, registros relacionados con ese registro con una relación varios a uno, registros creados en un paso anterior, o bien valores que forman parte del propio proceso.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Acciones](actions.md)  

 [Invocación de acciones personalizadas desde un flujo de trabajo](invoke-custom-actions-workflow-dialog.md)   
 [Supervisión de flujos de trabajo y acciones en tiempo real](monitor-manage-processes.md#BKMK_MonitorSyncWorkflows)
 
 
