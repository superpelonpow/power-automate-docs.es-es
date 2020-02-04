---
title: Información acerca de la automatización y ejecución de tareas repetitivas con flujos de botones | Microsoft Docs
description: Introducción a los flujos de botones.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 136bb90c47a1aeea2f11ef45e35a4957506ad488
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74363922"
---
# <a name="introducing-button-flows"></a>Presentación de los flujos de botón
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-flows"></a>¿Qué son los flujos de botón?
Hay muchas tareas repetitivas que a todos nos gustaría que se pudieran ejecutar pulsando un botón. Por ejemplo, es posible que necesite enviar un correo electrónico rápido a su equipo para recordar a los componentes que se unan a la sincronización diaria del equipo o que desee iniciar una nueva compilación de Visual Studio Online de su código base después de haber notificado que no hay más protecciones planeadas para ese día. Los flujos de botón permiten realizar estas y muchas otras tareas simplemente pulsando un botón del dispositivo móvil.

**Nota** Los flujos de botón se pueden crear desde un dispositivo móvil o desde el portal de Flow.  
  ![Imagen de información general](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>¿Por qué crear botones?
Cree botones para poder ejecutar fácilmente tareas repetitivas desde cualquier lugar y en cualquier momento a través de un dispositivo móvil. Los botones de ejecución ahorran tiempo y, como las tareas que realizan están automatizadas, habrá menos errores que si se realizaran manualmente.  

## <a name="create-a-button"></a>Creación de un botón
### <a name="prerequisites"></a>Requisitos previos
* Acceso a Flow. El administrador puede proporcionarle dicho acceso.
* Una cuenta con permisos para utilizar los conectores para crear el botón. Por ejemplo, necesitará una cuenta de Dropbox para crear un botón que acceda a Dropbox.

### <a name="from-the-portal"></a>Desde el portal
En este tutorial, vamos a crear un botón que inicia una compilación de Visual Studio Online (VSO) y envía notificaciones que le permiten saber en qué momento se inicia la compilación:  

1. Seleccione la lista desplegable **Mostrando** y elija la categoría **Botón**. Así se filtra la lista de plantillas para que aparezcan solo las que puede usarse en flujos de botón.  
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-1.png)   
2. Seleccione la plantilla **Trigger a new build in VSO** (Desencadenar una compilación nueva en VSO) en la lista.  
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-2.png)  
3. Haga clic en el botón **Usar esta plantilla** de la página **Trigger a new build in VSO** (Desencadenar una compilación nueva en VSO).   
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-3.png)  
4. Si no ha iniciado sesión, se le pedirá que lo haga en este momento:  
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-4.png)  
5. Después de iniciar sesión en Flow, se le solicitará que inicie sesión en los conectores que se usan en la plantilla que ha seleccionado. En este ejemplo, en el paso 2 seleccionamos la plantilla **Trigger a new build in VSO** (Desencadenar una compilación nueva en VSO), por lo que tenemos que iniciar sesión en VSO (y en cualquier otro conector con el que trabaje), en caso de que no haya iniciado sesión:  
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Seleccione el  botón **Aceptar** botón si está de acuerdo en autorizar a Flow a acceder a su cuenta de VSO.  
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-5.png)   
   **Nota** Todos los conectores se deben autorizar de forma similar. El diseñador que aparecerá será similar al siguiente cuando esté listo para avanzar al paso siguiente. Seleccione el botón **Continuar** para avanzar:  
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-6.png)   
7. Ya está preparado para configurar las propiedades de la compilación que desea iniciar:    
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-7.png)  
8. Seleccione o escriba los datos pertinentes en **Account Name** (Nombre de cuenta), **Project name** (Nombre de proyecto), **Build definition Id** (Id. de definición de compilación) **Source branch** (Rama de origen) y, opcionalmente, **Parameters** (Parámetros), en la tarjeta **Queue a new build** (Poner en cola una compilación nueva):    
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-8.png)  
9. A continuación, configure las propiedades de la notificación push en la tarjeta **Send a push notification** (Enviar una notificación push). De manera predeterminada, esta notificación push está configurada para enviar un vínculo HTML a una página web que muestre el estado de la compilación:  
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-9.png)  
10. Seleccione el botón **Crear flujo** para guardar el flujo de botón: ![Imagen de información general](./media/introduction-to-button-flows/create-button-10.png)  
11. En poco tiempo verá este mensaje de operación correcta:  
    ![Imagen de información general](./media/introduction-to-button-flows/create-button-11.png)  

Enhorabuena, ha creado un flujo de botón. Ahora puede ejecutar este flujo de botón en cualquier momento y lugar desde la pestaña **Botones** de la aplicación Flow. Solo tiene que presionar el "botón" y se ejecutará. La aplicación móvil de Power Automate está disponible para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="from-your-mobile-device"></a>Desde un dispositivo móvil
**Nota:** en este tutorial se muestran las pantallas de un dispositivo Android, pero las de un dispositivo iOS son similares.

En la aplicación Flow:

1. Seleccione la pestaña **Browse** (Examinar) y desplácese hasta la categoría **Button** (Botón).  
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. Seleccione el vínculo **See all** (Ver todos). Se muestran todas las plantillas de botón listas para usar.     
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. Seleccione la plantilla **Send an email to remind your team to join a meeting** (Enviar un correo electrónico para recordar el equipo que se una a una reunión)    
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Seleccione el vínculo **USE THIS TEMPLATE** (USAR ESTA PLANTILLA) en la parte inferior de la página.    
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. Será preciso que inicie sesión en todos los servicios que usa esta plantilla:    
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Seleccione el vínculo **Next** (Siguiente) una vez que haya iniciado sesión en todos los servicios.      
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. Seleccionar el vínculo **Create** (Crear) Aquí también puede revisar el flujo y realizar los cambios necesarios para personalizar el correo electrónico, por ejemplo.        
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Transcurridos unos segundos se crea el flujo de botón. Seleccione **SEE MY FLOW** (VER MI FLUJO):   
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. Vea todos los flujos en la pestaña **My flows** (Mis flujos)  
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

Enhorabuena, ha creado un flujo de botón. Ahora puede ejecutar este flujo de botón en cualquier momento y lugar desde la pestaña **Botones** de la aplicación Flow. Solo tiene que presionar el "botón" y se ejecutará. La aplicación Flow está disponible actualmente en dispositivos móviles con iOS y Android.  

![Imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>Desencadenamiento de un flujo de botón
Ahora que ha creado un flujo de botón, ha llegado el momento de ejecutarlo. Dado que los flujos de botón solo se pueden ejecutar desde la aplicación Flow, asegúrese de haberla instalado en el dispositivo móvil con Android o iOS.  

1. Ahora, inicie la aplicación Flow, pulse la pestaña **Buttons** (Botones) que se encuentra en la parte inferior de la página y pulse el *botón* que representa el flujo de botón que desea desencadenar:  
   ![Imagen de información general](./media/introduction-to-button-flows/trigger-button-1.png)   
2. Vea el progreso mientras se ejecuta el flujo:  
   ![Imagen de información general](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Por último, se actualiza la página, lo que indica que se ha completado el flujo de botón:  
   ![Imagen de información general](./media/introduction-to-button-flows/trigger-button-3.png)   

Esta es toda la información sobre la ejecución de flujos. 

Ahora debe recibir la notificación push que indica que se ha enviado el correo electrónico.  

## <a name="monitor-your-button-flow-runs"></a>Supervisión de las ejecuciones de los flujos de botón
Los flujos de botón se pueden supervisar desde la pestaña **Activity** (Actividad) de la aplicación Flow:   
![Imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**Nota:** pulse cualquier actividad para aumentar el detalle de los resultados de la ejecución, con el fin de obtener información acerca de la ejecución.  

![Imagen de información general](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>Administración de flujos de botón
Tiene control total de los flujos de botón, por lo que puede habilitar o deshabilitar, editar o eliminar un botón en cualquier momento y lugar. En la aplicación móvil o el portal de Flow, seleccione **My flows** (Mis flujos) para empezar a administrar los flujos.    

En la pestaña **My flows** (Mi flujos) de la aplicación Flow:

1. Seleccione el flujo que desea administrar:    
   ![Imagen de información general](./media/introduction-to-button-flows/trigger-button-4.png)   
2. Puede pulsar cualquiera de estas opciones, en función de lo que le gustaría realizar:    
   ![Imagen de información general](./media/introduction-to-button-flows/manage-flow-1.png)  
3. Pulse **Delete flow** (Eliminar flujo) para eliminar un flujo.  

**Nota** Cuando se elimina un flujo se elimina todo el historial de ejecuciones:   
![Imagen de información general](./media/introduction-to-button-flows/manage-flow-2.png)   

1. Pulse **Update** (Actualizar) cuando termine de editar un flujo de botón para guardar los cambios:   
   ![Imagen de información general](./media/introduction-to-button-flows/manage-flow-3.png)   
2. Pulse **Run history** (Historial de ejecuciones) para ver los resultados de todas las ejecuciones de un flujo de botón determinado:    
   ![Imagen de información general](./media/introduction-to-button-flows/manage-flow-4.png)  
3. Si deshabilita un flujo, dejará de estar disponible en la pestaña **Buttons** (Botones):    
   ![Imagen de información general](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Pasos siguientes
* [Compartir flujos de botones en Microsoft Flow](share-buttons.md).
* Aprenda a usar [tokens de desencadenadores de botones](introduction-to-button-trigger-tokens.md) para enviar datos en tiempo real cuando se ejecuten los flujos de botón
* Instale la aplicación móvil de Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).

