---
title: Inicio de flujos con botones Bttn | Microsoft Docs
description: Más información acerca de cómo iniciar los flujos con un bttn
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4eaafb1a551cc3333cde2058aebc41076b0267bd
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297151"
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Ejecutar los flujos con botones físicos (bttn) de The Button Corporation (versión preliminar)

Desencadene los flujos presionando un bttn (un botón físico realizado por [The Button Corporation](https://my.bt.tn/)). Por ejemplo, puede presionar un bttn que desencadene un flujo para llevar a cabo estas tareas:

* pone en contacto al departamento de soporte técnico con la información de ubicación
* envía un correo electrónico al equipo
* bloquea el calendario
* vuelve a solicitar suministros

> [!IMPORTANT]
> Debe [registrar](https://my.bt.tn/) su bttn antes de poder usarlo en un flujo.
> 
> [!TIP]
> Antes de crear el flujo, configure todas las propiedades de los bttn como nombre, ubicación y dirección de correo electrónico en el [sitio web de bttn](https://my.bt.tn/).
> 
> 

También puede desencadenar un flujo mediante un [botón físico Flic](flic-button-flows.md).

## <a name="prerequisites"></a>Requisitos previos
* Tener acceso a [Power Automate](https://flow.microsoft.com).
* Al menos un [bttn registrado](https://my.bt.tn/).

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>Crear un flujo desencadenado por un bttn
En este tutorial, se utiliza una plantilla de departamento de soporte técnico para crear un flujo que se puede desencadenar con tan solo pulsar un [bttn](https://my.bt.tn/). Cuando se ejecuta el flujo, se genera una solicitud de soporte técnico y, después, se envía al departamento de soporte técnico. La solicitud de soporte técnico proporciona al departamento de soporte técnico la ubicación de la sala donde se necesita ayuda. En este tutorial se muestra cómo crear este flujo desde una plantilla, pero puede usar la plantilla en blanco, que proporciona control total sobre todos los aspectos del flujo.

Puede usar cualquiera de estas plantillas para crear flujos rápidamente para su bttn y conectarse a Zendesk, Google y SharePoint, entre otros:

![plantillas de bttn](./media/bttn-button-flows/bttn-templates.png)

Sugerencia: Para los fines de este tutorial, asigne un nombre al bttn que represente una sala de conferencias en un edificio de oficinas convencional.

La configuración del bttn debe ser similar a la de este ejemplo (del sitio web de bttn):

![plantillas de bttn](./media/bttn-button-flows/bttn-config.png)

Ahora que ha registrado y configurado el bttn, vamos a empezar a crear el flujo.

### <a name="sign-in-and-select-a-template"></a>Inicio de sesión y selección de una plantilla
1. Inicie sesión en [Power Automate](https://flow.microsoft.com).
   
    ![iniciar sesión](./media/bttn-button-flows/sign-into-flow.png)
   
    Nota: Como alternativa, puede crear flujos en la aplicación móvil de Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).
2. Escriba **bttn** en el cuadro de búsqueda y seleccione el icono de búsqueda.
   
    ![buscar](./media/bttn-button-flows/bttn-search-template.png)
   
    Después de seleccionar el icono de búsqueda, aparecen todas las plantillas que puede usar con bttn.
3. Seleccione la plantilla **Use Bttn to call technical support for meeting room** (Usar Bttn para llamar al soporte técnico para la sala de reuniones).
   
    ![plantilla de soporte técnico](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-power-automate-to-connect-to-your-bttn"></a>Autorizar a Power Automate para conectar a bttn
1. Si se le solicita, inicie sesión en el bttn y en los servicios de Outlook de Office 365, lo que habilitará el botón **Continuar**.
   
    ![credenciales](./media/bttn-button-flows/bttn-provide-credentials.png)
2. Al iniciar sesión en el servicio bttn, autorice a Power Automate a usar sus bttn.
   
    **Importante**: Si no autoriza a Power Automate para usar sus bttns, no podrá verlos ni conectarse a ellos desde Power Automate.
   
    ![autorizar](./media/bttn-button-flows/authorize-bttn.png)
3. Después de iniciar sesión en ambos servicios, seleccione **Continuar**.
   
    ![Continuar](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>Selección del bttn que desencadena el flujo
1. En la tarjeta **When a bttn is pressed** (Cuando se presiona un bttn), abra la lista de identificadores de bttns y, después, seleccione el bttn que desea usar.
   
    ![seleccionar bttn](./media/bttn-button-flows/bttn-id.png)
   
    El flujo ahora debe ser similar al de este ejemplo.
   
    ![información general del flujo](./media/bttn-button-flows/bttn-done.png)
2. Asigne un nombre a su flujo y, después, seleccione **Crear flujo** para guardarlo.
   
    ![guardar flujo](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>Prueba del flujo y confirmación de los resultados
1. Presione el botón en el bttn.
2. Consulte el historial de ejecución de flujo para confirmar que se ejecutó correctamente.
   
    Puede comprobar el historial de ejecución en el sitio web de Power Automate o en el dispositivo móvil.
   
    Nota: El estado de ejecución se establece en **En ejecución** hasta que un usuario selecciona **Confirmación** en el correo electrónico de solicitud de soporte técnico.
3. También puede confirmar que el correo electrónico se envió al equipo de soporte técnico.
   
    Si ha seguido estos pasos, el correo electrónico de soporte técnico tendrá un aspecto similar al de este ejemplo:
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>Solución de problemas
* Si no se desencadena el flujo, inicie sesión en el sitio de The Button Corporation y confirme si se está grabando la actividad de botón (pulsaciones).
* También puede profundizar en la actividad de ejecución en el sitio de Power Automate y comprobar si hay mensajes de error.

## <a name="more-information"></a>Más información
* [Compartir flujos de botones en Microsoft Flow](share-buttons.md).
* Aprenda a usar [tokens de desencadenadores de botones](introduction-to-button-trigger-tokens.md) para enviar datos actuales cuando se ejecuten los flujos de botón.
* [Instale la aplicación Power Automate para Android](https://aka.ms/flowmobiledocsandroid).
* [Instale la aplicación Power Automate para iOS](https://aka.ms/flowmobiledocsios).

