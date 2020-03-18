---
title: Reemplazo de flujos de trabajo clásicos de Common Data Service con Power Automate | Microsoft Docs
description: En este artículo se describen las funcionalidades de Power Automate y los patrones recomendados para usar un flujo en lugar de un flujo de trabajo clásico.
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
ms.service: flow
ms.topic: article
ms.date: 08/27/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6e3e6d1ca0a1700bbfaf6d8e8fb76cc888456c2c
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193755"
---
# <a name="replace-classic-common-data-service-workflows-with-flows"></a>Reemplazo de flujos de trabajo clásicos de Common Data Service con flujos


En este tema se comparan las funcionalidades de Power Automate con el flujo de trabajo clásico.

Power Automate ofrece ventajas considerables con respecto al modelo de flujo de trabajo clásico. Debe considerar la posibilidad de usar Power Automate para automatizar los procesos en lugar del flujo de trabajo clásico. 

Cree flujos en lugar de flujos de trabajo clásicos de Common Data Service para crear procesos de automatización nuevos. Además, debe revisar los procesos de flujo de trabajo clásico existentes y considerar reemplazarlos con flujos.

## <a name="feature-capability-comparison"></a>Comparación de capacidades por característica

En esta tabla se resume una comparación entre las funcionalidades de Power Automate y las funcionalidades de los flujos de trabajo clásicos. 

*Estaremos agregando continuamente nuevas funcionalidades a Power Automate de modo que estén al mismo nivel e incluso mejor que las funcionalidades del flujo de trabajo clásico. A medida que aumenten las funcionalidades de Power Automate, actualizaremos la información de esta tabla, por lo que no olvide volver a consultarla con frecuencia. Para información sobre las próximas funcionalidades de los flujos que lo ayudarán a reemplazar el flujo de trabajo clásico por un flujo, consulte las [características nuevas y previstas para Power Automate](https://docs.microsoft.com/business-applications-release-notes/April19/microsoft-flow/planned-features) en las notas de la versión de abril de 2019*.

<table>
<tr>
<th colspan="2">Funcionalidad</th>
<th>Power Automate</th>
<th>Flujo de trabajo clásico</th>
</tr>
<tr>
<td rowspan="5">Modelado</td>
<td>Creación de ramas condicional</td>
<td>Sí</td>
<td>
                    
   Sí
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Bucle
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Condiciones de espera en los campos
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Rama paralela
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Conectores integrados a sistemas externos (desencadenar y realizar acciones en servicios externos)
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Composición
                    
                </td>
                <td>
                    
   Contenido dinámico
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Acceso a la imagen previa de datos de eventos
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ejecución de flujos de trabajo secundarios
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ejecución de acciones de Common Data Service (incluidas personalizadas)
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ejecución de actividades personalizadas de flujo de trabajo
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Agrupación de pasos a ejecutar en una transacción
                    
                </td>
                <td>
                    
   Sí (conjuntos de cambios)
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Flujos de trabajo de aprobación
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Ejecución
                    
                </td>
                <td>
                    
   Desencadenamiento en cambios de campos
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Desencadenamiento condicional en valores de campo (por ejemplo, en una fecha determinada en un campo de fecha)
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Desencadenador en varios eventos de entidad de Common Data Service
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ejecución a petición
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ámbitos de ejecución    <br/>
   (por ejemplo, organización, unidad de negocio)
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ejecución programada
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ejecución sincrónica (en tiempo real)
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
            </tr>
            <tr>
                <td rowspan="2">
                    
   Historial
                    
                </td>
                <td>
                    
   Auditoría
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ejecución de análisis
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td rowspan="3">
                    
   Creación y portabilidad
                    
                </td>
                <td>
                    
   Compatibilidad de la solución
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Diseñador moderno
                    
                </td>
                <td>
                    
   Sí
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
<td>Creación asistida por IA</td>
<td>Sí</td>
<td>No</td>
</tr>
</table>

## <a name="example-scenario-replace-workflow-with-a-flow"></a>Escenario de ejemplo: reemplazo de un flujo de trabajo por un flujo

Imagine un escenario de ventas en el que ha elaborado un presupuesto para un cliente y ahora necesita solicitar la aprobación del equipo de administración antes de enviar el presupuesto al cliente. Con los flujos de trabajo clásicos, esto no habría sido fácil de hacer y la mayoría de las soluciones obligaría a los desarrolladores a escribir actividades de flujo de trabajo personalizadas para recuperar los elementos de línea de la cotización.

Con los flujos, esto es más fácil de elaborar, tal como se muestra en el tutorial más adelante, en el que se tratan algunas de las funcionalidades de Power Automate para admitir el escenario. Esto incluye:

-   Crear un flujo que se ejecuta a petición

-   Obtener una lista de registros relacionados con una entidad de Common Data Service

-   Crear bucles en una lista de registros

-   Enviar solicitudes de aprobación

Para permitir que el vendedor desencadene la solicitud de aprobación a petición:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com/) y cree un flujo en una solución. Más información: [Creación de un flujo en una solución](create-flow-solution.md). 

1. En la lista de desencadenadores, seleccione **Common Data Service (Current Environment) – When a record is selected** (Common Data Service (entorno actual): cuando se selecciona un registro) y seleccione **Quotes** (Cotizaciones) como la entidad. Este desencadenador permite que un flujo se ejecute a petición en un registro o lista de registros.

1. Con el desencadenador configurado, agregue acciones para que se ejecuten en el flujo. Esto le proporcionará al aprobador el resumen detallado que necesita para identificar los valores y elementos cotizados. Para empezar, agregue la acción **Common Data Service (Current Environment) – List records** (Common Data Service (entorno actual): enumerar registros). Como queremos obtener elementos de línea individuales de una cotización, establezca la entidad en **Quote lines** (Líneas de cotización). Para garantizar que solo se muestren los elementos de la línea de cotización que pertenecen a la cotización para la que se desencadenó el flujo, especificaremos un criterio de filtro de estilo OData. En el campo **Filter Query** (Consulta de filtro), escriba *\_quoteid_value eq* y, luego, seleccione *Quote* (Cotización) en la lista de valores dinámicos que aparece.

    ![Definición del flujo](media/define-flow-1.png "Definición del flujo")

1. Como queremos resumir los elementos de línea de la cotización para la aprobación, agregue la acción **Initialize variable** (Inicializar la variable). Establezca el campo **Name** (Nombre) en *Quote line summary* (Resumen de línea de cotización) y el campo **Type** (Tipo) en String (Cadena) (del menú desplegable) y deje en blanco el campo **Value** (Valor).

1. Agregue la acción **Append to string variable** (Anexar a la variable de cadena) y seleccione la variable *Quote line summary* (Resumen de línea de cotización) que creamos anteriormente. En el campo **Value** (Valor), seleccione *Quantity, Name, Price per unit, Extended amount and Manual amount* (Cantidad, Nombre, Precio por unidad, Importe extendido e Importe manual) en la lista de valores dinámicos. El diseñador de Power Automate identifica que estos valores provienen de una lista de elementos de línea de la cotización y agrega esta acción en un bucle **Apply to each** (Aplicar a cada uno) para garantizar que la información de cada elemento de línea se agregue a este resumen.

    ![Definición del flujo](media/define-flow-2.png "Definición del flujo")

1. Para solicitar la aprobación del resumen de la cotización que creamos, agregue la acción **Approval – Start and wait for an approval** (Aprobación: iniciar y esperar una aprobación). Seleccione un tipo de aprobación (por ejemplo, Approve/Reject – First to respond [Aprobar o rechazar: primero en responder]), asigne a la solicitud de aprobación un **Title** (Título) (por ejemplo, el nombre de la cotización cuya aprobación se solicita, elegido de la lista de valores dinámicos), escriba la dirección de correo electrónico para la persona que necesita revisar y aprobar la cotización en el campo **Asignado a**. En el campo de detalles, agregue la variable *Quote line summary* (Resumen de línea de cotización), junto con cualquier otra información que podría ser pertinente con el selector del valor dinámico (por ejemplo, Total Amount [Importe total]).

1. Para determinar qué ocurre una vez que se acepta o rechaza una aprobación, agregue la acción **Condition** (Condición). Seleccione *Outcome* (Resultado) en la lista de valores dinámicos del primer campo en la condición, *Contains* (Contiene) en el menú desplegable en el segundo campo y escriba *Accept* (Aceptar) en el tercer campo de la condición. Por último, agregue acciones basadas en el resultado de la aprobación (por ejemplo, envíe un correo electrónico de notificación).

    ![Definición del flujo](media/define-flow-3.png "Definición del flujo")

Ahora tenemos creada la estructura de aprobación, por lo que el aprobador tiene toda la información necesaria para tomar una decisión sobre los pasos siguientes. Este es el flujo a petición del ejemplo completo para solicitar aprobación:

![Estructura de flujo de aprobación](media/approval-flow-structure.png "Estructura de flujo de aprobación")

Cuando este flujo se ejecuta en la cotización, resume los elementos de línea de esa cotización y envía una solicitud de aprobación a la que el aprobador puede responder desde Power Automate, o bien el correo electrónico accionable que recibe. A continuación, se muestra un ejemplo de la pantalla:

![Flujo en acción](media/flow-in-action.png "Flujo en acción")

## <a name="recommended-patterns"></a>Patrones recomendados


-   **Flujos de trabajo con lógica condicional else-if compleja**  
    
    En lugar de usar condiciones, se recomienda usar la [acción switch](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-switch-statement#add-switch-statement).

-   **Flujos de trabajo que se ejecutan desde un complemento o el código**  
    
    Se recomienda volver a diseñar el flujo para que empiece con los desencadenadores.

    -   Use los desencadenadores de Common Data Service para ejecutar flujos basados en eventos en él.

    -   Para ejecutar flujos basados en eventos en un servicio externo, aproveche los más de 260 conectores integrados.

    -   En escenarios en los que un conector necesario no está disponible de manera inmediata, puede crear fácilmente su propio conector personalizado. [Aprenda a crear conectores personalizados](https://docs.microsoft.com/connectors/custom-connectors/define-blank).

    -   Por último, si hay escenarios en los que no puede desencadenar el flujo mediante el conector de Common Data Service, uno de los conectores integrados, o crear un conector personalizado, aproveche el desencadenador [Cuando se recibe una solicitud HTTP](https://docs.microsoft.com/azure/connectors/connectors-native-reqres#use-the-http-request-trigger) para invocar el flujo.

-   **Flujos de trabajo que se ejecutan de manera recursiva**  
    
    Use el bucle [do-until](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) o [apply to each](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#foreach-loop) en Flows en su lugar.

-   **Flujos de trabajo que necesitan una lista de registros**  
    
    Use la acción **list records**. Cuando use esta acción, defina los criterios del filtrado de los registros con la sintaxis de OData para optimizar la acción al minimizar la cantidad de registros que quiere recuperar.

-   **Flujos de trabajo en suspensión para ejecutarse según una programación**  
    
    Use el desencadenador de **recurrencia** para ejecutar la lógica de negocios a intervalos periódicos.

-   **Flujos de trabajo para los que se administraron ejecuciones para garantizar que las actividades se ejecutaron en una sola transacción**  
    
    [Use la [acción de conjunto de cambios](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/automated-flows-support-change-sets-common-data-service) para garantizar que todas las acciones que incluya se realicen como una unidad atómica única en la que todas se ejecutan correctamente o presentan errores como un grupo. Si alguna de las acciones de un conjunto de cambios presenta un error, los cambios realizados por las operaciones completadas se revierten.

-   **Supervisión de ejecuciones de flujos de trabajo para descubrir errores**  
    
    En Power Automate, use la **configuración run-after** en una acción para configurarla a fin de que se ejecute cuando la acción anterior presente un error. Por ejemplo, envíe una notificación móvil de Power Automate cuando la acción de **actualizar un registro** presente un error o se agote el tiempo de espera.

## <a name="faqs"></a>Preguntas más frecuentes


-   **Tengo una licencia de Dynamics 365. ¿Puedo usar Power Automate?**

    Cada usuario de Dynamics 365 tiene derecho a usar Power Automate. Revise la información de la licencia: <https://flow.microsoft.com/pricing/>

-   **¿Con qué frecuencia se pueden desencadenar los flujos?**

    -   Los flujos de Dynamics 365 (o Common Data Service) se ejecutan casi en tiempo real después del desencadenador porque usan webhooks (no se requiere ningún sondeo).

    -   Al igual que con el acceso directo a la API, hay limitaciones o límites en el sistema, lo que está totalmente documentado aquí: <https://docs.microsoft.com/flow/limits-and-config>

    -   En concreto, hay un límite de 100 000 acciones cada 5 minutos por flujo y un solo bucle en un flujo no puede procesar más de 100 000 elementos a la vez.

    -   Máximo de 6 GB de rendimiento cada 5 minutos

-   **¿Durante cuánto tiempo se puede ejecutar un flujo único?**  
    
    El tiempo de espera de la ejecución de un flujo único se agota después de 30 días.

-   **¿Cómo muevo los flujos entre entornos?**  
    
    Al igual que los flujos de trabajo clásicos, puede crear flujos en soluciones para admitir todo el ciclo de vida de la aplicación para los procesos.

-   **¿Se hace un seguimiento de las dependencias de Power Automate en Common Data Service?**  
    
    De manera similar a otros componentes de una solución, se realiza un seguimiento de todas las dependencias de los flujos de soluciones en Common Data Service.

-   **¿Qué ocurre con los flujos de trabajo sincrónicos?** 
 
    Debe volver a evaluar la necesidad de flujos de trabajo sincrónicos para identificar si el objetivo o partes del flujo de trabajo se pueden compilar con un flujo. En concreto, a partir de nuestra telemetría, vemos que los flujos de trabajo sincrónicos son un colaborador importante a la experiencia general de rendimiento deficiente del usuario final. Sin embargo, para muchos usuarios, sería preferible dividir estas acciones como asincrónicas para que el usuario pudiera seguir con su actividad mientras Power Automate continúa garantizando la finalización de la acción.

-   **Con Power Automate, ¿mis datos permanecerán dentro de la región (es decir, en la misma región que mi entorno de Common Data Service o Dynamics 365)?**  
    
    Sí, Power Automate siempre usa la misma región que Common Data Service.

-   **¿Es necesario modificar el proxy o el firewall?**  
    
    Consulte la [referencia de la configuración de dirección IP](limits-and-config.md#ip-address-configuration) para determinar si es necesario hacer alguna modificación en el proxy o el firewall.
