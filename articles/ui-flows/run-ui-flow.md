---
title: Ejecución de flujos de interfaz de usuario desde otros flujos | Microsoft Docs
description: Ejecución de flujos de interfaz de usuario desde otros flujos
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3feab8291a3dc14adab398f7619fd5b6141674ab
ms.sourcegitcommit: 26cda5060446812f3725ccd4fe435839088f50fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "78244228"
---
# <a name="run-ui-flows"></a>Ejecución de los flujos de la interfaz de usuario

[Este tema es documentación preliminar y está sujeto a cambios].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Después de crear y probar un flujo de interfaz de usuario, puede ejecutarlo desde un evento, una programación o un botón. Para que esto sea posible, agregue el flujo de interfaz de usuario a un [flujo automatizado](../get-started-logic-flow.md), un [flujo de botón](../introduction-to-button-flows.md), un [flujo programado](../run-scheduled-tasks.md) o un [flujo de proceso empresarial](../business-process-flows-overview.md).

## <a name="prerequisites"></a>Requisitos previos

- Necesita la [puerta de enlace de datos local](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409) para que Power Automate desencadene el flujo de interfaz de usuario del dispositivo.
   
   La puerta de enlace es una conexión segura de nivel empresarial entre Power Automate y el dispositivo (donde se ejecuta el flujo de interfaz de usuario). Power Automate usa la puerta de enlace para acceder al dispositivo local para que pueda desencadenar los flujos de interfaz de usuario desde un evento, una programación o un botón.
- Una cuenta profesional o educativa. 

   >[!IMPORTANT]
   >Debe usar la misma cuenta profesional o educativa para configurar la puerta de enlace, para iniciar sesión en Power Automate y para iniciar sesión en el dispositivo Windows.
   

## <a name="run-your-ui-flow-from-an-event-button-schedule-or-business-process-flow"></a>Ejecución de un flujo de interfaz de usuario desde un flujo de evento, botón, programación o proceso empresarial

En este ejemplo, usaremos un flujo automatizado para desencadenar un flujo de interfaz de usuario cuando llega un correo nuevo.

1. Navegue a [Power Automate](https://flow.microsoft.com/).
1. Seleccione **Mis flujos** en la barra de navegación de la izquierda.
1. Seleccione **Nuevo** y después **Automatizado: desde cero**.

   >[!TIP]
   >Puede elegir cualquier otro tipo de flujo que se ajuste a sus necesidades.

1. Asigne un nombre al flujo en el cuadro **Nombre del flujo**.
1. Busque "correo electrónico nuevo" y, después, seleccione **Cuando llega un correo electrónico nuevo (V3)** en la lista de desencadenadores. 
    
   ![Selección de un desencadenador](../media/run-ui-flow/2d4ec17d239169a46905cef1829fa3a1.png "Selección de un desencadenador")

1. Seleccione **Crear** y, luego, seleccione **Nuevo paso**.

1. Busque **Flujos de interfaz de usuario** y seleccione **Ejecutar flujo de interfaz de usuario para el escritorio** en la lista de **acciones**. 

   ![Acción de búsqueda](../media/run-ui-flow/search-action.png "Acción de búsqueda")

1. Proporcione la información de puerta de enlace y las credenciales del dispositivo. 

   Tendrá que hacerlo una vez por dispositivo:

    - **Nombre de la conexión**: elija un nombre para la conexión del dispositivo a Flow. Puede ser diferente del nombre de la puerta de enlace.
    - **Nombre de usuario**: proporcione la cuenta profesional o educativa del dispositivo.
    - **Tipo de autenticación**: Seleccione Windows.
    - **Contraseña**: la contraseña de la cuenta profesional o educativa.
    - **Puerta de enlace**: seleccione la puerta de enlace que creó durante la instalación.

      ![Configuración del dispositivo](../media/run-ui-flow/connection-settings.png "Configuración de la conexión")

      >[!TIP]
      >Si no ve la puerta de enlace, es posible que tenga que seleccionar otra conexión. Para hacerlo, seleccione **…** en la parte superior derecha de la tarjeta **Ejecutar flujo de interfaz de usuario para el escritorio (versión preliminar)** y, luego, seleccione la conexión que quiere usar en **Mis conexiones**.

      ![Selección de una conexión nueva](../media/run-ui-flow/select-new-connection.png "Selección de una conexión nueva")

1. Seleccione el flujo de interfaz de usuario que creó anteriormente.

   ![Selección del flujo de interfaz de usuario](../media/run-ui-flow/select-ui-flow.png "Selección del flujo de interfaz de usuario")

1. Seleccione **Guardar** para guardar el flujo automatizado.

1. Para probar el flujo, envíe un corre electrónico para desencadenarlo. Verá que el flujo de interfaz de usuario reproduce los pasos que grabó. 

![Ejecución correcta que llama a un flujo de interfaz de usuario](../media/run-ui-flow/successful-run.png "Ejecución correcta que llama a un flujo de interfaz de usuario")

>[!TIP]
>No interactúe con el dispositivo mientras se ejecuta el flujo.

## <a name="use-inputs-and-outputs"></a>Uso de las entradas y salidas

Cuando define entradas y salidas dentro de un flujo de interfaz de usuario, puede pasar información desde y hacia esas entradas.

1. Al agregar un flujo de interfaz de usuario a un flujo, puede ver la lista de entradas que se definieron en el flujo de la interfaz de usuario.

   ![Entradas de flujo de interfaz de usuario](../media/run-ui-flow/inputs.png "Entradas de flujo de interfaz de usuario")

1. Puede rellenar cada campo de entrada en el flujo de interfaz de usuario con los valores de los pasos anteriores del flujo. Para hacerlo, seleccione el campo de entrada y, a continuación, seleccione una entrada del selector de tokens.


1. También puede usar las salidas del flujo de la interfaz de usuario como entradas para las acciones que aparecen más adelante en el flujo. Para hacerlo, seleccione el campo de entrada y, a continuación, seleccione una entrada del selector de tokens.


## <a name="learn-more"></a>Más información

 - Instale la [puerta de enlace de datos local](https://docs.microsoft.com/data-integration/gateway/service-gateway-app).
 - [Use la documentación de la aplicación Puerta de enlace de datos local](https://docs.microsoft.com/flow/gateway-manage).
 - [Solucione los problemas](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) de la puerta de enlace de datos local.
