---
title: Información sobre cómo crear flujos de interfaz de usuario para sitios web | Microsoft Docs
description: Obtenga información sobre cómo automatizar aplicaciones web con flujos de interfaz de usuario.
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
ms.date: 02/28/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: fb0b3b2dcd615130764d7f4c206e04e191bb1eca
ms.sourcegitcommit: bba5bd4ae3879b6bf1521d8ed636374fe09709e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "3298845"
---
# <a name="create-and-test-your-web-ui-flows"></a>Creación y prueba de los flujos de la interfaz de usuario web

Siga estos pasos para crear un flujo de interfaz de usuario web simple.

## <a name="create-a-web-ui-flow"></a>Creación de un flujo de interfaz de usuario web

1. Abra [Microsoft Edge (versión 80 o posterior) ](https://www.microsoft.com/edge) o Google Chrome, y luego vaya a [Power Automate](https://flow.microsoft.com/).

1. Inicie sesión con su cuenta profesional o educativa si es necesario.

1. Seleccione **Mis flujos** > **Flujos de interfaz de usuario** > **Nuevo**.

   ![Creación de un flujo de interfaz de usuario](../media/create-windows-ui-flow/create-new.png "Creación de un flujo de interfaz de usuario")

1. Seleccione **Aplicación web** > **Siguiente**.
    
   ![Seleccione Aplicación web](../media/create-web-ui-flow/select-web-app.png "Seleccione Aplicación web")

1. Escriba un nombre para el flujo de interfaz de usuario en el campo **Nombre del flujo**.

1. Escriba la dirección URL del sitio web que quiere automatizar en el campo **URL base** y, luego, seleccione **Launch recorder** (Iniciar grabadora).

   ![Asigne un nombre y una dirección URL](../media/create-web-ui-flow/give-a-name.png "Asigne un nombre y una dirección URL") 

   Se inicia el IDE de Selenium.

   >[!TIP] 
   >Sugerencia: Puede grabar acciones en varios sitios web HTTP o HTTPS dentro de la misma pestaña.  

1. En el IDE de Selenium, seleccione el botón **REC** rojo que está en el lado superior derecho de la pantalla para iniciar la grabadora.

   Se abre la dirección URL que eligió en el paso anterior.

   ![Seleccione REC](../media/create-web-ui-flow/select-rec.png "Seleccione REC")

1.  Haga las acciones que quiere grabar en el sitio web. 
    
    >[!TIP]
    >En la parte inferior derecha, puede ver el estado de la grabación.

    ![Estado de la grabación](../media/create-web-ui-flow/recording-status.png "Estado de la grabación")

1.  Cuando termine de grabar, seleccione el botón **Detener** rojo que está en la esquina superior derecha del IDE de Selenium.

    ![Botón Detener](../media/create-web-ui-flow/stop-button.png "Botón Detener" )

1. Seleccione el botón **Run current test** (Ejecutar la prueba actual) en la parte superior izquierda de la pantalla para ver el flujo de interfaz de usuario que acaba de crear.

    ![Ejecute la prueba actual](../media/create-web-ui-flow/run-test.png "Ejecute la prueba actual")

   >[!TIP]
   >Puede establecer el tiempo de espera entre los pasos para ralentizar la reproducción local de las pruebas. Esta configuración es solo para pruebas y no tiene ningún impacto cuando se implementa el flujo de interfaz de usuario.  
  
1. Seleccione el botón **Guardar proyecto** en la esquina superior derecha del IDE de Selenium. De este modo, se cierra y luego se carga el proyecto.

Ahora que creó un flujo de interfaz de usuario web, úselo en los otros flujos.

## <a name="limitations-and-known-issues-for-web-ui-flows"></a>Limitaciones y problemas conocidos de los flujos de interfaz de usuario web

>[!WARNING]
>**Las contraseñas del IDE de Selenium se almacenan en texto sin formato**.  


**Los flujos de interfaz de usuario ya no graban ni reproducen las aplicaciones Windows después de instalar una versión nueva**.

Confirme que está usando la [versión más reciente](https://go.microsoft.com/fwlink/?linkid=2102613&clcid=0x409).

**Perfil de usuario temporal para la reproducción**

Las grabaciones del IDE de Selenium se realizan con el perfil del usuario actual, pero la reproducción se hace con un perfil de usuario temporal. Esto significa que los sitios web que necesitan autenticación no pueden solicitar credenciales durante una sesión de grabación, pero se necesitarán los pasos de autenticación durante la reproducción. 

Para solucionarlo, el usuario debe editar manualmente el script para insertar los comandos necesarios para el proceso de inicio de sesión.

**Otras limitaciones**

-   Grabar aplicaciones de escritorio durante una sesión de grabación web. Si necesita automatizar aplicaciones web y de escritorio, puede crear flujos de interfaz de usuario independientes para cada tipo y, luego, combinarlos en un flujo.

-   Multi-Factor Authentication (MFA) no es compatible. Use un inquilino que no requiera MFA.

-   No se admiten estos comandos del IDE de Selenium: Run, AnswerOnNextPrompt, ChooseCancelOnNextConfirmation, ChooseCancelOnNextPrompt, ChooseOkOnNextConfirmation, Debugger, ClickAt, DoubleClickAt, Echo, MouseOut, MouseUpAt ni MouseDownAt.

-   No se admite el clic con el botón derecho. 

-   Se genera una entrada de flujo de interfaz de usuario web adicional cuando se usan comandos Foreach. Para evitar este problema, especifique cualquier valor en los campos adicionales. No afecta la reproducción.

-   Si el archivo .side contiene varios proyectos de prueba, solo se ejecuta el primero que se creó. 

     >[!TIP]
     >Tenga en cuenta que el IDE de Selenium ordena las pruebas por nombre y no por fecha de creación, por lo que es posible que la primera prueba creada no sea la primera de la lista.

-   Es posible que la reproducción directa en el IDE de Selenium no se comporte según lo previsto. Sin embargo, la reproducción en tiempo de ejecución a través de la infraestructura de flujo de interfaz de usuario se comporta correctamente.

## <a name="next-steps"></a>Pasos siguientes

- Aprenda a ejecutar [flujos de interfaz de usuario](run-ui-flow.md).

- Si quiere hacer más cosas con los flujos de interfaz de usuario, también puede probar los flujos de interfaz de usuario con parámetros de [entrada y salida](inputs-outputs-web.md).

 
