---
title: Información general sobre flujos de proceso de negocio | MicrosoftDocs
ms.custom: ''
ms.date: 12/12/2019
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
ms.openlocfilehash: a6e936b833f6b1e1d6cf6e050031969d41e40de6
ms.sourcegitcommit: 31692af25f91af60cf77572edcb0c986602dc9a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "3298889"
---
# <a name="business-process-flows-overview"></a>Información general sobre flujos de proceso de negocio


Puede ayudar a asegurarse de que los usuarios especifiquen datos de manera coherente y siguen los mismos pasos cada vez que trabajan con un cliente mediante la creación de un flujo de proceso de negocio. Por ejemplo, es posible que quiera crear un flujo de proceso de negocio para que todos los usuarios controlen las solicitudes del servicio de atención al cliente de la misma manera, o bien para exigir que los usuarios obtengan la aprobación de una factura antes de enviar un pedido. Los flujos de proceso de negocio usan la misma tecnología subyacente que otros procesos, pero las funciones que proporcionan son muy diferentes de otras características que usan los procesos. Para obtener más información sobre cómo crear o editar un flujo de proceso de negocio, consulte [Crear un flujo de proceso de negocio](create-business-process-flow.md).  
  
 [Vea un vídeo corto (4:49) sobre flujos de proceso de negocio.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>Motivos para usar flujos de proceso de negocio  
Los flujos de proceso de negocio proporcionan una guía para que la gente realice el trabajo. Proporcionan una experiencia de usuario simplificada que guía a los usuarios por los procesos que su organización ha definido para las interacciones que deben avanzarse a una conclusión de algún tipo. Esta experiencia del usuario se puede adaptar para que la gente con diferentes roles de seguridad pueda tener una experiencia que se adapte mejor al trabajo que hacen.  
  
 Use flujos de proceso de negocio para definir un conjunto de pasos para que la gente siga para obtener el resultado deseado. Estos pasos ofrecen un indicador visual que especifica en qué parte del proceso empresarial se encuentra cada cual. Los flujos de proceso de negocio reducen la necesidad de entrenamiento porque no es necesario que los nuevos usuarios se centren en la entidad que deben usar. Pueden dejar que el proceso les guíe. Puede configurar los flujos de proceso de negocio para respaldar aspectos comunes de ventas que pueden ayudar a los grupos de ventas a obtener mejores resultados. Para los grupos de servicios, los flujos de proceso de negocio pueden ayudar al nuevo personal a adaptarse al ritmo más rápido y a evitar errores que pueden provocar clientes insatisfechos.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>¿Qué pueden hacer los flujos de proceso de negocio?  
 Con los flujos de proceso de negocio, puede definir un conjunto de *fases* y *pasos* que se mostrarán a continuación en un control en la parte superior del formulario.  
  
 ![Proceso de negocio con fases](media/business-process-stages.png "Proceso empresarial con fases")  
  
 Cada fase contiene un grupo de pasos. Cada paso representa un campo donde pueden introducirse los datos. Los usuarios avanzan a la siguiente fase con el botón **Fase siguiente**. Puede crear un paso necesario para que la gente deba especificar los datos en el campo correspondiente para poder pasar a la siguiente fase. Esto habitualmente se denomina "puerta de fase".  
  
 Los flujos de proceso de negocio parecen relativamente simples comparado con otros tipos de procesos porque no se ofrecen ninguna lógica de negocio condicional o automatización además de ofrecer la experiencia simplificada de entrada de datos y el control de la entrada en las fases. Sin embargo, cuando se combinan con otros procesos y personalizaciones, pueden tener un rol importante para ahorrar tiempo a los usuarios, reducir costos de aprendizaje y aumentar la adopción por parte del usuario.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Flujos de proceso de negocio integrados con otras personalizaciones  
 Cuando usted o el usuario especifican datos mediante flujos de proceso de negocio, los cambios de los datos también se aplican a los campos de formulario para aplicar una automatización que suministra reglas de negocio o scripts de formularios inmediatamente. Los pasos pueden agregarse a los valores definidos para los campos que no se encuentran presentes en el formulario y estos campos se agregarán al modelo de objetos `Xrm.Page` usado para scripts de formularios. Cualquier flujo de trabajo que esté iniciado por los cambios en los campos incluidos en un flujo de proceso de negocio se aplicará cuando se guarden datos en el formulario. Si la automatización la aplica un flujo de trabajo en tiempo real, los cambios serán visibles inmediatamente para el usuario cuando los datos del formulario se actualicen después de guardar el registro.  
  
 Aunque el control del flujo de proceso de negocio del formulario no proporciona ninguna programabilidad de cliente directa, los cambios que se aplican por reglas de negocio o scripts de formularios se aplican automáticamente a los controles del flujo de proceso de negocio. Si oculta un campo en un formulario, ese campo también estará oculto en el control del flujo de proceso de negocio. Si establece un valor mediante reglas de negocio o scripts de formularios, el valor se establecerá en el flujo de proceso de negocio.  
  
### <a name="concurrent-process-flows"></a>Flujos de proceso simultáneos  
 Los flujos de proceso de negocio simultáneos permiten a los personalizadores configurar varios procesos de negocio y asociarlos con el mismo registro inicial. Los usuarios pueden cambiar entre varios procesos de negocio que se ejecutan simultáneamente, y reanudar su trabajo en la fase del proceso en la que estaban.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Flujos de proceso de negocio del sistema  
 Se incluyen los siguientes flujos de proceso de negocio. Para comprender cómo funcionan los flujos de procesos de negocio, revise estos flujos de procesos de negocio del sistema:  
  
-   Proceso de cliente potencial a oportunidad de venta  
  
-   Proceso de oportunidad de venta  
  
-   Proceso de teléfono a caso  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Varias entidades en flujos de proceso de negocio  
 Puede usar un flujo de proceso de negocio para una sola entidad o abarcar varias entidades. Por ejemplo, puede tener un proceso que empiece con una oportunidad, continúe a una oferta, un pedido y después a una factura, para acabar volviendo a cerrar la oportunidad.  
  
 Puede diseñar flujos de proceso de negocio que relacionen los registros de hasta cinco entidades distintas en un solo proceso para que las personas que usan la aplicación puedan concentrarse en el flujo del proceso en lugar de en la entidad en la que trabajan. Pueden desplazarse más fácilmente entre los registros relacionados de la entidad.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Varios flujos de proceso de negocio están disponibles por entidad  
 No todos los usuarios de una organización pueden seguir el mismo proceso y varias condiciones pueden requerir que se aplique otro proceso. Puede tener hasta 10 flujos de proceso de negocio activos por entidad para proporcionar los procesos adecuados para diferentes situaciones.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Controlar el flujo de proceso de negocio que se aplicará  
 Puede asociar los flujos de procesos de negocio con roles de seguridad para que solo los usuarios con esos roles de seguridad puedan consultarlos o usarlos. También puede establecer el orden de los flujos de proceso de negocio de modo que pueda controlar el flujo de proceso de negocio que se establecerá de forma predeterminada. Esto funciona de la misma forma en que se definen los formularios múltiples para una entidad.  
  
 Al crear un nuevo registro de entidad, la lista de definiciones de procesos de negocio activos disponible se filtra según el rol de seguridad del usuario. La primera definición de proceso de negocio activada disponible para el rol de seguridad del usuario según la lista de orden del proceso es la que se aplica de forma predeterminada. Si hay disponibles varias definiciones de proceso de negocio activas, los usuarios pueden cargar otra desde el cuadro de diálogo Cambiar proceso. Siempre que se intercambian los procesos, el que se está usando actualmente pasa al segundo plano y se reemplaza por el seleccionado, pero mantiene su estado y se pueden volver a intercambiar. Cada registro puede tener varias instancias de proceso asociadas (cada una de ellas para una definición de flujo de proceso de negocio diferente, hasta un total de 10). Al cargar un formulario, se representa solo un flujo de proceso de negocio. Cuando un usuario aplica un proceso diferente, dicho proceso se puede cargar solo de forma predeterminada para ese usuario determinado.  
  
 Para asegurarse de que un proceso de negocio se cargue de forma predeterminada para todos los usuarios (comportamiento equivalente a “anclar” el proceso), se puede agregar un script de API de cliente personalizado (recurso web) en la carga del formulario que cargue específicamente una instancia de proceso de negocio existente en función del ID de la definición del proceso de negocio. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Consideraciones sobre el flujo de proceso de negocio  
 Puede definir flujos de proceso de negocio solo para esas entidades que las admitan. También deberá tener en cuenta los límites para el número de procesos, fases y pasos que se pueden agregar.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Flujos de proceso de negocio que llaman a un flujo de trabajo  
 Puede llamar a flujos de trabajo a petición desde dentro de un flujo de proceso de negocio. Puede configurar esto en el nuevo diseñador de flujo de proceso de negocio arrastrando un componente de flujo de trabajo a una fase del proceso o la sección Flujos de trabajo globales. Para obtener más información acerca del uso de flujos de trabajo en flujos de proceso de negocio, consulte [Blog: Automatización de flujos de proceso de negocio en Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/).  
  
 Cuando incluye un flujo de trabajo que desea desencadenar en la salida de una fase en el flujo de proceso de negocio, y esa fase es la última fase del flujo, el diseñador da la impresión de que el flujo de trabajo se desencadenará cuando se complete esa fase. Sin embargo, el flujo de trabajo no se desencadenará porque no se produce una transición de fase. No recibirá una advertencia o un error que le impida incluir el flujo de trabajo en la fase. Cuando un usuario interactúa con el flujo de proceso de negocio, al acabar o abandonar el proceso no se produce una transición de fase y, por tanto, el flujo de trabajo no se desencadena. Tenga en cuenta los siguientes ejemplos:  
  
-   Puede crear un flujo de proceso de negocio con dos fases, S1 se conecta a S2, con un flujo de trabajo en la fase S2 y establece el desencadenador en **Salida de fase**.  
  
-   Puede crear un flujo de proceso de negocio con tres fases, S1 se conecta a S2, después S2 se bifurca a S3. Incluya también un flujo de trabajo en S2 y establezca el desencadenador en **Salida de fase**.  
  
 El flujo de trabajo no se desencadenará en ningún caso. Para solucionar este problema, puede agregar un flujo de trabajo global y agregarle el flujo de trabajo que desea desencadenar de modo que el flujo de trabajo se desencadene para el proceso de negocio en lugar para una fase del proceso. Puede establecer el desencadenador de un flujo de trabajo global en Proceso abandonado o Proceso finalizado para que el flujo de trabajo se desencadene cuando un usuario abandone o complete el proceso de negocio.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>Entidades que pueden usar flujos de proceso de negocio  
 Todas las entidades personalizadas pueden usar flujos de proceso de negocio. Las entidades estándar siguientes también pueden usar flujos de proceso de negocio:  
  
-   Cuenta  
-   Cita  
-   Campaña  
-   Actividad de campaña  
-   Respuesta de campaña  
-   Competidor  
-   Contacto  
-   Enviar por correo electrónico  
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
-   Orden  
-   Usuario  
-   Tarea  
-   Equipo  
  
 Para habilitar una entidad personalizada para flujos de procesos de negocio, active la casilla **Flujos de proceso de negocio (se crearán campos)** en la definición de la entidad. Tenga en cuenta que no se puede deshacer esta acción.  
  
> [!NOTE]
>  Si se desplaza a la fase del flujo del proceso de negocio que contiene la entidad de `Social Activity` y elige el botón **Fase siguiente** , verá la opción **Crear** . Al elegir **Crear** se carga el formulario **Actividad social**. Sin embargo, dado que `Social Activity` no es válido para `Create` desde la interfaz de usuario de la aplicación, no podrá guardar el formulario y verá el mensaje de error: "Error inesperado".  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Número máximo de procesos, fases y pasos  
 Para garantizar un rendimiento aceptable y la capacidad de uso de la interfaz de usuario, hay algunas limitaciones que debe conocer cuando planee usar flujos de proceso de negocio:  
  
-   No puede haber más de 10 procesos de flujo de proceso de negocio habilitados por entidad.  
  
-   Cada proceso puede contener 30 fases como máximo.  
  
-   Los procesos de múltiples entidades no pueden contener más de cinco entidades.
  
## <a name="business-process-flow-entity-customization-support"></a>Compatibilidad con la personalización de entidades de flujo de proceso de negocio 

Introducidas en la actualización de la versión 9.0 de Dynamics 365 (online), las entidades de flujo de proceso de negocio pueden aparecer en el sistema para que los datos de registro de entidad pueden estar disponibles en cuadrículas, vistas, gráficos y paneles. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Utilice registros de entidad de flujo de proceso de negocio con cuadrículas, vistas, gráficos y paneles

Con los flujos de proceso de negocio disponibles como una entidad, ahora puede usar búsquedas avanzadas, vistas, gráficos y paneles procedentes de datos de flujos de procesos de negocio para una entidad dada, como un cliente potencial o una oportunidad. Los personalizadores y los administradores del sistema pueden crear paneles, vistas, gráficos y cuadrículas de flujo de proceso de negocio personalizados similar a los creados con cualquier otra entidad.

Los flujos de proceso de negocio, como **Proceso de cliente potencial a ventas de la oportunidad**, aparecen como una entidad personalizable en el Explorador de soluciones.

![Explorador de soluciones con la entidad Proceso de cliente potencial a ventas de la oportunidad](media/bpf-lead-solution-explorer.png)

Para acceder a una vista de flujo de proceso de negocio predeterminada, abra el explorador de soluciones, expanda **Entidades** > expanda el proceso que desee, como **Proceso de venta de cliente potencial a oportunidad**, seleccione **Vistas**y seleccione la vista que desee.

Hay varias vistas predeterminadas disponibles que puede ver como un gráfico, como la vista **Proceso de venta de oportunidad activo**. 

![Vista Proceso de ventas de la oportunidad activa](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interacción con la entidad de flujo de proceso de negocio desde un flujo de trabajo
También puede interactuar con las entidades de flujo de proceso de negocio desde un flujo de trabajo. Por ejemplo, puede crear un flujo de trabajo para el registro de entidad Flujo de proceso de negocio para cambiar la Fase activa cuando se actualice un campo en el registro de entidad Oportunidad. Para obtener más información sobre cómo hacerlo, vea [Automate business process flow stages using workflows](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows) (Automatización de las fases de flujo de proceso de negocio mediante flujos de trabajo).

### <a name="run-business-process-flows-offline"></a>Ejecución de los flujos de procesos de negocio sin conexión

Puede usar los flujos de procesos de negocio sin conexión si se cumplen estas condiciones:

- El flujo del proceso de negocio se usa desde una aplicación de Power Apps.
- Se ha habilita la aplicación Power Apps para su uso sin conexión.
- El flujo de procesos de negocio tiene una sola entidad.

En concreto, los tres comandos que están disponibles para un flujo de proceso de negocio cuando la aplicación Power Apps está sin conexión son:

- Fase siguiente
- Fase anterior
- Fase Establecer como activo

### <a name="limitations-of-using-business-process-flow-entities"></a>Limitaciones del uso de entidades de flujo de proceso de negocio

- En la actualidad, no se pueden crear formularios personalizados para entidades en función de un flujo de proceso de negocio.
- Si una solución incluye una entidad de flujo de proceso de negocio, esta se debe agregar de forma manual a la solución antes de exportarla. En caso contrario, la entidad de flujo de proceso de negocio no se incluirá en el paquete de solución. Más información: [Agregar componentes de la solución](/powerapps/maker/model-driven-apps/create-solution#add-solution-components)
- Al agregar una entidad Proceso a una aplicación controlada por modelos, la funcionalidad puede quedar limitada. Obtenga más información acerca de la [creación y edición de flujos de procesos de negocio](https://docs.microsoft.com/power-automate/create-business-process-flow). 

### <a name="next-steps"></a>Pasos siguientes  
 [Vea un vídeo corto (4:49) sobre flujos de proceso de negocio](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [Crear un flujo de proceso de negocio](create-business-process-flow.md)   
 [Mejora de los flujos de proceso de negocio con ramas](enhance-business-process-flows-branching.md) <br/>
 [Notas del producto: Habilitación de procesos con Dynamics 365](https://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf)</br>
