---
title: Reemplazo de cuadros de diálogo con aplicaciones de lienzo o flujos de proceso de negocio | Microsoft Docs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- flow
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b338991cfdbb73a8a0464fd4322714ece82c2ac5
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74373030"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>Reemplazo de cuadros de diálogo con aplicaciones de lienzo o flujos de proceso de negocio
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

[Los cuadros de diálogo están en desuso](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated) y es necesario reemplazarlos por aplicaciones de lienzo o flujos de procesos de negocio. En este tema se describen las distintas capacidades de estas opciones, así como las situaciones en las que se puede usar un flujo de proceso de negocio o una aplicación de lienzo insertada en un formulario basado en modelos para reemplazar un cuadro de diálogo existente.

## <a name="feature-capability-comparison"></a>Comparación de capacidades por característica

En esta tabla se enumera el conjunto de capacidades de los cuadros de diálogo y las capacidades equivalentes en los flujos de proceso y las aplicaciones de lienzo.


|Capacidad del cuadro de diálogo  | ¿Capacidad en flujos de proceso de negocio?  | ¿Capacidad en aplicaciones de lienzo?  |
|---------|---------|---------|
|Página     | Sí <br/> (fase de proceso de negocio)    | Sí <br/> (pantalla de aplicación)        |
|Solo pregunta   |  No    |  Sí <br/> (etiquetas)        |
|Pregunta y respuesta     |  Sí <br/> (solo atributos de entidad)    | Sí <br/> (etiquetas y campos de entrada)    |
|Argumentos de entrada     |  Limitada <br/> (pasos en fase de proceso de negocio)    | Sí <br/> (parámetros de cadena de consulta)     |
|Variables   |  No     |  Sí       |
|Variables de consulta    |  No     |  Sí     |
|Lógica de creación de ramas condicional    |  Sí     | Sí <br/>  (navegar a cualquier pantalla en la aplicación)    |
|Reutilizar <br/> (iniciar como un cuadro de diálogo secundario)   |  No     | Sí <br/> (navegar a cualquier pantalla dentro de la aplicación, iniciar una aplicación diferente en una nueva ventana)     |
|Ejecutar flujos de trabajo al iniciar y al finalizar    |   Sí      |  No <br/> (usar un flujo en su lugar)  |
|Ejecutar flujos de trabajo al escribir    | Sí    | No <br/> (usar un flujo en su lugar)   |
|Ejecutar flujos de trabajo al cambiar de página   |  Sí       | No <br/> (usar un flujo en su lugar)    |
|Empezar a usar URL  |   No      |  Sí     |
|Registro de sesión    |  Sí       |  No     |
|Soporte de SDK   |  Sí     |  Sí     |

### <a name="additional-capabilities-with-business-process-flows"></a>Capacidades adicionales con flujos de proceso de negocio
- Análisis de proceso (vistas, gráficos y tiempo invertido en una fase)
- Controles personalizados

### <a name="additional-capabilities-with-canvas-apps"></a>Capacidades adicionales con aplicaciones de lienzo
- Análisis de aplicación (uso y rendimiento de la aplicación)
- Composición de la página de varias entidades
- Ejecutar flujos
- Conectores de datos (estándar y personalizados)
- Iniciar como una aplicación independiente
- Diseño configurable

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>Elegir entre un flujo de proceso de negocio o una aplicación de lienzo
Cuando opta por reemplazar el cuadro de diálogo, es importante tener en cuenta la experiencia que quiere ofrecer al usuario. Tenga en cuenta también que se puede modelar casi cualquier cuadro de diálogo mediante una aplicación de lienzo.

Los flujos de proceso de negocio son más adecuados para reemplazar cuadros de diálogo que modelan procesos que sirven de guía en una serie de tareas, para las cuales es necesaria la colaboración entre grupos de personas y el contexto de la aplicación Dynamics 365. Por ejemplo, revisión de presupuestos y enrutamiento. 

Como alternativa, las aplicaciones de lienzo sirven para reemplazar cuadros de diálogo que modelan tareas prescriptivas, como un guion de llamada para la prospección de clientes potenciales o para simplificar la experiencia del usuario en otras tareas, como actualizar una oportunidad. Tenga en cuenta que estos escenarios incluso pueden beneficiarse de tener una aplicación de lienzo independiente. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>Reemplazar cuadros de diálogo mediante flujos de proceso de negocio
Imagine que tiene un cuadro de diálogo que, tras una serie de páginas, pide datos esenciales sobre el usuario, genera un presupuesto, envía un correo a los revisores para que acepten o rechacen el presupuesto y, por último, envía un correo al cliente. Este tipo de proceso se modela de manera más eficaz mediante un flujo de proceso de negocio. 

Para reemplazar el cuadro de diálogo, empiece por identificar las fases principales del proceso. Entre ellas se incluye una fase *Preparar contenido* para asegurarse de se enumeran todos los productos y se aplican descuentos; una fase *Generar presupuesto* para crear el presupuesto y revisar si el formato el correcto; una fase *Revisión principal* para enviar el presupuesto para su revisión y aprobación; una fase *Revisión secundaria* para revisar el presupuesto en determinadas circunstancias; y, finalmente, una fase *Enviar presupuesto* para enviar el presupuesto al cliente.

Después, identifique los pasos principales que los usuarios deben seguir en el proceso. Por ejemplo, la fase *Preparar contenido* podría incluir un sencillo paso de verdadero o falso para que el usuario vuelva a comprobar los productos que se van a incluir en el presupuesto, un paso obligatorio de búsqueda para seleccionar una lista de precios y un paso numérico para indicar un descuento antes de continuar con la siguiente fase. La fase *Generar presupuesto* podría tener un [paso de acción](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow) para crear un presupuesto basado en toda la información que se ha capturado previamente en la fase *Preparar contenido* y su registro de Dynamics 365 relacionado. Las fases *Revisión principal* y *Revisión secundaria* podrían incluir varios pasos de verdadero o falso para guiar en la revisión del presupuesto, junto con un paso necesario para capturar el estado de aprobación y garantizar que el proceso solo pueda pasar a la fase siguiente después de recibir la aprobación. Configure la [seguridad de nivel de campo](/customer-engagement/admin/field-level-security) en este paso para asegurarse de que solo los revisores autorizados puedan realizar la aprobación del presupuesto.  Además, se puede agregar un flujo de trabajo a las fases *Revisión principal* y *Revisión secundaria* de modo que, al entrar, se envíe una notificación por correo a todos los revisores. 

Por último, configure las fases y los pasos de flujo de proceso de negocio, junto con la lógica condicional para guiar el flujo de proceso. En este ejemplo, podría agregar una [rama condicional](enhance-business-process-flows-branching.md) tras la fase *Revisión principal* de modo que, si un paso indica la necesidad de un segundo nivel de revisión, la siguiente fase del proceso será *Revisión secundaria* y, en caso contrario, será la fase *Enviar presupuesto*.

Para poner este flujo de proceso de negocio a disposición de los usuarios, asegúrese primero de que los usuarios adecuados tienen privilegios para el flujo de proceso de negocio y, después, actívelo.

Para obtener más información sobre cómo crear un flujo de proceso de negocio, vea [Tutorial: Crear un flujo de proceso de negocio para estandarizar los procesos](create-business-process-flow.md).

## <a name="dialog-replacement-using-canvas-app-scenario"></a>Reemplazar cuadros de diálogo con aplicaciones de lienzo

Supongamos que tiene un cuadro de diálogo que sigue un guion de llamada para guiar a los representantes de ventas cuando realizan llamadas de telemarketing a clientes potenciales. Este proceso se puede capturar fácilmente mediante una aplicación de lienzo.

Empiece conectándose a los orígenes de datos que necesitará para leer y escribir datos. En este ejemplo, se usa una [conexión a Dynamics 365](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline) para la información de clientes potenciales, cuentas y contacto.

Empiece identificando el número de pantallas necesarias. En este ejemplo, habrá cinco pantallas. 
-   Pantalla 1. Para seleccionar un cliente potencial de una lista para llamarlo.
-   Pantalla 2. Para presentaciones, comprobar la disponibilidad para entablar la conversación y concertar una segunda llamada en otra fecha. 
-   Pantalla 3. Para determinar datos como presupuesto, autoridad, necesidad y escala de tiempo. 
-   Pantalla 4. Para capturar los pasos siguientes y programar llamadas de seguimiento. 
-   Pantalla 5. Agradecer al cliente potencial el tiempo dedicado al final de la llamada.

Después, compile cada pantalla. En la primera pantalla, [cree una galería](/powerapps/maker/canvas-apps/customize-layout-sharepoint) de clientes potenciales a los que debe llamarse. En la segunda, use etiquetas para el título de la pantalla y proporcione el guion de la llamada. Use también controles como botones de radio para indicar si es un buen momento para hablar con esta persona. Si lo es, use una lógica condicional para habilitar un botón que permita navegar a la pantalla siguiente y, si no, muestre un guion en la misma pantalla para intentar concertar una segunda llamada con el cliente. De forma similar, defina el guion de la llamada en las pantallas posteriores.

Por último, [defina la navegación entre pantallas](/powerapps/maker/canvas-apps/functions/function-navigate). En este ejemplo, además de navegar por las pantallas de forma secuencial, es posible que quiera que el usuario se desplace desde la segunda pantalla hasta la última (el final del guion en el que se da las gracias al cliente potencial por su tiempo) si el cliente potencial no está interesado en tener una conversación.

Para poner esta aplicación a disposición de los usuarios, tiene que publicarla. Piense en cómo cambiaría este escenario si hubiera disponible una aplicación independiente que proporcionara guiones de llamada y admitiera la entrada de datos rápida.

Supongamos que quiere incluir esta experiencia en Dynamics 365 Sales. Para hacerlo, empiece creando un iframe en un formulario de Dynamics 365 Sales. Después, navegue a la sección **Aplicaciones** en el menú de Power Apps, seleccione la aplicación que acaba de publicar, copie el vínculo web debajo de la pestaña **Detalles** y péguela como la URL para el iframe. 

Si damos un paso más, supongamos que quiere que esta aplicación esté disponible directamente desde el formulario principal del cliente potencial y se encuentre en el contexto del cliente potencial para que la aplicación no pida al usuario que seleccione un cliente potencial en la primera pantalla. Para pasar información pertinente a la aplicación, solo tiene que modificar la dirección URL del iframe para anexar una cadena de consulta que contenga esta información, como los identificadores de cliente potencial o de cuenta, usando JavaScript que se ejecute en un determinado evento, como en la carga del formulario. Después, actualice la aplicación para quitar la primera pantalla (para la selección del cliente potencial) y, en su lugar, acceda a los valores que se pasaron a la aplicación a través de la cadena de consulta mediante la [función Param](/powerapps/maker/canvas-apps/functions/function-param).

## <a name="dialog-replacement-faq"></a>Preguntas más frecuentes sobre el reemplazo de cuadros de diálogo

¿Se hace un seguimiento de las dependencias en el lienzo? 
- El seguimiento de las dependencias en las aplicaciones de lienzo se hace de la misma manera que con las dependencias en aplicaciones de Dynamics 365.

¿Se puede iniciar una aplicación de lienzo como una ventana emergente desde un botón en la barra de comandos?
- Sí. Para ello, basta con establecer la URL de la aplicación de lienzo como URL de destino, obtenida de la sección **Detalles** de la aplicación como se describió anteriormente.

¿Se puede llamar a los flujos de trabajo desde una aplicación de lienzo?
- No es posible hacerlo. Es preferible usar un flujo. Más información: [Presentación de los flujos de botones con entradas del usuario](button-flow-with-user-input-tokens.md)

¿Puedo convertir automáticamente cuadros de diálogo en flujos de proceso de negocio o aplicaciones de lienzo?
- No hay una manera automatizada de convertir cuadros de diálogo en flujos de proceso de negocio o aplicaciones de lienzo.


## <a name="see-also"></a>Vea también
[Tutorial: Crear un flujo de proceso de negocio para estandarizar los procesos](create-business-process-flow.md) </br>
[¿Qué son las aplicaciones de lienzo en Power Apps?](/powerapps/maker/canvas-apps/getting-started)


