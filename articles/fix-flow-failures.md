---
title: Solución de problemas en un flujo | Microsoft Docs
description: Resolución de algunos de los motivos más habituales por los que los flujos producen un error
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/01/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: faa0b50a9a525d5abaa818d05be8a97e6ad6663b
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297327"
---
# <a name="troubleshooting-a-flow"></a>Solución de problemas en un flujo


## <a name="repair-tips-in-email"></a>Sugerencias de reparación en el correo electrónico

Las sugerencias de reparación se envían a los propietarios de los flujos por correo electrónico cada vez que se produce un error en un flujo. Estos mensajes de correo electrónico de sugerencias de reparación contienen comentarios específicos y accionables sobre determinados errores. Por ejemplo, un error común es configurar un flujo que intenta obtener el administrador de una persona en Office 365, pero no hay ningún administrador configurado en Azure Active Directory (Azure AD). Si esta u otras diversas condiciones hacen que el flujo genere un error, recibirá un correo electrónico de sugerencias de reparación como este:

![Sugerencias de reparación](media/fix-flow-failures/repair-tips-email.png)

El correo electrónico de sugerencias de reparación contiene las siguientes secciones:

Nombre|Descripción
---|---
Hora|Muestra la hora en que se produjo el error del flujo por primera vez.
¿Qué ha ocurrido?|Proporciona una descripción del problema que causó el error en el flujo.
¿Cómo puedo corregirlo?|Proporciona sugerencias para resolver el problema que provoca el error en el flujo.
Sugerencias para la solución de problemas|Proporciona detalles, como el número de veces que el flujo generó un error y un vínculo para volver a intentar el flujo con los mismos datos de entrada.

Para corregir los errores notificados, seleccione **Corregir mi flujo** y siga los pasos del correo electrónico de sugerencias de reparación.

Los correos electrónicos de sugerencias de reparación son opcionales. Si no quiere recibirlos, solo tiene que desactivarlos en el menú de propiedades del flujo específico.

Si el flujo genera un error, también puede solucionarlo directamente en Power Automate.  Estos son algunos escenarios de error comunes y sugerencias para corregirlos.

## <a name="identify-the-error"></a>Identificación del error
Antes de poder corregir un flujo, debe identificar el motivo del error. Haga clic o pulse en el icono de notificaciones de la parte superior del portal web (o abra la pestaña **Actividad** en la aplicación móvil) y, a continuación, haga clic o pulse en el flujo en la lista que aparece.

![Notificaciones](./media/fix-flow-failures/notifications-toolbar.png)

Los detalles del flujo aparecen y, al menos en un paso se muestra un icono rojo con el signo de exclamación. Abra ese paso y revise el mensaje de error.

![Mensaje de error](./media/fix-flow-failures/flow-run-failure.png)


## <a name="authentication-failures"></a>Errores de autenticación
En muchos casos, los flujos generan errores debido a un error de autenticación. Si tiene este tipo de error, el mensaje de error contiene el texto **No autorizado** o aparece un código de error **401** o **403**. Normalmente, se puede corregir un error de autenticación mediante la actualización de la conexión:

1. En la parte superior del portal web, haga clic o pulse en el icono de engranaje para abrir el menú **Configuración** y, luego, haga clic o pulse en **Conexiones**.
2. Desplácese hasta la conexión en la que aparecía el mensaje de error de **No autorizado**.
3. Junto a la conexión, haga clic o pulse en el vínculo **Repetir contraseña** del mensaje sobre la conexión que no se autentica.
4. Compruebe sus credenciales mediante las instrucciones que aparecen, vuelva al error de ejecución del flujo y, a continuación, haga clic o pulse en **Volver a enviar**.
   
    Ahora el flujo debería ejecutarse según lo previsto.

## <a name="action-configuration"></a>Configuración de acciones
Los flujos también pueden producir un error si una opción de una acción del flujo no funciona según lo previsto. En este caso, el mensaje de error contiene el texto **Solicitud incorrecta** o **No se encuentra**, o aparece un código de error **400** o **404**.

El mensaje de error debe especificar cómo corregir el error. Debe hacer clic o pulsar en el botón **Editar** y, a continuación, corregir el problema dentro de la definición de flujo. Guarde el flujo actualizado y, a continuación, haga clic o pulse en **Volver a enviar** para probar la ejecución de nuevo con la configuración actualizada.

## <a name="other-failures"></a>Otros errores
Si aparece el código de error **500** o **502**, el error es temporal o transitorio. Haga clic o pulse en **Volver a enviar** para probar el flujo de nuevo.

## <a name="getting-help-from-support-or-the-community"></a>Obtención de ayuda del servicio de soporte técnico o de la comunidad

Cuando necesite ayuda, puede usar nuestras opciones de **Autoayuda** o **Solicitar ayuda** a otros usuarios.

### <a name="self-help"></a>Autoayuda 

1. Vaya al [sitio de soporte técnico](https://flow.microsoft.com/support/).
1. Vaya a la categoría **Autoayuda** y seleccione una de las opciones de autoayuda.

    ![Sección Solicitar ayuda. Contacto con soporte técnico.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Solicitar ayuda a otros

1. Vaya al [sitio de soporte técnico](https://flow.microsoft.com/support/).
1. Seleccione **Contacto con soporte técnico** en la sección **Solicitar ayuda**.
    
    ![Sección Solicitar ayuda. Contacto con soporte técnico.](media/fix-flow-failures/ask-for-help.png)

1. Rellene los campos **Tipo de problema**, **Categoría** y **Díganos en qué necesita que le ayudemos** y, luego, seleccione **Ver soluciones**. 

1. Observe que la sección **Soluciones** se muestra después de seleccionar **Ver soluciones**. Esta sección contiene una lista de los resultados que puede usar para ayudar a resolver el problema que tiene. 

    ![Detalles del asistente integrado](media/fix-flow-failures/integrated-helper-details.png)

Si necesita ayuda con un problema, puede encontrarla en nuestra [comunidad](https://go.microsoft.com/fwlink/?LinkID=787467) y en Microsoft. 

