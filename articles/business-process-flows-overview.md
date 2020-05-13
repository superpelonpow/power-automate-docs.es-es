---
title: Introducción a los flujos de proceso de negocio | Microsoft Docs
ms.custom: ''
ms.date: 05/06/2019
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: 4469877e-bb95-481a-bc52-c9746f937ce5
caps.latest.revision: 16
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9d3ded6a38d45fa97a206abdf0ee5d89d2255124
ms.sourcegitcommit: 7a42629c7bc15208c5a9d692ab89616fc0aa40cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82973077"
---
# <a name="business-process-flows-overview"></a>Introducción a los flujos de proceso de negocio


Puede ayudar a garantizar que los usuarios escriban los datos de forma coherente y sigan los mismos pasos cada vez que trabajan con un cliente mediante la creación de un flujo de proceso de negocio. Por ejemplo, es posible que quiera crear un flujo de proceso de negocio para que todos los usuarios controlen las solicitudes de servicio de cliente del mismo modo, o bien para requerir que el personal obtenga la aprobación de una factura antes de enviar un pedido. Los flujos de proceso de negocio usan la misma tecnología subyacente que otros procesos, pero las funcionalidades que proporcionan son muy diferentes a las de otras características que usan los procesos. Para obtener información sobre cómo crear o modificar un flujo de proceso de negocio, vea [Creación de un flujo de proceso de negocio](create-business-process-flow.md).  
  
 [Vea un vídeo corto (4:49) sobre los flujos de proceso de negocio.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>Cuándo usar los flujos de proceso de negocio  
Los flujos de proceso de negocio proporcionan una guía para que los usuarios realicen su trabajo. Proporcionan una experiencia de usuario más eficaz que guía a los usuarios a través de los procesos que la organización ha definido para las interacciones que se deben hacer avanzar a algún tipo de conclusión. Esta experiencia de usuario se puede adaptar para que usuarios con distintos roles de seguridad puedan tener la experiencia que mejor se adapte al trabajo que realizan.  
  
 Puede usar flujos de proceso de negocio para definir un conjunto de pasos que los usuarios pueden seguir para llegar a un resultado deseado. Estos pasos proporcionan un indicador visual que indica a los usuarios en qué parte del proceso de negocio se encuentran. Los flujos de proceso de negocio reducen la necesidad de aprendizaje, ya que no es necesario que los usuarios se centren en qué entidad deberían usar. Pueden permitir que el proceso les guíe. Puede configurar flujos de proceso de negocio para admitir metodologías de venta comunes que pueden ayudar a los grupos de ventas a obtener mejores resultados. Para los grupos de servicio, los flujos de proceso de negocio pueden ayudar a los empleados nuevos a ponerse al día más rápidamente y evitar errores que podrían dar lugar a la insatisfacción de los clientes.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>¿Qué pueden hacer los flujos de proceso de negocio?  
 Con los flujos de proceso de negocio, se define un conjunto de *fases* y *pasos* que, después, se muestran en un control en la parte superior del formulario.  
  
 ![Proceso de negocio con fases](media/business-process-stages.png "Proceso de negocio con fases")  
  
 Cada fase contiene un grupo de pasos. Cada paso representa un campo donde se pueden escribir datos. Los usuarios avanzan a la fase siguiente por medio del botón **Fase siguiente**. Puede hacer que un paso sea obligatorio para que los usuarios tengan que escribir datos para el campo correspondiente antes de poder continuar a la fase siguiente. Normalmente, esto se denomina "puerta de fase".  
  
 Los flujos de proceso de negocio parecen relativamente simples en comparación con otros tipos de procesos, ya que no proporcionan ninguna lógica de negocios condicional o automatización más allá de proporcionar la experiencia simplificada para la entrada de datos y controlar la entrada en fases. Pero al combinarlos con otros procesos y personalizaciones, pueden desempeñar un papel importante a la hora de ahorrar tiempo para los usuarios, reducir los costos de aprendizaje y aumentar la adopción del usuario.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Flujos de proceso de negocio integrados con otras personalizaciones  
 Cuando usted o el usuario escribe datos mediante flujos de proceso de negocio, los cambios de los datos también se aplican a los campos de formulario para que la automatización proporcionada por las reglas de negocios o los scripts de formulario se pueda aplicar de forma inmediata. Se pueden agregar pasos que establezcan valores para los campos que no están presentes en el formulario y estos campos se agregarán al modelo de objetos de `Xrm.Page` que se usa para los scripts de formulario. Los flujos de trabajo que se inicien por los cambios realizados en los campos incluidos en un flujo de proceso de negocio se aplicarán cuando se guarden los datos del formulario. Si la automatización la aplica un flujo de trabajo en tiempo real, los cambios serán visibles inmediatamente para el usuario cuando se actualicen los datos del formulario después de guardar el registro.  
  
 Aunque el control de flujo de proceso de negocio en el formulario no proporciona ninguna programación del lado cliente directa, los cambios aplicados por las reglas de negocios o los scripts de formulario se aplican automáticamente a los controles de flujo de proceso de negocio. Si oculta un campo en un formulario, ese campo también se ocultará en el control de flujo de proceso de negocio. Si establece un valor mediante reglas de negocios o scripts de formulario, ese valor se establecerá en el flujo de proceso de negocio.  
  
### <a name="concurrent-process-flows"></a>Flujos de proceso simultáneos  
 Los flujos de proceso de negocio simultáneos permiten a los personalizadores configurar varios procesos de negocio y asociarlos con el mismo registro inicial. Los usuarios pueden cambiar entre varios procesos de negocio que se ejecuten de forma simultánea y reanudar su trabajo en la fase del proceso en la que se encontraban.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Flujos de proceso de negocio del sistema  
 Se incluyen los flujos de proceso de negocio siguientes. Para entender cómo funcionan los flujos de proceso de negocio, revise estos flujos de proceso de negocio del sistema:  
  
-   Proceso de cliente potencial a ventas de la oportunidad  
  
-   Proceso de ventas de la oportunidad  
  
-   Proceso de teléfono a caso  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Varias entidades en flujos de proceso de negocio  
 Puede usar un flujo de proceso de negocio para una sola entidad o abarcar varias entidades. Por ejemplo, puede tener un proceso que comienza con una oportunidad, continúa con una oferta, un pedido y después una factura, antes de volver para cerrar la oportunidad en último lugar.  
  
 Puede diseñar flujos de proceso de negocio que conecten entre sí los registros de hasta cinco entidades diferentes en un único proceso, para que los usuarios de la aplicación puedan centrarse en el flujo de su proceso en lugar de la entidad en la que están trabajando. Se pueden desplazar con más facilidad entre los registros de la entidad relacionada.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Varios flujos de proceso de negocio disponibles por cada entidad  
 No todos los usuarios de una organización pueden seguir el mismo proceso y cada condición puede requerir que se aplique un proceso distinto. Puede tener hasta 10 flujos de proceso de negocio activos por cada entidad para proporcionar procesos adecuados para cada situación.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Control del flujo de proceso de negocio que se va a aplicar  
 Puede asociar flujos de proceso de negocio con roles de seguridad para que solo los usuarios con esos roles de seguridad puedan verlos o usarlos. También puede establecer el orden de los flujos de proceso de negocio para controlar cuáles se establecerán de forma predeterminada. Esto funciona de la misma manera que la definición de varios formularios para una entidad.  
  
 Cuando alguien crea un registro de entidad, la lista de definición de procesos de negocio activos disponibles se filtra por el rol de seguridad del usuario. La primera definición de proceso de negocio activado disponible para el rol de seguridad del usuario según la lista de orden de procesos es la que se aplica de forma predeterminada. Si hay más de una definición de proceso de negocio activo, los usuarios pueden cargar otra desde el cuadro de diálogo Cambiar proceso. Cada vez que los procesos se cambian, el que se representa actualmente pasa a segundo plano y se reemplaza por el que se ha seleccionado, pero mantiene su estado y se puede cambiar de nuevo. Cada registro puede tener varias instancias de proceso asociadas (una para cada definición de flujo de proceso de negocio diferente, hasta un total de 10). Al cargar el formulario, solo se representa un flujo de proceso de negocio. Cuando un usuario aplica otro proceso, ese proceso solo se puede cargar de forma predeterminada para ese usuario concreto.  
  
 Para asegurarse de que un proceso de negocio se carga de forma predeterminada para todos los usuarios (un comportamiento equivalente a "fijar" el proceso), se puede agregar un script de API cliente personalizado (recurso web) al cargar el formulario en el que se cargue de forma específica una instancia existente de proceso de negocio en función del identificador de la definición de proceso de negocio. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Consideraciones sobre los flujos de proceso de negocio  
 Solo puede definir flujos de proceso de negocio para las entidades que los admitan. También deberá tener en cuenta los límites para el número de procesos, fases y pasos que se pueden agregar.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Flujos de proceso de negocio que llaman a un flujo de trabajo  
 Puede llamar a flujos de trabajo a petición desde dentro de un flujo de proceso de negocio. Para configurarlo desde el nuevo Diseñador de flujos de proceso de negocio, arrastre un componente de flujo de trabajo a una fase del proceso o a la sección de flujos de trabajo globales. Para obtener más información sobre el empleo de flujos de trabajo en flujos de proceso de negocio, vea [Blog: Business process flow automation in Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/) (Blog: Automatización de flujos de proceso de negocio en Dynamics 365).  
  
 Cuando incluye un flujo de trabajo que quiere que se desencadene en la salida de fase de una fase del flujo de proceso de negocio, y esa fase es la última del flujo, el diseñador da la impresión de que el flujo de trabajo se desencadenará cuando que se haya completado la fase. Pero el flujo de trabajo no se desencadenará porque no tiene lugar una transición de fase. No recibirá una advertencia ni un error que le impida incluir el flujo de trabajo en la fase. Cuando un usuario interactúa con el flujo de proceso de negocio, finalizar o abandonar el proceso no produce una transición de fase y, por tanto, el flujo de trabajo no se desencadena. Considere los ejemplos siguientes:  
  
-   Crea un flujo de proceso de negocio con dos fases, S1 se conecta a S2, con un flujo de trabajo en la fase S2 y establece el desencadenador en **Salida de fase**.  
  
-   Crea un flujo de proceso de negocio con tres fases, S1 se conecta a S2 y después S2 se bifurca a S3. Incluye un flujo de trabajo en S2 y establece el desencadenador en **Salida de fase**.  
  
 El flujo de trabajo no se desencadenará en ninguno de los casos. Para solucionar este problema, puede agregar un flujo de trabajo global y agregarle el flujo de trabajo que quiere que se desencadene para que el flujo de trabajo se desencadene para el proceso de negocio empresarial en lugar de para una fase del proceso. Puede establecer el desencadenador de un flujo de trabajo global en Proceso abandonado o Proceso finalizado para que el flujo de trabajo se desencadene cuando un usuario abandone o complete el proceso de negocio.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>Entidades que pueden usar flujos de proceso de negocio  
 Todas las entidades personalizadas pueden usar flujos de proceso de negocio. Las entidades estándar siguientes también pueden usar flujos de proceso de negocio:  
  
-   Cuenta  
-   Cita  
-   Campaña  
-   Actividad de campaña  
-   Respuesta de la campaña  
-   Competidor  
-   Contacto  
-   Correo  
-   Derecho  
-   Fax  
-   Caso  
-   Factura  
-   Cliente potencial  
-   Carta  
-   Lista de marketing  
-   Oportunidad  
-   Llamada de teléfono  
-   Producto  
-   Elemento de lista de precios  
-   Oferta  
-   Cita periódica  
-   Documentación de ventas  
-   Actividad social  
-   Pedido  
-   Usuario  
-   Tarea  
-   Equipo  
  
 Para habilitar una entidad personalizada para flujos de proceso de negocio, active la casilla **Flujos de proceso de negocio (se crearán campos)** de la definición de la entidad. Tenga en cuenta que esta acción no se puede deshacer.  
  
> [!NOTE]
>  Si navega a la fase de flujo de proceso de negocio que contiene la entidad `Social Activity` y hace clic en el botón **Fase siguiente**, verá la opción **Crear**. Al hacer clic en **Crear**, se carga el formulario **Actividad social**. Pero como `Social Activity` no es válido para `Create` desde la interfaz de usuario de la aplicación, no se puede guardar el formulario y aparece el mensaje de error: "Error inesperado".  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Número máximo de procesos, fases y pasos  
 Para garantizar un rendimiento aceptable y la facilidad de uso de la interfaz de usuario, hay algunas limitaciones que debe tener en cuenta cuando vaya a usar flujos de proceso de negocio:  
  
-   No puede haber más de 10 procesos de flujo de proceso de negocio activos por entidad.  
  
-   Cada proceso no puede contener más de 30 fases.  
  
-   Los procesos de varias entidades no pueden contener más de 5 entidades.
  
## <a name="business-process-flow-entity-customization-support"></a>Compatibilidad con la personalización de entidades de flujo de proceso de negocio 

Introducidas en la actualización de la versión 9.0 de Dynamics 365 (en línea), las entidades de flujo de proceso de negocio pueden aparecer en el sistema para que los datos de registro de entidad puedan estar disponibles en paneles, vistas, gráficos y cuadrículas. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Uso de registros de entidad de flujo de proceso de negocio con paneles, vistas, gráficos y cuadrículas

Como los flujos de procesos de negocio están disponibles como una entidad, ahora puede usar búsquedas avanzadas, vistas, gráficos y paneles con origen en los datos de flujo de proceso de negocio para una entidad determinada, por ejemplo un cliente potencial o una oportunidad. Los administradores del sistema y los personalizadores pueden crear paneles, vistas, gráficos y cuadrículas de flujo de proceso de negocio personalizados similares a los que se crean con cualquier otra entidad.

Los flujos de proceso de negocio, como **Proceso de cliente potencial a ventas de la oportunidad**, aparecen como una entidad personalizable en el Explorador de soluciones.

![Explorador de soluciones con la entidad Proceso de cliente potencial a ventas de la oportunidad](media/bpf-lead-solution-explorer.png)

Para acceder a una vista de flujo de proceso de negocio predeterminada, abra el Explorador de soluciones, expanda **Entidades** > expanda el proceso que quiera, como **Proceso de cliente potencial a ventas de la oportunidad**, seleccione **Vistas**  y, después, seleccione la vista que quiera.

Hay disponibles varias vistas predeterminadas que puede ver como un gráfico, como la vista **Proceso de ventas de oportunidad activa**. 

![Vista Proceso de ventas de la oportunidad activa](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interacción con la entidad de flujo de proceso de negocio desde un flujo de trabajo
También puede interactuar con las entidades de flujo de proceso de negocio desde un flujo de trabajo. Por ejemplo, puede crear un flujo de trabajo para el registro de entidad Flujo de proceso de negocio para cambiar la Fase activa cuando se actualice un campo en el registro de entidad Oportunidad. Para obtener más información sobre cómo hacerlo, vea [Automate business process flow stages using workflows](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows) (Automatización de las fases de flujo de proceso de negocio mediante flujos de trabajo).

### <a name="run-business-process-flows-offline"></a>Ejecución de los flujos de procesos de negocio sin conexión

Puede usar los flujos de procesos de negocio sin conexión si se cumplen estas condiciones:

- El flujo del proceso de negocio se usa desde una aplicación de Power Apps.
- La aplicación Power Apps está habilitada para su uso sin conexión.
- El flujo de procesos de negocio tiene una sola entidad.

En concreto, los tres comandos que están disponibles para un flujo de proceso de negocio cuando la aplicación Power Apps está sin conexión son:

- Fase siguiente
- Fase anterior
- Fase Establecer como activo

### <a name="limitations-of-using-business-process-flow-entities"></a>Limitaciones del uso de entidades de flujo de proceso de negocio

- En la actualidad, no se pueden crear formularios personalizados para entidades en función de un flujo de proceso de negocio.
- Si una solución incluye una entidad de flujo de proceso de negocio, esta se debe agregar de forma manual a la solución antes de exportarla. En caso contrario, la entidad de flujo de proceso de negocio no se incluirá en el paquete de solución. Más información: [Crear y editar entidades](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-entities-solution-explorer)
- Al agregar una entidad Proceso a una aplicación controlada por modelos, la funcionalidad puede quedar limitada. Obtenga más información acerca de la [creación y edición de flujos de procesos de negocio](https://docs.microsoft.com/power-automate/create-business-process-flow). 

### <a name="next-steps"></a>Pasos siguientes  
 [Vea un vídeo corto (4:49) sobre los flujos de proceso de negocio](https://go.microsoft.com/fwlink/p/?linkid=842226)  
 [Crear un flujo de proceso de negocio](create-business-process-flow.md)  
 [Mejora de los flujos de proceso de negocio con ramas](enhance-business-process-flows-branching.md) <br/>
 [Whitepaper: Process Enablement with Dynamics 365](https://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf) (Notas del producto: Habilitación de procesos con Dynamics 365)</br>
