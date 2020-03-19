---
title: Ejecución de flujos de interfaz de usuario desde otros flujos | Microsoft Docs
description: Ejecute de flujos de interfaz de usuario desde otros flujos en modo atendido o desatendido.
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
ms.date: 03/03/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0852e8b52f7b158d8fc97316b0f719f8e557a15f
ms.sourcegitcommit: 14ea422c0b306f738757036cc0e240584dd810f5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79188116"
---
# <a name="run-attended-and-unattended-ui-flows"></a>Ejecución de flujos de interfaz de usuario atendidos y desatendidos

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

    - **Puerta de enlace**: Seleccione la puerta de enlace que creó anteriormente o use **Nueva puerta de enlace** para crear una.   
    - **Dominio y nombre de usuario**: muestra la cuenta profesional o educativa del dispositivo.
    - **Contraseña**: proporcione la contraseña de la cuenta profesional o educativa.

      ![Configuración del dispositivo](../media/run-ui-flow/uiflow-connection-card.png "Configuración de la conexión")

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

## <a name="run-ui-flows-unattended-or-attended"></a>Ejecución de flujos de interfaz de usuario en modo atendido o desatendido

Cuando se crean flujos de interfaz de usuario, se ejecutan en modo **atendido** o **desatendido**. El modo desatendido es más adecuado para aplicaciones que no necesitan supervisión humana.

Al ejecutarse en modo desatendido, la aplicación de flujos de interfaz de usuario inicia sesión automáticamente en los dispositivos de destino que ejecutan Windows 10, Windows Server 2016 o Windows Server 2019. Una vez completada la automatización, la aplicación de flujos de interfaz de usuario cierra la sesión en el dispositivo y notifica su actividad en Power Automate.

Al ejecutarse en modo atendido, la aplicación de flujos de interfaz de usuario usará una sesión de usuario de Windows existente.

Los flujos de la interfaz de usuario elegirán entre modos atendidos y desatendidos según el estado del equipo, según se describe más adelante en este artículo.

### <a name="unattended-mode"></a>Modo desatendido

Para ejecutar flujos de interfaz de usuario desatendidos, el equipo de destino debe estar disponible y que todos los usuarios hayan cerrado sesión. Las sesiones de usuario bloqueadas de Windows impiden que se ejecuten los flujos de interfaz de usuario.

Los flujos de interfaz de usuario realizan lo siguiente:
1. Los flujos de interfaz de usuario crean, administran y después liberan la sesión de usuario de Windows en los dispositivos de destino.

1. Los flujos de interfaz de usuario en modo desatendido se ejecutarán en dispositivos que tienen la pantalla bloqueada.

1. Los dispositivos con Windows 10 no pueden ejecutar en modo desatendido si hay alguna sesión de usuario de Windows activa en el dispositivo (incluso si está bloqueada). Recibirá este error: *No se puede ejecutar el flujo de interfaz de usuario. Hay una sesión de usuario de Windows bloqueada o inactiva en el dispositivo de destino*.

1. En Windows Server, si tiene una sesión de usuario de Windows bloqueada abierta con el mismo usuario con el que se supone que se ejecuta el flujo de la interfaz de usuario, recibirá el mismo error: *No se puede ejecutar el flujo de interfaz de usuario. Hay una sesión de usuario de Windows bloqueada o inactiva en el dispositivo de destino*.

### <a name="attended-mode"></a>Modo atendido
Para ejecutar un flujo de interfaz de usuario atendido, debe tener una sesión de usuario de Windows activa que coincida con el nombre del usuario configurado para la conexión. La sesión no debe estar bloqueada.

Si se está ejecutando un flujo de interfaz de usuario atendido en el equipo de destino, se recomienda evitar las interacciones con el dispositivo (por ejemplo, mover el mouse) hasta que se complete la ejecución.


## <a name="schedule-multiple-ui-flows-on-the-same-device"></a>Programación de varios flujos de interfaz de usuario en el mismo dispositivo

Se pueden programar varios flujos de interfaz de usuario para que se ejecuten en uno o varios dispositivos. Si en un mismo dispositivo se desencadenan varias ejecuciones de flujo de interfaz de usuario, el back-end de flujos de interfaz de usuario organiza las ejecuciones siguiendo estas reglas:

1.  Envía el primer flujo de interfaz de usuario al dispositivo de destino.

1.  Pone en cola otros flujos de interfaz de usuario y los muestra **en espera** en la página de flujos de interfaz de usuario o de detalles de puerta de enlace.

1.  Envía el siguiente flujo de interfaz de usuario cuando se completa una ejecución.

>[!NOTE]
>Estas reglas de orquestación se aplican a los flujos de interfaz de usuario programados por el mismo usuario o por usuarios diferentes en el mismo dispositivo.

>[!IMPORTANT]
>Si hay demasiados flujos de interfaz de usuario en la cola de ejecución, podría producirse un error de tiempo de espera. Actualmente, se producirá un error en las ejecuciones de flujo de interfaz de usuario si no se ejecutan en un plazo de 30 minutos después de desencadenarse.

## <a name="rerun-failed-ui-flows"></a>Volver a ejecutar los flujos de interfaz de usuario con errores

Si se produce un error en una ejecución de flujo de interfaz de usuario, puede intentar ejecutarla después de corregir la causa del error o, en ciertos casos, solucionar la ejecución que ha dado error.

1. Vaya a la página de detalles de flujos de interfaz de usuario e identifique la ejecución con error que quiere volver a ejecutar.

1. Seleccione el flujo primario de la ejecución en la que está interesado.

   Esto le lleva a la ejecución del flujo principal en la que se produjo un error en el flujo de interfaz de usuario.

1. En el menú Acción, seleccione el botón Volver a enviar.

## <a name="troubleshoot-failures"></a>Solución de errores

### <a name="failed-ui-flows"></a>Flujos de interfaz de usuario con errores

1. Si el flujo de interfaz de usuario desatendida produce el error **No se puede crear una nueva sesión**, siga estos pasos para resolver el problema:

    1.  En Windows 10, confirme que no tiene una sesión de usuario activa bloqueada o desbloqueada en el dispositivo de destino.
    1.  En Windows Server 2016 o Windows Server 2019, confirme que no ha alcanzado el número máximo de sesiones de usuario activas configuradas para el equipo, dado que no se podrán crear nuevas sesiones para ejecutar nuevos flujos de interfaz de usuario.

### <a name="ui-flows-app-status"></a>Estado de la aplicación de flujos de interfaz de usuario

La aplicación de flujos de interfaz de usuario es el software que se instala en el equipo local y que administra y ejecuta ejecuciones de flujo de interfaz de usuario. Permite a nuestros servicios en la nube de flujos de interfaz de usuario comunicarse y coordinar flujos en el equipo.

En la lista de puertas de enlace y en las páginas de detalles de puerta de enlace verá el estado actual de la aplicación de flujos de interfaz de usuario para cada dispositivo.

![Captura de pantalla que muestra la lista de puertas de enlace](../media/run-ui-flow/gateway-list.png)

La aplicación de flujos de interfaz de usuario puede estar en los siguientes estados:

1. **Disponible**: la aplicación de flujos de interfaz de usuario está en línea y lista para ejecutar flujos de interfaz de usuario.

1. **En ejecución**: se están ejecutando uno o varios flujos de interfaz de usuario en la máquina. Cualquier otro flujo de interfaz de usuario que el back-end envíe al dispositivo de destino se pondrá en cola y esperará su turno para ejecutarse.

1. **Corregir conexión a la puerta de enlace**: el servicio en la nube de flujo de interfaz de usuario no puede acceder al dispositivo de destino, probablemente porque hay un problema con la conexión de la puerta de enlace. Para resolver este problema, vaya a la conexión y confirme que las credenciales que usa son correctas.

1. **Desconocido**: este estado significa que el back-end no puede acceder a la aplicación de flujos de interfaz de usuario.

    1. Si el **estado de puerta de enlace** es **sin conexión**, confirme que el dispositivo está encendido y conectado a Internet. También puede [solucionar los problemas de la puerta de enlace](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot).

    1. Si el **estado de la puerta de enlace** es **en línea**, intente realizar las siguientes acciones:

        1. Confirme que la aplicación de flujos de interfaz de usuario y los servicios se están ejecutando en el dispositivo.

        1. Reinicie el servicio de flujo de interfaz de usuario en el dispositivo.

## <a name="learn-more"></a>Más información

 - Instale la [puerta de enlace de datos local](https://docs.microsoft.com/data-integration/gateway/service-gateway-app).
 - [Use la documentación de la aplicación Puerta de enlace de datos local](https://docs.microsoft.com/flow/gateway-manage).
 - [Solucione los problemas](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) de la puerta de enlace de datos local.
