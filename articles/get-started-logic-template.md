---
title: Creación de un flujo a partir de una plantilla | Microsoft Docs
description: Cree un flujo de cualquiera de las diversas plantillas integradas.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/07/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8ccb933188902b89fa45b65cfec0d3d0e96de4c8
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195713"
---
# <a name="create-a-flow-from-a-template-in-power-automate"></a>Creación de un flujo desde una plantilla en Power Automate

Cree un flujo desde una de las muchas plantillas integradas que pueden, por ejemplo, enviarle un mensaje Slack cuando un administrador le envíe un correo electrónico en Office 365.

**Nota**: use la opción [Crear un flujo desde cero](get-started-logic-flow.md) si ya tiene un proceso en mente y no encuentra una plantilla para él.

**Requisitos previos**

* Una cuenta en [flow.microsoft.com](https://flow.microsoft.com)
* Una cuenta de Slack
* Credenciales de Office 365

## <a name="choose-a-template"></a>Elegir una plantilla
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. En [flow.microsoft.com](https://flow.microsoft.com), seleccione **Plantillas** en la barra de navegación superior.
2. En la barra de búsqueda, escriba **Slack** y, a continuación, seleccione el icono de búsqueda.
3. Verá solo las plantillas relacionadas con Slack, por lo que ahora puede seleccionar **Enviar un mensaje en Slack cuando el administrador me envíe un correo electrónico**.
   
    ![Nueva opción de la barra de navegación izquierda](./media/get-started-logic-template/select-template.png)
4. Confirme que esta plantilla hará lo que desea y, después, seleccione **Usar esta plantilla**.
5. Si no ha iniciado sesión en Office o Slack, seleccione **Iniciar sesión** y, a continuación, siga las indicaciones.
   
    ![Lista de conexiones que requiere la plantilla](./media/get-started-logic-template/confirm-connections.png)
6. Después de confirmar las conexiones, seleccione **Continuar**.
   
    Aparece el flujo, que muestra cada acción con una barra de título de color naranja.
   
    ![Eventos y acciones predeterminadas de la plantilla](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>Personalización de un flujo
1. Seleccione la barra de título de un evento para expandirla y, a continuación, personalizarla (por ejemplo, mediante la especificación de un filtro en el correo electrónico que le interese).
2. Se expandirán automáticamente las acciones que requieran su intervención.
   
    Por ejemplo, la acción **Publicar mensaje** se expande porque es preciso especificar un canal, por ejemplo, su *\@nombredeusuario*. También puede personalizar el contenido del mensaje. De forma predeterminada, el mensaje contendrá solo el asunto, pero se puede incluir más información.
   
    ![Especificar el canal de Slack](./media/get-started-logic-template/specify-keyword.png)
3. Cerca de la parte superior de la pantalla, especifique el nombre del flujo y seleccione **Crear flujo**.
4. Por último, si está satisfecho con el flujo, seleccione **Listo**.
   
    ![Botón Listo](./media/get-started-logic-template/done.png)

Ahora, cuando el administrador le envíe un correo electrónico, recibirá un mensaje Slack que contiene la información que ha especificado.

## <a name="next-steps"></a>Pasos siguientes
* [Visualización de flujos en acción](see-a-flow-run.md)
* [Publicación de su propia plantilla](publish-a-template.md)
* [Uso de una plantilla para Common Data Service](common-data-model-intro.md)
* [Cree flujos de equipo](create-team-flows.md) e invite a otros a colaborar en el diseño de flujos.

