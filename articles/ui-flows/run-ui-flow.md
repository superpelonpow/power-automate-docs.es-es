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
ms.date: 03/24/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7d9142fa86b256ca816cf128f8b76bae7d1c5a90
ms.sourcegitcommit: 855ee8b55aebe7b8e202006c39debfff02df1d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "3298933"
---
# <a name="run-attended-and-unattended-ui-flows"></a>Ejecución de flujos de interfaz de usuario atendidos y desatendidos

Después de crear y probar un flujo de interfaz de usuario, puede ejecutarlo desde un evento, una programación o un botón. Para que esto sea posible, agregue el flujo de interfaz de usuario a un [flujo automatizado](../get-started-logic-flow.md), un [flujo de botón](../introduction-to-button-flows.md), un [flujo programado](../run-scheduled-tasks.md) o un [flujo de proceso empresarial](../business-process-flows-overview.md).

## <a name="prerequisites"></a>Requisitos previos

- Necesita la [puerta de enlace de datos local](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409) para que Power Automate desencadene el flujo de interfaz de usuario del dispositivo.
   
   La puerta de enlace es una conexión segura de nivel empresarial entre Power Automate y el dispositivo (donde se ejecuta el flujo de interfaz de usuario). Power Automate usa la puerta de enlace para acceder al dispositivo local para que pueda desencadenar los flujos de interfaz de usuario desde un evento, una programación o un botón.
- Una cuenta profesional o educativa. 

   >[!IMPORTANT]
   >Debe usar la misma cuenta profesional o educativa para configurar la puerta de enlace, para iniciar sesión en Power Automate y para iniciar sesión en el dispositivo Windows.
   

## <a name="run-your-ui-flow-from-an-event-button-schedule-or-business-process-flow"></a>Ejecución de un flujo de interfaz de usuario desde un flujo de evento, botón, programación o proceso empresarial

En este ejemplo, usaremos un flujo automatizado para desencadenar un flujo de interfaz de usuario cuando llega un correo nuevo.

1. Navegue hasta [Power Automate](https://flow.microsoft.com/).
1. Seleccione **Mis flujos** en la barra de navegación de la izquierda.
1. Seleccione **Nuevo** y después **Automatizado: desde cero**.

   >[!TIP]
   >Puede elegir cualquier otro tipo de flujo que se ajuste a sus necesidades.

1. Asigne un nombre al flujo en el cuadro **Nombre del flujo**.
1. Busque "correo electrónico nuevo" y, después, seleccione **Cuando llega un correo electrónico nuevo (V3)** en la lista de desencadenadores. 
    
   ![Selección de un desencadenador](../media/run-ui-flow/select-email-trigger.png "Selección de un desencadenador")

1. Seleccione **Crear** y, luego, seleccione **Nuevo paso**.

1. Busque **Flujos de interfaz de usuario** y seleccione **Ejecutar flujo de interfaz de usuario para el escritorio** en la lista de **acciones**. 

   ![Acción de búsqueda](../media/run-ui-flow/search-action.png "Acción de búsqueda")

1. Proporcione la información de puerta de enlace y las credenciales del dispositivo. 

   Tendrá que hacerlo una vez por dispositivo:

    - **Puerta de enlace**: seleccione la puerta de enlace que creó anteriormente o use **Nueva puerta de enlace** para crear una.   
    - **Dominio y nombre de usuario**: muestra la cuenta profesional o educativa del dispositivo.
       >[!Important]
        >Asegúrese de que puede iniciar sesión en el dispositivo con estas credenciales.  
    - **Contraseña**: proporciona su contraseña de la cuenta profesional o educativa.

      ![Configuración del dispositivo](../media/run-ui-flow/uiflow-connection-card.png "Configuración de conexión")

      >[!TIP]
      >Si no ve la puerta de enlace, es posible que se encuentre en un entorno cuya región sea diferente de la de la puerta de enlace. Seleccione **Solucionar problemas de una puerta de enlace que falta** en la lista de nombres de puerta de enlace para obtener más información. También puede confirmar la puerta de enlace y que las regiones de Power Automate se [asignen correctamente](../regions-overview.md#region-mappings-for-power-automate-and-gateways).

      >[!TIP]
      >Si no ve la puerta de enlace, es posible que tenga que seleccionar otra conexión. Para hacerlo, seleccione **…** en la parte superior derecha de la tarjeta **Ejecutar flujo de interfaz de usuario para el escritorio** o **Ejecutar flujo de interfaz de usuario para la Web** y, luego, seleccione la conexión que quiere usar en **Mis conexiones**.


      ![Selección de una conexión nueva](../media/run-ui-flow/select-new-connection.png "Selección de una conexión nueva")

1. Seleccione el flujo de interfaz de usuario que creó anteriormente.

   ![Selección del flujo de interfaz de usuario](../media/run-ui-flow/select-ui-flow.png "Selección del flujo de interfaz de usuario")

1. Seleccione **Guardar** para guardar el flujo automatizado.
 >[!TIP]
 >Antes de realizar las pruebas, confirme que la puerta de enlace está en línea. Vaya a **Datos** > **Puertas de enlace** en el panel de navegación, seleccione el nombre de la puerta de enlace, haga clic en **...**, vaya a **Detalles** y compruebe si el **estado de la puerta de enlace** es **en línea**. Si el **estado de la puerta de enlace** es **sin conexión**, compruebe que el dispositivo está encendido y conectado a Internet. 

1. Para probar el flujo, envíe un corre electrónico para desencadenarlo. Verá que el flujo de interfaz de usuario reproduce los pasos que ha grabado. 

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

Al ejecutarse en modo desatendido, la aplicación de flujos de interfaz de usuario inicia sesión automáticamente en los dispositivos de destino que ejecutan Windows 10, Windows Server 2016 o Windows Server 2019. Una vez completada la automatización, la aplicación de flujos de interfaz de usuario cierra la sesión en el dispositivo y notifica su actividad en Power Automate.

Al ejecutarse en modo atendido, la aplicación de flujos de interfaz de usuario usará una sesión de usuario de Windows existente.

Al agregar un flujo de interfaz de usuario a un flujo, puede elegir si quiere que el flujo de interfaz de usuario se ejecute en modo atendido o desatendido. Estas son algunas diferencias clave entre las ejecuciones atendidas y las desatendidas:

### <a name="unattended-mode"></a>Modo desatendido

Para ejecutar flujos de interfaz de usuario desatendidos, el equipo de destino debe estar disponible y que todos los usuarios hayan cerrado sesión. 

>[!IMPORTANT]
>Las sesiones de usuario bloqueadas de Windows impiden que se ejecuten los flujos de interfaz de usuario.

Los flujos de interfaz de usuario realizan lo siguiente:
1. Los flujos de interfaz de usuario crean, administran y, después, liberan la sesión de usuario de Windows en los dispositivos de destino.

1. Los flujos de interfaz de usuario desatendidos se ejecutan en dispositivos con la pantalla bloqueada para que nadie pueda verlos mientras se ejecutan.

1. Los dispositivos con Windows 10 no se pueden ejecutar en modo desatendido si hay alguna sesión de usuario de Windows activa (incluso si está bloqueada). Recibirá este error: *No se puede ejecutar el flujo de la interfaz de usuario. Hay una sesión de usuario de Windows bloqueada o inactiva en el dispositivo de destino*.

1. En Windows Server, si tiene una sesión de usuario de Windows bloqueada abierta con el mismo usuario con el que se debe ejecutar el flujo de la interfaz de usuario, recibirá el mismo error: *No se puede ejecutar el flujo de la interfaz de usuario. Hay una sesión de usuario de Windows bloqueada o inactiva en el dispositivo de destino*.

### <a name="attended-mode"></a>Modo atendido
Para ejecutar un flujo de interfaz de usuario atendido, debe tener una sesión de usuario de Windows activa que coincida con el nombre del usuario configurado para la conexión. La sesión no debe estar bloqueada.

Cuando se inicia un flujo de interfaz de usuario atendido en el equipo de destino, se recomienda no interactuar con el dispositivo hasta que se complete la ejecución.


## <a name="schedule-multiple-ui-flows-on-the-same-device"></a>Programación de varios flujos de interfaz de usuario en el mismo dispositivo

Se pueden programar varios flujos de interfaz de usuario para que se ejecuten en uno o varios dispositivos. Si se desencadena la ejecución de más de un flujo de interfaz de usuario en el mismo dispositivo, Power Automate seguirá estas reglas:

1.  El primer flujo de interfaz de usuario se ejecutará en el dispositivo de destino.

1.  Pone en cola otros flujos de interfaz de usuario y los muestra **En espera** en la página de detalles de flujos de interfaz de usuario y puertas de enlace.

1.  Selecciona el siguiente flujo de interfaz de usuario cuando se completa una ejecución.

>[!NOTE]
>Estas reglas de orquestación se aplican a los flujos de interfaz de usuario programados por un usuario o por usuarios diferentes en el mismo dispositivo.

>[!IMPORTANT]
>Si hay demasiados flujos de interfaz de usuario en la cola de ejecución, podría producirse un error de tiempo de espera. Se producirá un error en las ejecuciones de flujo de interfaz de usuario si no se ejecutan en un plazo de 30 minutos después de desencadenarse.

## <a name="load-balance-requests-across-gateways-in-a-cluster"></a>Solicitudes de equilibrio de carga entre puertas de enlace de un clúster

Puede optar por distribuir las ejecuciones de flujo de interfaz de usuario uniformemente entre las puertas de enlace de un clúster. De forma predeterminada, la selección de una puerta de enlace durante el equilibrio de carga es aleatoria.

Siga [estos pasos para agregar una puerta de enlace y crear un clúster](https://docs.microsoft.com/data-integration/gateway/service-gateway-install#add-another-gateway-to-create-a-cluster).

>[!NOTE]
>Los miembros de la puerta de enlace sin conexión dentro de un clúster afectarán negativamente al rendimiento. Deshabilite o quite esos miembros.

Para proporcionar equilibrio de carga desde la página de detalles de puertas de enlace de Power Automate, navegue a **Datos** -> **Puertas de enlace** y seleccione el clúster de puerta de enlace. 

En la página de detalles de puertas de enlace, active Ejecutar en todas las puertas de enlace del clúster. Se distribuirán las ejecuciones de flujos de interfaz de usuario en todas las puertas de enlace dentro de ese clúster.

   ![Distribución de la ejecución del flujo de interfaz de usuario en el clúster de puerta de enlace](../media/run-ui-flow/gw_cluster.png "Distribución de la ejecución del flujo de interfaz de usuario en el clúster de puerta de enlace")
   
>[!IMPORTANT]
>Si usa cuentas de Windows locales, todos los equipos del clúster deben tener la misma cuenta local con la misma contraseña. Use estas credenciales al crear la conexión de flujo de interfaz de usuario.
>Si usa equipos unidos de Active Directory o Azure AD, compruebe que la cuenta de usuario que va a usar en la conexión de flujo de interfaz de usuario puede acceder a todos los equipos del clúster.
   
## <a name="best-practices-to-avoid-timeouts-and-distribute-load-across-machines"></a>Prácticas recomendadas para evitar tiempos de espera y distribuir la carga entre equipos

Si planea ejecutar varios flujos de interfaz de usuario, hay una serie de estrategias que puede adoptar para distribuir la carga y asegurarse de que todos los flujos de interfaz de usuario se ejecutan correctamente sin sobrecargar los equipos de destino o provocar tiempos de espera porque se están ejecutando varios flujos de interfaz de usuario al mismo tiempo. Puede usar uno de los siguientes:

1. Planifique los flujos de interfaz de usuario para que se ejecuten en distintos momentos del día y se reparta la carga a lo largo del tiempo. Esto funciona mejor si tiene un conjunto de máquinas único o limitado que puede ejecutar cargas de trabajo y puede controlar los desencadenadores (por ejemplo, flujos programados) que inician los flujos de interfaz de usuario.
1. Cree clústeres de equipos que puedan ejecutar flujos de interfaz de usuario con configuraciones idénticas en paralelo. 
1. Cree varios flujos. Cada uno debe usar una conexión independiente con distintos equipos como destino. 

Al seguir estas estrategias, puede evitar que varios flujos de interfaz de usuario intenten ejecutarse en el mismo dispositivo y, en algunos casos, se produzca un error de tiempo de espera. 

>[!NOTE]
>Si está ejecutando flujos de interfaz de usuario en modo desatendido, tendrá que prever el número de flujos de interfaz de usuario que planea ejecutar la organización en paralelo y adquirir una cantidad adecuada de complementos desatendidos. 


## <a name="rerun-failed-ui-flows"></a>Volver a ejecutar los flujos de interfaz de usuario con errores

Si se produce un error al ejecutar un flujo de interfaz de usuario, corríjalo y siga estos pasos para volver a ejecutarlo: 

   1. Vaya a la página de detalles e identifique la ejecución con errores.

   1. En el menú Acción, seleccione el botón **Volver a enviar**.

## <a name="troubleshoot-failures"></a>Solucionar problemas de fallos

1. Si el flujo de interfaz de usuario desatendido produce el error **No se puede crear una nueva sesión**, siga estos pasos para resolver el problema:

    - En Windows 10, confirme que no tiene una sesión de usuario activa bloqueada o desbloqueada en el dispositivo de destino.
    - En Windows Server 2016 o Windows Server 2019, confirme que no ha alcanzado el número máximo de sesiones de usuario activas configuradas para el dispositivo. Los flujos de interfaz de usuario no podrán ejecutarse si no pueden crear nuevas sesiones.

1. Si está ejecutando flujos de interfaz de usuario en un sistema operativo con un idioma distinto del inglés y recibe el mensaje *502: Solicitud incorrecta*, confirme que ha seguido los [pasos para actualizar los flujos de interfaz de usuario de la versión preliminar](upgrade.md).


1. Si el **estado de puerta de enlace** es **sin conexión**, confirme que el dispositivo está encendido y conectado a Internet. También puede [solucionar los problemas de la puerta de enlace](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot).

1. Si el **estado de la puerta de enlace** es **en línea**, intente realizar las siguientes acciones:

   - Confirme que la aplicación de flujos de interfaz de usuario y los servicios se están ejecutando en el dispositivo.

   - Reinicie el servicio de flujo de interfaz de usuario en el dispositivo.

## <a name="learn-more"></a>Más información

 - Instale la [puerta de enlace de datos local](https://docs.microsoft.com/data-integration/gateway/service-gateway-app).
 - [Use la documentación de la aplicación Puerta de enlace de datos local](https://docs.microsoft.com/flow/gateway-manage).
 - [Solucione los problemas](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) de la puerta de enlace de datos local.



