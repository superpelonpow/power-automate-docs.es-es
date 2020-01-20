---
title: Introducción a Tarjetas adaptables para Teams | Microsoft Docs
description: Aprenda a usar tarjetas adaptables en Microsoft Teams.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/01/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7b39474bbc59ba059fd73f2edc7f9b5750edbec2
ms.sourcegitcommit: e3543e32e4e8e8163bef0565e27b657eabbdc741
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2020
ms.locfileid: "75868765"
---
# <a name="overview-of-adaptive-cards-for-microsoft-teams"></a>Introducción a Tarjetas adaptables para Microsoft Teams

<br>
<iframe width="1129" height="635" src="https://www.youtube.com/embed/FqQ3jM2qPRM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


Las tarjetas adaptables constituyen un método independiente de la plataforma para compartir y mostrar bloques de información sin la complejidad de personalizar CSS o HTML para representarlos. Puede crear tarjetas adaptables en formato JSON, con integraciones que las aplicaciones y los servicios en la nube pueden intercambiar de forma abierta. Cuando se entrega a un host específico, como Microsoft Teams, el formato JSON se transforma en una interfaz de usuario nativa que se adapta automáticamente al host. Por lo tanto, los diseñadores de procesos pueden ofrecer ahora patrones de interfaz de usuario coherentes siempre que necesiten mostrar información como parte de una automatización o un proceso de negocio.
 
Dado que las tarjetas adaptables se ajustan al host, son vehículos perfectos para compartir información entre Microsoft Teams y otros servicios.

  ![Captura de pantalla de Tarjetas adaptables](media/adaptive-cards/multi-adaptive-cards.png)
 
## <a name="currently-available-actions-for-flows"></a>Acciones disponibles actualmente para flujos
 
Las siguientes acciones permiten a los desarrolladores crear tarjetas adaptables para Microsoft Teams. A medida que los escenarios de integración evolucionen, Power Automate admitirá también otros hosts, lo que ampliará sus oportunidades de aprovechar Tarjetas Adaptables a través de las suscripciones a la nube de Microsoft.
 
## <a name="directing-content-to-teams-members-or-aad-users"></a>Direccionamiento de contenido a **miembros de Teams o usuarios de AAD**
 
- **Muestre su propia tarjeta adaptable como el bot de Flow a un usuario**  
  Esta acción publica una tarjeta adaptable como bot de Flujo para un usuario específico. En este caso, deberá proporcionar una dirección de correo electrónico de destinatario y la tarjeta se mostrará en el chat del destinatario o en las fuentes de actividades durante la ejecución del flujo. No es necesario que el usuario forme parte de una instancia de Teams para recibir estos tipos de tarjetas adaptables. En este caso, solo los botones de dirección URL funcionan redirigiendo a la URL que se configura dentro del flujo.

    ![Ejemplos de tarjetas adaptables](media/adaptive-cards/top.png)
 
- **Post an adaptive card as the Flow bot to a Teams user, and wait for a response** (Publique una tarjeta adaptable como bot de Flow en un usuario de Teams y espere respuesta)  
  Esta acción publica una tarjeta adaptable como bot de Flow para un usuario específico, como el caso presentado anteriormente en este artículo. Aunque, en este caso, la ejecución de flujo no continuará después de la publicación hasta que el destinatario responda a las entradas que se requieren en la tarjeta. El flujo continúa después de que el destinatario responda. El flujo devuelve contenido dinámico para una (1) sola respuesta por destinatario y por tarjeta.
 
## <a name="directing-content-to-teams-channels"></a>Direccionamiento de contenido a **canales de Teams**
 
- **Muestre su propia tarjeta adaptable como el bot de Flow en un canal**  
  Esta acción publica una tarjeta adaptable como bot de Flujo en un canal específico de Teams. En este caso, se le pedirá la instancia de Teams y un canal en el que se publicará la tarjeta. El marcador de Flow ha de tener acceso a la instancia de Teams para publicar allí una tarjeta adaptable. En este caso, solo los botones de dirección URL funcionan redirigiendo a la URL que se configura dentro del flujo.
 
- **Post an adaptive card as the Flow bot to a Teams channel, and wait for a response** (Publique una tarjeta adaptable como bot de Flow en un canal de Teams y espere respuesta)  
  Esta acción publica una tarjeta adaptable como bot de Flow en un canal específico de Teams, como en el caso anterior. Aunque, en este caso, el flujo no continuará hasta que alguien en el canal haya respondido a las entradas que se requieren en la tarjeta. El flujo continuará cuando alguien del canal de Teams responda, pero solo devolverá contenido dinámico para una (1) sola respuesta por respondedor y tarjeta.
 
     ![](media/adaptive-cards/bottom.png)

     >[!TIP]
     >Cuando se usa esta tarjeta, el flujo espera respuesta de cualquier miembro de Teams.
 
 
## <a name="known-issues"></a>Problemas conocidos
 
- No es posible recopilar datos de las tarjetas adaptables a menos que se creen con una de las acciones "en espera de respuesta". Las tarjetas adaptables que no esperan devuelven un error en todas las acciones de botón excepto OpenURL. Obtenga más información sobre [botones de OpenURL](https://adaptivecards.io/explorer/Action.OpenUrl.html). 

- Si selecciona botones Action.Submit en una tarjeta que no incluya el sufijo "en espera de respuesta", se producirá un error.
 
- Las tarjetas adaptables creadas con las acciones "en espera de respuesta" solo se pueden enviar una vez por tarjeta. La ejecución de flujo continuará después de la primera respuesta y se omitirán los envíos posteriores.
 
- Solo se mostrará la información incluida en el cuadro de entrada "Actualizar mensaje" (consulte la imagen 3) en la tarjeta de reemplazo después de que los consumidores envíen la tarjeta.

  Los detalles adicionales, como el identificador de usuario de la persona que envía la tarjeta, estarán disponibles en el contenido dinámico de las acciones que siguen a la acción "en espera de respuesta". Aunque puede que sea necesario incluir el conector de usuarios de Office 365 para poder completar la información de perfil deseada para el usuario que envió la tarjeta.
 
- Una vez que las tarjetas adaptables "en espera de respuesta" se envían, la tarjeta se restablece y luego aparece exactamente igual, a menos que se configure el área de mensajes de reemplazo o actualización. Los mensajes de actualización son un procedimiento recomendado que se propone para actualizar a otros, pero también para evitar que los consumidores intenten enviar la tarjeta más de una vez.
 
   ![Mensaje de actualización](media/adaptive-cards/update-message.png) 
 
>[!TIP]
>Se han de configurar las entradas de **Actualizar mensaje** y **Se recomienda actualizar la tarjeta** si se quiere una tarjeta de reemplazo.
 
- Power Automate usa las características y los servicios exclusivos de Tarjetas adaptables de Microsoft para administrar las tarjetas de cualquier host. El objetivo de este artículo es aclarar cualquier información específica relacionada con las acciones de flujo. También puede usar la documentación completa sobre [creación de tarjetas adaptables](https://docs.microsoft.com/adaptive-cards/).
 
## <a name="learn-more"></a>Más información 
 
- Creación de su [primera tarjeta adaptable](https://docs.microsoft.com/power-automate/create-adaptive-cards)
- Documentación completa sobre el [conector de Microsoft Teams](https://docs.microsoft.com/connectors/teams/)
- Documentación completa sobre [E/S de tarjetas adaptables](https://docs.microsoft.com/adaptive-cards) 

