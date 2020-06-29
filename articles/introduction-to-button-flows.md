---
title: Información sobre la automatización y ejecución de tareas repetitivas con flujos instantáneos | Microsoft Docs
description: Introducción a los flujos instantáneos.
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
ms.date: 03/17/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3607d41dbe78b591aed97f366dd783db4a0725fb
ms.sourcegitcommit: 549224cf13fc761f473c880e8d0d8f2741cc7b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "3435025"
---
# <a name="introducing-instant-flows"></a>Introducción a los flujos instantáneos

## <a name="what-are-instant-flows"></a>¿Qué son los flujos instantáneos?
Hay muchas tareas repetitivas que todos deseamos poder ejecutar con solo tocar un botón. Por ejemplo, es posible que deba enviar rápidamente un correo electrónico a su equipo para recordarles que se unan a la sincronización diaria del equipo, o puede que desee comenzar una nueva compilación en Visual Studio Online de su base de código después de haber sido notificado de que no hay más registros planificados para el día. Los flujos instantáneos permiten realizar estas y muchas otras tareas con tan solo pulsar un botón del dispositivo móvil.

**Nota** Los flujos instantáneos se pueden crear desde un dispositivo móvil o desde el portal de Power Automate.  
  ![Imagen de información general](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>¿Por qué crear botones?
Cree botones para poder ejecutar fácilmente tareas repetitivas desde cualquier lugar y en cualquier momento a través de un dispositivo móvil. Los botones de ejecución ahorran tiempo y, como las tareas que realizan están automatizadas, habrá menos errores que si se realizaran manualmente.  

## <a name="create-a-button"></a>Creación de un botón
### <a name="prerequisites"></a>Requisitos previos
* Acceda a Power Automate](https://flow.microsoft.com).
* Una cuenta con permisos para utilizar los conectores para crear el botón. Por ejemplo, necesitará una cuenta de Dropbox para crear un botón que acceda a Dropbox.

### <a name="from-the-portal"></a>Desde el portal
En este tutorial, vamos a crear un botón que inicia una compilación de Visual Studio Online (VSO) y envía notificaciones que le permiten saber en qué momento se inicia la compilación:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com).
1. Seleccione **Crear** en el lado izquierdo de la pantalla.
1. Seleccione **Flujo instantáneo**.
1. Dele un nombre a su flujo en **Nombre de flujo** > **Activar manualmente un flujo** > **Crear**. 
 
2. Seleccione la plantilla **Desencadenar una compilación nueva en VSO** en la lista de plantillas.  
   ![Imagen que muestra las plantillas](./media/introduction-to-button-flows/create-button-2.png)  
3. Seleccione el botón **Usar esta plantilla** de la página **Desencadenar una compilación nueva en VSO**.   
   ![Imagen que muestra la plantilla que se va a usar](./media/introduction-to-button-flows/create-button-3.png)  
4. Si no ha iniciado sesión, se le pedirá que lo haga en este momento:  
   ![Imagen que muestra las opciones de inicio de sesión](./media/introduction-to-button-flows/create-button-4.png)  
5. Después de iniciar sesión en Flow, se le solicitará que inicie sesión en los conectores que se usan en la plantilla que ha seleccionado. En este ejemplo, en el paso 2 seleccionamos la plantilla **Desencadenar una compilación nueva en VSO**, por lo que tenemos que iniciar sesión en VSO (y en cualquier otro conector con el que trabaje), en caso de que no haya iniciado sesión:  
   ![Imagen que muestra el botón de inicio de sesión](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Seleccione el botón **Aceptar** botón si está de acuerdo en autorizar a Power Automate a acceder a su cuenta de VSO.  
   ![Imagen que muestra las opciones para autorizar el acceso a su cuenta de Visual Studio](./media/introduction-to-button-flows/create-button-5.png)   
   **Nota** Todos los conectores se deben autorizar de forma similar. El diseñador que aparecerá será similar al siguiente cuando esté listo para avanzar al paso siguiente. Seleccione el botón **Continuar** para avanzar:  
   ![Botón Continuar](./media/introduction-to-button-flows/create-button-6.png)   
7. Ya está preparado para configurar las propiedades de la compilación que desea iniciar:    
   ![Pantalla de propiedades](./media/introduction-to-button-flows/create-button-7.png)  
8. Seleccione o escriba los datos pertinentes en **Nombre de cuenta**, **Nombre de proyecto**, **Id. de definición de compilación**, **Rama de origen** y, opcionalmente, **Parámetros**, en la tarjeta **Poner en cola una compilación nueva**:    
   ![Pantalla de nueva compilación](./media/introduction-to-button-flows/create-button-8.png)  
9. A continuación, configure las propiedades de la notificación push en la tarjeta **Enviar una notificación push**. De manera predeterminada, esta notificación push está configurada para enviar un vínculo HTML a una página web que muestre el estado de la compilación:  
   ![Pantalla de notificación push](./media/introduction-to-button-flows/create-button-9.png)  
10. Seleccione el botón **Crear flujo** para guardar el flujo instantáneo: ![Crear botón de flujo](./media/introduction-to-button-flows/create-button-10.png)  
11. En poco tiempo verá este mensaje de operación correcta:  
    ![Mensaje de éxito](./media/introduction-to-button-flows/create-button-11.png)  

Enhorabuena, ha creado un flujo instantáneo. Ahora puede ejecutar este flujo instantáneo en cualquier momento y lugar desde la pestaña **Botones** de la aplicación Flow. Solo tiene que presionar el "botón" y se ejecutará. La aplicación móvil Power Automate está disponible para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="from-your-mobile-device"></a>Desde un dispositivo móvil

>[!NOTE]
>En este tutorial se muestran las pantallas de un dispositivo Android, pero las de un dispositivo iOS son similares.

En la aplicación:

1. Seleccione la pestaña **Examinar** y desplácese hasta la categoría **Botón**.  
   ![Pantalla de aterrizaje](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. Seleccione el vínculo **Ver todos**. Se muestran todas las plantillas de botón listas para usar.     
   ![Vínculo Ver todo](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. Seleccione la plantilla **Enviar un correo electrónico para recordar el equipo que se una a una reunión**    
   ![Imagen de la opción para enviar un correo electrónico para recordar el equipo que se una a una reunión](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Seleccione el vínculo **USAR ESTA PLANTILLA** en la parte inferior de la página.    
   ![Imagen de USAR ESTA PLANTILLA](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. Será preciso que inicie sesión en todos los servicios que usa esta plantilla:    
   ![Imagen de inicio de sesión en servicios de actualización](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Seleccione el vínculo **Siguiente** una vez que haya iniciado sesión en todos los servicios.      
   ![Vínculo Siguiente](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. Seleccionar el vínculo **Crear**. Aquí también puede revisar el flujo y realizar los cambios necesarios para personalizar el correo electrónico, por ejemplo.        
   ![Crear vínculo](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Transcurridos unos segundos, se crea el flujo instantáneo. Seleccione **VER MI FLUJO**:   
   ![Imagen de VER MI FLUJO](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. Vea todos los flujos en la pestaña **Mis flujos**  
   ![Imagen de Ver todos los flujos](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

Enhorabuena, ha creado un flujo instantáneo. Ahora puede ejecutar este flujo instantáneo en cualquier momento y lugar desde la pestaña **Botones** de la aplicación Flow. Solo tiene que presionar el "botón" y se ejecutará. La aplicación Flow está disponible actualmente en dispositivos móviles con iOS y Android.  

![Imagen de nuevo flujo instantáneo](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-an-instant-flow"></a>Desencadenar un flujo instantáneo
Ahora que ha creado un flujo instantáneo, ha llegado el momento de ejecutarlo. Dado que los flujos instantáneos solo se pueden ejecutar desde la aplicación Flow, asegúrese de haberla instalado en el dispositivo móvil Android o iOS.  

1. Ahora, inicie la aplicación Flow, pulse la pestaña **Botones** que se encuentra en la parte inferior de la página y pulse el *botón* que representa el flujo instantáneo que quiere desencadenar:  
   ![Desencadenar el flujo](./media/introduction-to-button-flows/trigger-button-1.png)   
2. Vea el progreso mientras se ejecuta el flujo:  
   ![Imagen del flujo de ejecución](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Por último, se actualiza la página, lo que indica que se ha completado el flujo instantáneo:  
   ![Imagen de flujo finalizado](./media/introduction-to-button-flows/trigger-button-3.png)   

Esta es toda la información sobre la ejecución de flujos. 

Ahora debe recibir la notificación push que indica que se ha enviado el correo electrónico.  

## <a name="monitor-your-instant-flow-runs"></a>Supervisión de las ejecuciones de flujo instantáneo
Los flujos instantáneos se pueden supervisar desde la pestaña **Actividad** de la aplicación Flow:   
![Imagen de la pestaña actividad](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

>[SUGERENCIA] Pulse cualquier actividad para aumentar el detalle de los resultados de la ejecución con el fin de obtener información sobre la ejecución.  

![Imagen de detalles de la actividad](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-instant-flows"></a>Administración de flujos instantáneos
Tiene control total de los flujos instantáneos, por lo que puede habilitar o deshabilitar, editar o eliminar un botón en cualquier momento y lugar. En la aplicación móvil o el portal de Flow, seleccione **Mis flujos** para empezar a administrar los flujos.    

En la pestaña **Mis flujos** de la aplicación Flow:

1. Seleccione el flujo que desea administrar:    
   ![Imagen de todos los flujos](./media/introduction-to-button-flows/trigger-button-4.png)   
2. Puede pulsar cualquiera de estas opciones, en función de lo que le gustaría realizar:    
   ![Opciones para administrar flujos](./media/introduction-to-button-flows/manage-flow-1.png)  

   Pulse **Eliminar flujo** para eliminar un flujo.  

      >[!WARNING]
      >Cuando se elimina un flujo se elimina todo el historial de ejecución.

      ![Imagen de advertencia de eliminación de flujo](./media/introduction-to-button-flows/manage-flow-2.png)   

   Pulse **Actualizar** cuando termine de editar un flujo instantáneo para guardar los cambios:   
   ![Imagen de actualización de flujo](./media/introduction-to-button-flows/manage-flow-3.png)   

   Pulse **Historial de ejecución** para ver los resultados de todas las ejecuciones de un flujo instantáneo determinado:    
   ![Ver historial de ejecución](./media/introduction-to-button-flows/manage-flow-4.png)  

   Si deshabilita un flujo, dejará de estar disponible en la pestaña **Botones**:    
   ![Los flujos deshabilitados no se encuentran en la pestaña botones](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Pasos siguientes
* [Uso compartido de flujos instantáneos](share-buttons.md).
* Aprenda a usar [tokens de desencadenadores de botones](introduction-to-button-trigger-tokens.md) para enviar datos en tiempo real cuando se ejecuten los flujos instantáneos.
* Instale la aplicación móvil de Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).

