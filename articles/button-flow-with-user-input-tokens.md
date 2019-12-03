---
title: Información acerca de cómo automatizar tareas repetitivas con flujos de botones que necesitan entradas del usuario | Microsoft Docs
description: Power Automate simplifica la automatización de tareas repetitivas. Puede incluso que los flujos necesiten entradas del usuario al ejecutar una tarea repetitiva.
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
ms.date: 02/15/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: fe7e8f685d319e11994adaf1926d2d0ab03706d7
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74358586"
---
# <a name="introducing-button-flows-with-user-input"></a>Presentación de los flujos de botones con entradas del usuario
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Cree un flujo de botón para ejecutar tareas rutinarias simplemente con pulsar un botón. Para personalizar un flujo, permita al usuario proporcionar detalles específicos que se usarán al ejecutarlo. Este tema le guía a través de la creación de un flujo de botón que usa las entradas de los usuarios y, después, la ejecución del flujo de botón, y resalta cómo proporcionar la entrada del usuario.

Puede crear un flujo de botón en el sitio web de Power Automate o en la aplicación móvil para Power Automate. En este tema, utilizará el sitio web.

### <a name="prerequisites"></a>Requisitos previos
* Una cuenta en el sitio web de Power Automate.

## <a name="open-the-template"></a>Apertura de la plantilla
1. Inicie sesión en el [sitio web de Power Automate](https://flow.microsoft.com), escriba **Visual Studio** en el cuadro de búsqueda y haga clic o pulse en el icono de búsqueda para buscar todas las plantillas que estén relacionadas con Visual Studio:
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. Seleccione la plantilla **Open a Priority 2 Bug in Visual Studio**:
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. Seleccione el botón **Usar esta plantilla**:
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    Esta plantilla usa Visual Studio Team Services (VSTS) y los servicios de notificación push. Si no tiene conexión con estos servicios, es preciso que inicie sesión en ellos. El botón **Iniciar sesión** solo aparecerá si se hace falta iniciar sesión en un servicio.
4. Después de iniciar sesión en todos los servicios requeridos, haga clic o pulse el botón **Continuar**:
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. (opcional) Para cambiar el nombre del flujo escríbalo en el cuadro de la parte superior del portal:
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>Personalizar la entrada de usuario
1. En la tarjeta del desencadenador, seleccione **Editar**:
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. Seleccione el icono **+** para expandir la página, con el fin de que pueda agregar campos de entrada personalizados:
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. Escriba la información de **Introducir entrada** e **Introducir** de cada uno de los campos personalizados que desea que estén disponibles cuando se ejecute el flujo.  
   
    En este ejemplo, creará dos campos de entrada personalizados (**Pasos para la reproducción de error** y **Gravedad de error**) para que cualquier persona que use este flujo pueda escribir los pasos necesarios para reproducir el error y evaluar la gravedad del error:  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>Personalización del error
1. Pulse la barra de título de la tarjeta **Create a new work item** (Crear nuevo elemento de trabajo):
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. Elija las opciones más apropiadas para su entorno de VSTS y seleccione **Editar**:
   
    Por ejemplo, conectarse a myinstance.visualstudio.com escribiendo **myinstance**.
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. Seleccione **Mostrar opciones avanzadas** para que aparezcan los restantes campos de esta tarjeta:
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. Coloque el cursor delante del símbolo (token) **Bug title** y escriba "Gravedad:" en el campo de texto **Title** (Título).
5. Con el cursor en el campo de texto del título, seleccione el símbolo (token) **Bug severity** (Gravedad del error) y escriba "--".  
6. En el campo de texto **Description** (Descripción), coloque el cursor inmediatamente después del símbolo (token) **Bug description** (Descripción del error) y presione Entrar para iniciar una nueva línea.
7. Coloque el cursor en la línea nueva y, a continuación, seleccione el símbolo (token) **Pasos para la reproducción de error**:
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>Personalización de la notificación push
1. Pulse la barra de título de la tarjeta **Send a push notification** (Enviar notificación de inserción) para expandirla.
2. En la lista de símbolos (tokens) de contenido dinámico, seleccione **Ver más**y, después, agregue el símbolo (token) **URL** en el campo de texto **Link** (Vínculo).
3. En el campo de texto **Link label** (Etiqueta de vínculo), agregue el símbolo (token) **Id**:
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. Pulse **Crear flujo** en el menú para crear el flujo: ![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>Ejecución del flujo
En este tutorial, usará la aplicación móvil para Power Automate para ejecutar el flujo de botón que acaba de crear. Proporcionará toda la entrada de usuario necesaria para crear un error con un título, una descripción, los pasos para la reproducción y un nivel de gravedad.  

1. En la aplicación móvil para Power Automate, pulse en la pestaña **Botones** y, después, pulse el botón **Create bug report with steps** (Crear informe de errores con pasos).
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. Escriba el título del error que está notificando y pulse **Next** (Siguiente). Por ejemplo:
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. Escriba la descripción del error que está notificando y pulse **Next** (Siguiente). Por ejemplo:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. Escriba los pasos que se deben dar para reproducir el error que está notificando y pulse **Next** (Siguiente). Por ejemplo:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. Escriba la gravedad del error que está notificando y pulse **Done** (Listo):  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    El flujo se ejecuta.
6. (opcional) Pulse la pestaña **Activity** (Actividad) para mostrar los resultados.
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. (opcional) Para mostrar los resultados detallados de la ejecución del flujo, pulse el paso **Create a new work item** (Crear un nuevo elemento de trabajo).
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)


## <a name="use-different-input-types"></a>Uso de diferentes tipos de entrada

Los flujos de botón también pueden aceptar tipos de datos enriquecidos. Esta es la lista de tipos de entrada de datos que los flujos de botón aceptan: 

- Texto
- Listas desplegables (como botones de radio)
- Dirección de correo electrónico
- Archivo (por ejemplo, una fotografía del teléfono)
- Casilla Sí o No
- Número
- Fecha (con un selector de calendario)

Para usar estos tipos de entrada, agregue el desencadenador **Desencadenar un flujo manualmente** y, luego, cualquiera de estos tipos al flujo:

![Opciones de entrada](media/button-flow-with-user-input-tokens/input-options.png)

Además, puede que le interese designar algunas entradas como necesarias y otras como opcionales. Use el menú de acción (... en el lado derecho) en cada campo de entrada. Hay un límite de cinco entradas por botón.

![Selección de tokens opcionales](media/button-flow-with-user-input-tokens/required-optional.png)

## <a name="next-steps"></a>Pasos siguientes
* [Compartir flujos de botones](share-buttons.md)
* [Más información sobre los flujos de botones](introduction-to-button-flows.md)  
* [Más información acerca de los flujos de botones con tokens de desencadenador](introduction-to-button-trigger-tokens.md)  

