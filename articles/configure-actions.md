---
title: Configurar acciones para flujos de trabajo en Power Apps | MicrosoftDocs
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
ms.openlocfilehash: cba86e3e10591bb5e1ac36a68840ff7954146329
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296975"
---
# <a name="configure-custom-actions-from-a-workflow"></a>Configurar acciones personalizadas desde un flujo de trabajo


Se puede habilitar una acción personalizada desde un flujo de trabajo sin escribir código. Más información: [Invocación de acciones personalizadas desde un flujo de trabajo](invoke-custom-actions-workflow-dialog.md).  
  
 También puede crear una acción para que un desarrollador la use en el código, o puede que tenga que modificar una acción que se haya definido previamente. Como procesos de flujo de trabajo, tenga en cuenta lo siguiente:  
  
-   ¿Qué debe hacer la acción?  
  
-   ¿En qué condiciones debe llevarse a cabo la acción?  
  
 
A diferencia de los procesos de flujo de trabajo, no necesita establecer las opciones siguientes:  
  
- **Iniciar al**: las acciones se inician si el código llama al mensaje generado para ellas.  
  
- **Ámbito**: las acciones se ejecutan siempre en el contexto del usuario que llama.  
  
- **Ejecutar en segundo plano**: las acciones son siempre flujos de trabajo en tiempo real.  
  
Las acciones también tienen algo de lo que carecen los procesos de flujo de trabajo: argumentos de entrada y salida. Más información: [Definición de argumentos de proceso](configure-actions.md#BKMK_DefineProcessArgs)  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Creación de una acción  
  
> [!IMPORTANT]
>  Si va a crear una acción para incluirla como parte de una solución que se va a distribuir, puede crearla en el contexto de la solución. Vaya a **[Configuración](/powerapps/maker/model-driven-apps/advanced-navigation#settings)** > **Soluciones** y busque la solución no administrada de la que esta acción va a formar parte. A continuación, en la barra de menú, seleccione **Nuevo** > **Proceso**. De este modo se asegura que el prefijo de personalización asociado con el nombre de la acción será coherente con otros componentes de la solución. Después de crear la acción, no puede cambiar el prefijo.  
  
 Como los procesos de flujo de trabajo, las acciones tienen las siguientes propiedades en el cuadro de diálogo **Crear proceso**.  
  
 **Nombre del proceso**  
 Tras escribir el nombre del proceso, se creará un nombre único para él quitando espacios o caracteres especiales del nombre del proceso.  
  
 **Categoría**  
 Esta propiedad establece que se trata de un proceso de acción. No se puede cambiar una vez guardado el proceso.  
  
 **Entidad**  
 Con los procesos de acciones, puede seleccionar una entidad para proporcionar contexto para el flujo de trabajo igual que con otros tipos de procesos, pero también tiene la opción de elegir **Ninguno (global)**. Use esta opción si la acción no requiere el contexto de una entidad específica. No se puede cambiar una vez guardado el proceso.  
  
 **Tipo**  
 Use esta propiedad para elegir entre crear una nueva acción desde cero o partir de una plantilla existente.  
  
<a name="edit"></a>   
## <a name="edit-an-action"></a>Editar una acción  
 Debe desactivar los procesos para poder modificarlas.  
  
 Puede editar una acción que se creó como parte de una solución no administrada o se incluyó en una solución instalada en la organización. Si la solución es una solución administrada, es posible que no pueda editarla. El editor de soluciones puede modificar las propiedades administradas para que la acción instalada con una solución administrada no se pueda editar.  
  
 Cuando se guarda una acción, se genera un nombre único basándose en el nombre del proceso. Este nombre único tiene el prefijo de personalización agregado desde el editor de soluciones. Este es el nombre del mensaje que un desarrollador usará en el código.  
  
 Al editar una acción tiene las siguientes opciones:  
  
 **Nombre del proceso**  
 Una vez creado el proceso y generado el nombre único a partir del nombre del proceso, puede modificar el nombre del proceso. Es posible que quiera implementar una convención de nomenclatura para que sea más fácil encontrar procesos específicos.  
  
 **Nombre único**  
 Cuando se guarda una acción, se genera un nombre único basándose en el nombre del proceso. Este nombre único tiene el prefijo de personalización de editor de soluciones agregado. Este es el nombre del mensaje que un desarrollador usará en el código. No cambie este nombre único si el proceso se ha activado y el código existe en espera de llamar a la acción con este nombre.  
  
> [!IMPORTANT]
>  Una vez activada la acción y el código está escrito para usar un nombre único, el nombre único no se debe cambiar sin cambiar también el código que le hace referencia.  
  
 **Habilitar reversión**  
 Generalmente, los procesos que admiten transacciones "desharán" (o revertirán) la operación completa si alguna parte falla. Hay algunas excepciones a esto. Algunas acciones que los desarrolladores pueden hacer en el código iniciado por la acción podrían no ser compatibles con las transacciones. Por ejemplo, si el código realiza acciones en otros sistemas que estén fuera del ámbito de la transacción. Estas pueden revertirse ejecutando la acción en una aplicación. Algunos mensajes de la plataforma no admiten transacciones. No obstante, todo lo que puede realizar con la interfaz de usuario de la acción admitirá transacciones. Todas las acciones que forman parte de un flujo de trabajo en tiempo real se consideran en la transacción, pero con las acciones tiene la opción de descartar esto.  
  
 Debería consultar con el programador que usará este mensaje para determinar si debe estar en la transacción o no. Normalmente, una acción debe estar en la transacción si las acciones realizadas por el proceso de negocio no tienen sentido, a menos que todas se completen correctamente. El ejemplo clásico consiste en transferir fondos entre dos cuentas bancarias. Si se retiran fondos de una cuenta debe depositarlos en la otra. Si una acción falla, deben fallar ambas.  
  
> [!NOTE]
>  No puede habilitar la reversión si una acción personalizada se invoca directamente desde un flujo de trabajo. Puede habilitar la reversión si una acción se desencadena por un mensaje de servicios web de Power Apps.  
  
 **Activar como**  
 Como todos los procesos, puede activar el proceso como una plantilla y usarlo como punto de partida avanzado para los procesos que sigan un modelo similar.  
  
 **Definir argumentos de procesos**  
 En este área, se especifican los datos que la acción espera iniciar y los datos que se transferirán fuera de la acción. Más información: [Definición de argumentos de proceso](configure-actions.md#BKMK_DefineProcessArgs)  
  
 **Agregar fases, condiciones y acciones**  
 Al igual que otros procesos, se especifican qué acciones se van a realizar y cuándo. Más información: [Adición de fases, condiciones y acciones](configure-actions.md#BKMK_AddStagesConditionsAndActions)

<a name="BKMK_DefineProcessArgs"></a>   
### <a name="define-process-arguments"></a>Definición de argumentos de proceso  
 Cuando un desarrollador usa un mensaje, puede empezar con algunos datos que se pueden transferir al mensaje. Por ejemplo, para crear un nuevo registro de caso, puede ser el valor de título de caso que se transfiere como un argumento de entrada.  
  
 Cuando finalice el mensaje, el programador puede necesitar pasar algunos datos que han cambiado o se han generado con el mensaje a otra operación en su código. Estos datos son el argumento de salida.  
  
 Los argumentos de entrada y de salida deben tener un nombre, un tipo y determinada información sobre si el argumento siempre es obligatorio. También puede proporcionar una descripción.  
  
 El nombre del mensaje y la información de todos los argumentos de proceso representan la "firma" del mensaje. Después de activar una acción y de empezarla a usar en código, la firma no debe cambiar. Si esta firma cambia, cualquier código que use el mensaje generará un error. La única excepción a esto sería cambiar uno de los parámetros para que no sea siempre obligatorio.  
  
 Puede cambiar el orden de los argumentos clasificándolos o moviéndolos arriba o abajo porque los argumentos se identifican por el nombre, no por el orden. Además, el cambio de la descripción no interrumpirá el código que utiliza el mensaje.  
  
#### <a name="action-process-argument-types"></a>Tipos de argumento de proceso de acción  
 La siguiente tabla describe los tipos de argumento de proceso de acción.  
  
|Tipo|Descripción|  
|----------|-----------------|  
|Boolean|Un valor `true` o `false`.|  
|DateTime|Un valor que almacena la información de fecha y hora.|  
|Decimal|Un valor numérico con precisión decimal. Se usa cuando la precisión es extremadamente importante.|  
|Entidad|Un registro para la entidad especificada. Al seleccionar Entidad, la lista desplegable se activa y permite seleccionar el tipo de entidad.|  
|EntityCollection|Una recopilación de registros de la entidad.|  
|EntityReference|Un objeto que contiene el nombre, el identificador y el tipo de registro de una entidad que lo identifica de forma única. Al seleccionar EntityReference, la lista desplegable se activa y permite seleccionar el tipo de entidad.|  
|Flotante|Un valor numérico con precisión decimal. Se utiliza cuando los datos vienen de una medida que no es absolutamente exacta.|  
|Entero|Un número entero.|  
|Dinero|Un valor que almacena los datos sobre una cantidad de dinero.|  
|Picklist|Un valor que representa una opción para un atributo OptionSet.|  
|Cadena|Un valor de texto.|  
  
> [!NOTE]
> Los valores de argumento **EntityCollection** no se pueden definir en la interfaz de usuario para las condiciones o acciones. Se proporcionan para que los desarrolladores los usen en código personalizado. Más información: [Crear acciones propias](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Adición de fases y pasos  
 Las acciones son un tipo de proceso muy similar a los flujos de trabajo en tiempo real. Todos los pasos que se pueden usar en flujos de trabajo en tiempo real se pueden usar en acciones. Para obtener más información acerca de los pasos que se pueden usar en los flujos de trabajo en tiempo real y las acciones, consulte [Fases y pasos del flujo de trabajo](configure-workflow-steps.md).  
  
 Además de los pasos que se pueden usar para los flujos de trabajo en tiempo real, las acciones también tienen el paso **Asignar valor**.   En las acciones, solo se pueden usar para definir argumentos de salida. Puede usar al Asistente de formulario para establecer los argumentos de salida en valores específicos o, más probablemente, en valores del registro sobre el que se ejecuta la acción, registros relacionados con ese registro con una relación varios a uno, registros creados en un paso anterior, o bien valores que forman parte del propio proceso.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Acciones](actions.md)  

 [Invocar acciones personalizadas desde un flujo de trabajo](invoke-custom-actions-workflow-dialog.md)   
 [Supervisión de flujos de trabajo y acciones en tiempo real](monitor-manage-processes.md#BKMK_MonitorSyncWorkflows)
 
 
