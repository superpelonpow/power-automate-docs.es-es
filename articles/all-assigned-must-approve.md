---
title: Creación de un flujo de aprobación que requiera la aprobación de todos | Microsoft Docs
description: Cree un flujo de aprobación que requiera que todos los usuarios lo aprueben o que una persona rechace una solicitud.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/07/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3f668d4462c06e061efe2a03b4e5e842364c4b6e
ms.sourcegitcommit: 5b1965a0c319c4294b7dc0c829120ed1f4f90444
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2020
ms.locfileid: "82153482"
---
# <a name="create-an-approval-flow-that-requires-everyone-to-approve"></a>Creación de un flujo de aprobación que requiere que todos lo aprueben


En este tutorial se muestra cómo crear un flujo de trabajo de aprobación que requiere que todos (todos los aprobadores asignados) acuerden que se apruebe una solicitud de vacaciones, pero que cualquier aprobador pueda rechazar toda la solicitud.

Este tipo de flujo de trabajo de aprobación es útil en una organización que requiera que el jefe de una persona y el jefe del jefe estén de acuerdo con una solicitud de vacaciones para que esta se apruebe. Sin embargo, cualquiera de los jefes puede rechazar la solicitud sin los datos de la otra persona.

> [!NOTE]
> Aunque en este tutorial se resalta un escenario de aprobación de vacaciones, puede usar este tipo de flujo de aprobación en cualquier situación en la que varios aprobadores deban aprobar una solicitud.
>
>

## <a name="prerequisites"></a>Requisitos previos

* Acceso a [Power Automate](https://flow.microsoft.com), Microsoft Office 365 Outlook y Usuarios de Microsoft Office 365.
* Una [lista](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) de SharePoint.

    En este tutorial se da por supuesto que ya ha creado una lista de SharePoint que se usa para solicitar vacaciones. Vea el tutorial de [aprobaciones en paralelo](parallel-modern-approvals.md) para obtener un ejemplo en profundidad que detalla cómo sería la lista de SharePoint.
* Familiaridad con los conceptos básicos de la creación de flujos.

    Puede revisar cómo agregar [acciones, desencadenadores](multi-step-logic-flow.md#add-another-action) y [condiciones](add-condition.md). En los pasos siguientes se da por hecho que sabe cómo realizar estas acciones.

> [!NOTE]
> Aunque en este tutorial se usan SharePoint y Office 365 Outlook, puede usar otros servicios como Zendesk, Salesforce, Gmail o cualquiera de los más de [200 servicios](https://flow.microsoft.com/connectors/) que admite Power Automate.
>
>

## <a name="create-the-flow"></a>Creación del flujo

> [!NOTE]
> Si no ha creado previamente una conexión a SharePoint o a Office 365, siga las instrucciones cuando se le pida que inicie sesión.
>
>

En este tutorial se utilizan tokens. Para mostrar una lista de tokens, pulse o haga clic en cualquier control de entrada y, después, busque el token en la lista **Contenido dinámico** que se abre.

Inicie sesión en [Power Automate](https://flow.microsoft.com) y siga estos pasos para crear un flujo.

1. Seleccione **Mis flujos** > **Nuevo** > **Automated-from blank** (Automatizado desde cero), en la parte superior izquierda de la pantalla.
1. Asigne un nombre al flujo y, luego, agregue el desencadenador **SharePoint - Cuando se crea o se modifica un elemento**.
1. En **Dirección del sitio**, escriba la dirección del sitio de SharePoint que hospeda la lista de solicitudes de vacaciones y luego seleccione una lista en **Nombre de lista**.
1. Seleccione **Nuevo paso**, agregue la acción **Obtener el administrador (V2)** de Office 365, seleccione el cuadro **Usuario (UPN)** y, luego, agréguele el token **Creado por correo electrónico**.

    El token **Creado por correo electrónico** se encuentra en la categoría **Cuando se crea o se modifica un elemento** de la lista **Contenido dinámico**. Este token proporciona acceso de forma dinámica a datos sobre el administrador a la persona que ha creado el elemento en SharePoint.

1. Seleccione **Nuevo paso**, agregue otra acción **Obtener el administrador (V2)** de Office 365 y, luego, agregue el token **Correo electrónico** al cuadro **Usuario (UPN)** .

    El token **Correo electrónico** se encuentra en la categoría **Obtener el administrador (V2)** de la lista **Contenido dinámico**. Este token proporciona acceso de forma dinámica a la dirección de correo electrónico del administrador del administrador.

    También puede cambiar el nombre de la tarjeta **Obtener el administrador (V2) 2** por algo que tenga sentido, como "Omitir administrador de niveles".
1. Seleccione **Nuevo paso**, agregue la acción **Iniciar y esperar una aprobación** y, luego, seleccione **Aprobar o rechazar: todos deben aprobar** en la lista **Tipo de aprobación**.

   > [!IMPORTANT]
   > Si cualquier aprobador rechaza la solicitud de aprobación, se considera rechazada para todos los aprobadores.
   >
   >
1. Use la tabla siguiente como guía para completar la tarjeta **Iniciar y esperar una aprobación**.

   | Campo | Descripción |
   | --- | --- |
   | Tipo de aprobación |Consulte los [tipos de aprobación](#approval-types-and-their-behaviors). |
   |  Título |El título de la solicitud de aprobación. |
   |  Asignado a |Las direcciones de correo electrónico de los aprobadores. |
   |  Detalles |Cualquier información adicional que desea que se envíe a los aprobadores que se enumeran en el campo **Asignado a**. |
   |  Vínculo del elemento |Una dirección URL que conduce al usuario al elemento de aprobación. En este ejemplo, es un vínculo al elemento de SharePoint. |
   |  Descripción del vínculo del elemento |Una descripción del **vínculo del elemento**. |

   > [!TIP]
   > La acción **Iniciar y esperar una aprobación** proporciona varios tokens, entre los que se incluyen **Respuestas** y **Resultado**. Utilice estos tokens en su flujo de para proporcionar una gran funcionalidad de informes enriquecidos de los resultados de una ejecución de un flujo de solicitud de aprobación.
   >
   >

    La tarjeta **Iniciar y esperar una aprobación** es una plantilla para la solicitud de aprobación que se envía a los aprobadores. Configúrela de forma que resulte útil para su organización. Aquí se muestra un ejemplo.

    ![Iniciar y esperar una aprobación](media/all-assigned-must-approve/start-an-approval-card.png)

    Cuando un flujo con la acción **Iniciar y esperar una aprobación** se configura con **Aprobar o rechazar: todos deben aprobar**, espera hasta que todos los incluidos en **Asignado a** aprueben o al menos un **Asignado a** rechace la solicitud de aprobación.

    >[!TIP]
    >Agregue un paso de **Condición** si quiere que el flujo compruebe la respuesta de la solicitud de aprobación y realice diferentes acciones en función del valor de **Resultado**. El valor de **Resultado** puede ser **Aprobar** o **Rechazar**. 

    Vamos a continuar con el flujo y a enviar un correo electrónico cuando se tome una decisión sobre la solicitud de aprobación.

1. Seleccione **Nuevo paso**, busque "enviar un correo electrónico", agregue la acción **Enviar correo electrónico (V2)** de Office 365 y, luego, configure la acción para enviar un correo electrónico con los resultados de la solicitud a la persona que desea ir a vacaciones.

    Este es un ejemplo del aspecto que podría tener la tarjeta **Enviar correo electrónico (V2)** .

    ![enviar un correo electrónico](media/all-assigned-must-approve/send-an-email-card.png)

> [!NOTE]
> Todas las acciones posteriores a **Iniciar y esperar una aprobación** se ejecutan de acuerdo con la selección de la lista **Tipo de aprobación** de la tarjeta **Iniciar y esperar una aprobación**. En la tabla siguiente se muestra el comportamiento en función de la selección.
>
>

### <a name="approval-types-and-their-behaviors"></a>Tipos de aprobación y sus comportamientos

| Tipo de aprobación | Comportamiento |
| --- | --- |
| Aprobar o rechazar: todos deben aprobar | **Todos** los aprobadores deben aprobar o rechazar la solicitud para completar el proceso. </p> Las acciones que siguen a la acción **Iniciar y esperar una aprobación** se ejecutan después de que **todos** los aprobadores efectúen la aprobación, o cuando se realice un solo rechazo.|
| Aprobar o rechazar: primero en responder | La aprobación o el rechazo por parte de un aprobador completa la solicitud.  </p> Las acciones que siguen a la acción **Iniciar y esperar una aprobación** se ejecutan después de que cualquiera de los aprobadores lo decida.|
| Respuestas personalizadas: esperar todas las respuestas | Todos los aprobadores deben responder para completar el proceso. |
| Respuestas personalizadas: esperar una respuesta | Una respuesta de cualquier aprobador completa el proceso. |

Seleccione **Guardar** en la parte superior de la pantalla para guardar el flujo.

Enhorabuena, el flujo está completo. Si ha seguido todos los pasos, el flujo será como el de la siguiente imagen:

![imagen de flujo global](media/all-assigned-must-approve/overall-flow.png)

Ahora, cada vez que se agrega un elemento a la lista de SharePoint, o si cambia algún elemento, se desencadena el flujo y envía solicitudes de aprobación a todos los aprobadores que figuran en la lista del cuadro **Asignado a** de la tarjeta **Iniciar y esperar una aprobación**. El flujo envía solicitudes de aprobación tanto a través de la aplicación móvil Power Automate como por correo electrónico. La persona que crea el elemento en SharePoint recibe un correo electrónico que resume los resultados, en el que se indica con claridad si la solicitud se ha aprobado o rechazada.

Este es un ejemplo de la solicitud de aprobación que se envía a cada aprobador.

![solicitud de aprobación](media/all-assigned-must-approve/approval-request.png)

Este es un ejemplo de cómo pueden ser una respuesta y un resumen de las respuestas después que se ejecute un flujo.

![tokens de respuesta](media/all-assigned-must-approve/response-output.png)

## <a name="learn-more-about-approvals"></a>Más información acerca de las aprobaciones

* [Aprobaciones modernas de un aprobador único](modern-approvals.md)
* [Aprobaciones modernas secuenciales](sequential-modern-approvals.md)
* [Aprobaciones modernas en paralelo](parallel-modern-approvals.md)
* [Aprobaciones y Common Data Service](common-data-model-approve.md)
* [Aprobar solicitudes sobre la marcha](mobile-approvals.md)
