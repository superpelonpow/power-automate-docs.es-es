---
title: Introducción | Microsoft Docs
description: Formas rápidas de empezar a automatizar el trabajo y la vida con Power Automate.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/05/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: bb50b99f0a86e1221aaa4c4072426a31b9bf8f61
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74368660"
---
# <a name="get-started-with-power-automate"></a>Introducción a Power Automate 

[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

<br>
<iframe width="1129" height="635" src="https://www.youtube.com/embed/hCuxuUaGC6Y" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Bienvenido. Power Automate es un servicio que le ayuda a crear flujos de trabajo automatizados entre sus aplicaciones y servicios favoritos para sincronizar archivos, obtener notificaciones, recopilar datos, etc.

## <a name="types-of-flows"></a>Tipos de flujos

Power Automate es uno de los pilares de Power Platform. Proporciona una plataforma con poco código para la automatización de procesos y flujos de trabajo. Esta es una lista de los diferentes tipos de flujos:

| **Tipo de flujo**                                                                       | **Caso de uso**                                                                                  | **Destino**                                                                             |
|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| [Flujos automatizados](get-started-logic-flow.md)                 | Cree un flujo que realice automáticamente una o varias tareas después de que lo desencadene un evento. | [Conectores](https://docs.microsoft.com/connectors/) para servicios en la nube o locales. |
| [Flujos de botón](introduction-to-button-flows.md)              | Ejecute tareas repetitivas desde cualquier lugar, en cualquier momento, a través del dispositivo móvil.                        |                                                                                        |
| [Flujos programados](run-scheduled-tasks.md)                    | Cree un flujo que realice una o varias tareas según una programación.             |                                                                                        |
| [Flujos de proceso de negocio](business-process-flows-overview.md) | Defina un conjunto de pasos que los usuarios pueden seguir para llegar a un resultado deseado.                 | Procesos humanos                                                                        |
| [Flujos de interfaz de usuario (versión preliminar)](ui-flows/overview.md)                                                | Registre y automatice la reproducción de pasos manuales en un software heredado.                    | Aplicaciones web y de escritorio que no tienen API disponibles para la automatización.    |

Puede crear y administrar todos los flujos de la pestaña **Mis flujos** de Power Automate.

Si es un usuario de Dynamics 365, puede que también esté familiarizado con los procesos clásicos de Common Data Service, entre los que se incluyen [flujos de trabajo](configure-workflow-steps.md), [acciones](create-actions.md), [flujos de tareas móviles](create-mobile-task-flow.md) y [cuadros de diálogo](use-cds-for-apps-dialogs.md).

El primer paso es [registrarse](sign-up-sign-in.md) o, si ya tiene una cuenta de Power Automate, [iniciar sesión](https://flow.microsoft.com/signin) directamente en su tableta o equipo de escritorio, o incluso en su teléfono.

## <a name="check-out-the-start-page"></a>Visitar la página de inicio ##

[En la página de inicio](https://flow.microsoft.com) de Power Automate, puede [explorar una amplia variedad de plantillas](https://flow.microsoft.com/templates) y obtener más información sobre sus características clave. Se hará una idea rápidamente de lo que Power Automate puede hacer y de cómo puede ayudarle tanto en el ámbito profesional como personal.

Con Power Automate, puede hacer lo siguiente:

- Buscar fácilmente servicios y plantillas.

    ![Página de inicio de Flow (1)](./media/getting-started/flowhome1.png)

- Elegir un servicio de entre los más populares.

    ![Página de inicio de Flow (2)](./media/getting-started/flowhome2.png)

- Ver información general sobre cada flujo.

    ![Página de inicio de Flow (3)](./media/getting-started/flowhome3.png)

Cada plantilla está diseñada para un propósito específico. Por ejemplo, el envío de un mensaje de texto cuando su jefe le envíe correos electrónicos, la incorporación de clientes potenciales de Twitter a Dynamics 365 o la realización de copias de seguridad de sus archivos. Estas plantillas son solo el aspecto más destacado, pero hay mucho más. Están diseñadas para inspirarle a crear flujos personalizados para cualquier proceso que necesite.

## <a name="create-your-first-flow"></a>Creación del primer flujo ##

1. Seleccione una plantilla que le resulte útil. Una plantilla sencilla es [**Recibir recordatorios diarios en el correo**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/):

    ![plantilla de recordatorio diario](./media/getting-started/template-details.png)

1. Seleccione **Continuar**.

    ![Creación de una conexión](./media/getting-started/create-connection.png)

1. Escriba las direcciones de correo electrónico a la que se enviará el recordatorio diario. A continuación, escriba el mensaje recordatorio. Por último, seleccione **Crear flujo** y compruebe que el flujo se ejecuta como cabría esperar.

    ![Indicar las credenciales para la conexión](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > Ahora puede explorar las condiciones que desencadenan el flujo y la acción que se deriva de dichos eventos. Aproveche para experimentar con la configuración y crear su propio flujo. Incluso puede agregar o eliminar acciones.

1. Seleccione **Listo**.

[Siga este tutorial](get-started-logic-template.md) para obtener más información sobre la creación de flujos a partir de plantillas.

## <a name="get-creative"></a>Creatividad ##

Ahora que ha creado su primer flujo a partir de una plantilla, use cualquiera de los más de [150 orígenes de datos](https://flow.microsoft.com/connectors/) que Power Automate admite para [crear sus propios flujos desde cero](get-started-logic-flow.md).

![Compilación de un flujo](./media/getting-started/build-a-flow.png)

Si crea un flujo de trabajo desde cero, podrá controlarlo en su totalidad. Aquí le presentamos algunas ideas para empezar:

- [Flujos con muchos pasos](multi-step-logic-flow.md)
- [Ejecución de tareas de forma programada](run-scheduled-tasks.md)
- [Creación de un flujo de aprobación](wait-for-approvals.md)
- [Visualización de un flujo en acción](see-a-flow-run.md)
- [Publicación de una plantilla](publish-a-template.md)
- [Creación de flujos desde una plantilla de Microsoft Teams](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/)


## <a name="peek-at-the-code"></a>Inspección del código

No es necesario que sea desarrollador para crear flujos; sin embargo, Power Automate proporciona la característica **	Inspeccionar código** para permitir a cualquier persona examinar más de cerca el código que se genera para todas las acciones y desencadenadores de un flujo. Al inspeccionar el código, puede obtener una descripción más clara de los datos que usan los desencadenadores y las acciones. Siga estos pasos para inspeccionar el código que se genera para los flujos desde el diseñador de Power Automate: 

1. Seleccione el elemento de menú **...** en la esquina superior derecha de cualquier **acción** o **desencadenador**. 
1. Seleccione **Inspeccionar código**.

    ![Inspeccionar código](media/getting-started/peek-code.png)

1. Observe la representación JSON completa de las acciones y los desencadenadores. Esto incluye todas las entradas, como el texto que escribe directamente, y las expresiones usadas. Puede seleccionar aquí las expresiones y, a continuación, pegarlas en el editor de expresiones de **contenido dinámico**. Esto sirve también para comprobar que los datos esperados están presentes en el flujo.

    ![Inspeccionar código](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Búsqueda sencilla de los flujos

Cuando su vertiente creativa empiece a *fluir*, puede crear muchos flujos. Pero si necesita encontrar alguno en concreto, no se preocupe, porque es un proceso sencillo. Basta con recurrir al cuadro de búsqueda en la pantalla **Mis flujos**, **Flujos del equipo**, **Conexiones** o **Soluciones** para que aparezcan únicamente los flujos que coincidan con los términos de búsqueda que especifique.

![Filtrado o búsqueda de flujos](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> El filtro de búsqueda solo busca entre los flujos que se han cargado en la página. Si no encuentra el flujo, pruebe a seleccionar **Cargar más** en la parte inferior de la página.

## <a name="get-notifications-when-somethings-wrong"></a>Recepción de notificaciones cuando haya algún problema

Use el centro de notificaciones de Power Automate (en la parte superior derecha del diseñador) para ver rápidamente una lista de los flujos que dieron error recientemente. El centro de notificaciones muestra un número que indica el número de flujos que dieron error recientemente.

Desde el centro de notificaciones, puede ir a la página **Actividad** de Power Automate para ver todos los flujos que recientemente se ejecutaron, enviaron notificaciones o dieron error.

![Centro de notificaciones](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Uso de la aplicación móvil ##

Descargue la aplicación móvil de Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows). Con la aplicación, podrá [supervisar la actividad de los flujos](mobile-monitor-activity.md), [administrarlos](mobile-manage-flows.md) y [crearlos a partir de plantillas](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Podemos ayudarle ##

Tenemos muchas ganas de ver lo que puede hacer con Power Automate, y queremos asegurarnos de que tenga una gran experiencia. No olvide visitar nuestros tutoriales de [aprendizaje paso a paso](https://flow.microsoft.com/guided-learning/) ni de [unirse a nuestra comunidad](https://go.microsoft.com/fwlink/?LinkID=787467), donde podrá realizar preguntas y compartir sus ideas. [Póngase en contacto con soporte técnico](https://go.microsoft.com/fwlink/?LinkID=787479) si surge algún problema.