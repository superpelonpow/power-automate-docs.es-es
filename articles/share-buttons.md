---
title: Compartir los botones con otros usuarios | Microsoft Docs
description: Comparta sus botones con otros usuarios para que puedan usarlos y ahorrar tiempo.
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
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3209748b03823add7622472665ce70b4cd581b1f
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74372754"
---
# <a name="share-button-flows-in-power-automate"></a>Uso compartido de flujos de botones en Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
En la aplicación móvil Power Automate, puede compartir [flujos de botones](introduction-to-button-flows.md) (botones) con otros usuarios o grupos de su organización. Cuando se comparte un botón, la persona o grupo con quien se haga puede ejecutarlo de la misma forma que sus propios botones. También puede [compartir un vínculo](share-buttons.md#re-share-a-button) a los botones que otra persona ha compartido con usted. Los botones se pueden [dejar de compartir](share-buttons.md#stop-sharing-a-button) en cualquier momento.

> Las capturas de pantalla usadas en este documento se han realizado desde un dispositivo Android. Si usas un iPhone, las imágenes pueden tener una apariencia diferente, pero la funcionalidad es la misma.
> 
> 

Siga [estos pasos](share-buttons.md#use-shared-buttons) para usar un botón que alguien ha compartido con usted.

## <a name="prerequisites"></a>Requisitos previos
Para compartir botones, necesita:

* Una cuenta con acceso a [Power Automate](https://flow.microsoft.com).
* Un flujo que compartir.
* Un dispositivo móvil con la aplicación móvil de Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).
* Un grupo o usuario en su organización con quien compartir el botón.

## <a name="share-a-button"></a>Uso compartido de un botón
Puede compartir un botón desde la pestaña **Botones** de la aplicación móvil Power Automate.

1. Pulse el icono pequeño que hay junto al botón que desea compartir.
   
    ![compartir botón](./media/share-buttons/share-button-flows-buttons-tab.png)
2. Pulse **Invitar a otros** en la página **Button users** (Usuarios del botón).
   
    ![compartir botón](./media/share-buttons/share-button-flows-button-users.png)
3. Busque y seleccione el grupo o la persona con quien le gustaría compartir el botón.
   
    ![compartir botón](./media/share-buttons/share-button-flows-invite-others-select.png)
4. Pulse **ENVIAR** en la página **Invitar a otros**.
   
    ![compartir botón](./media/share-buttons/share-button-flows-invite-others-send.png)
5. Pulse **LISTO** en la página que indica que la operación de compartir el botón se ha completado correctamente.
   
    ![compartir botón](./media/share-buttons/share-button-flows-invite-others-done.png)

## <a name="require-users-to-use-their-own-connections"></a>Requerir a los usuarios que utilicen sus propias conexiones
> [!NOTE]
> Al compartir un botón, puede permitir que las personas con quienes lo ha compartido el utilicen todas las conexiones que usa el botón. También puede exigirles que usen sus propias conexiones. Si permite que otros usuarios utilicen sus conexiones, no podrán acceder a las credenciales de su conexión ni utilizarlas en otro flujo.
> 
> 

Siga estos pasos para exigir a las personas con quienes ha compartido los botones que usen sus propias conexiones.

1. Seleccione **ADMINISTRAR CONEXIONES** en la pantalla que se muestra inmediatamente después de compartir un botón.
2. Seleccione **EDITAR** en el botón que desea administrar.
3. Seleccione **Proporcionado por el usuario** o su dirección de correo electrónico.
   
    La elección que realice determinará las conexiones que se deben utilizar en el botón compartido.
   
    ![compartir botón](./media/share-buttons/share-button-select-connection-provided-by-user.png)
   
    La opción que se elija se puede cambiar en cualquier momento. Para ello, seleccione la pestaña **Flujos** > el flujo que compartió > **Usuarios y conexiones** > la pestaña **CONEXIONES** > **EDITAR** en el botón que desea administrar.
   
    ![compartir botón](./media/share-buttons/share-button-flows-conn-provided-by-user.png)

## <a name="view-the-list-of-button-users"></a>Visualización de la lista de usuarios de los botones
Puede ver todos los grupos o usuarios con los que se comparte un botón siguiendo estos pasos en la pestaña **Botones**:

1. Pulse el icono pequeño que hay junto al botón en el que está interesado.
2. En la página **Usuarios botón**, consulte todos los grupos o usuarios con los que se ha compartido el botón.
   
    ![ver usuarios del botón](./media/share-buttons/share-button-flows-button-users-list.png)

## <a name="stop-sharing-a-button"></a>Dejar de compartir un botón
Para dejar de compartir un flujo de botones, siga estos pasos en la pestaña **Botones**:

1. Pulse el icono pequeño que hay junto al botón que desea dejar de compartir.
2. En la página **Usuarios botón**, pulse el usuario o grupo con el que desea dejar de compartir el botón.
   
    ![dejar de compartir un botón](./media/share-buttons/share-button-flows-remove-user-list.png)
3. Pulse **Quitar usuario** cuando se muestre la página del usuario.
   
    ![dejar de compartir un botón](./media/share-buttons/share-button-flows-remove-user.png)
4. Espere a que se complete la operación de eliminación. Observe que la lista **Button users** (Usuarios del botón) se actualiza, y el usuario o grupo que ha quitado ya no aparece.
   
    ![dejar de compartir un botón](./media/share-buttons/share-button-flows-remove-user-result.png)

## <a name="monitor-the-run-history"></a>Supervisión del historial de ejecución
Todo el historial de ejecución, incluidas las ejecuciones iniciadas por una persona con la que se ha compartido un botón, solo aparece en la pestaña **Actividad** de la aplicación móvil de Power Automate del creador del botón.

## <a name="use-shared-buttons"></a>Uso de botones compartidos
Antes de poder ejecutar un botón que alguien ha compartido con usted, debe agregarlo a su pestaña **Botones** de la página **Agregar botones**.

1. Pulse **Obtener más** (o el banner **Hay nuevos botones disponibles**, si aparece) en la pestaña **Botones**.
   
    ![nuevo botón compartido conmigo](./media/share-buttons/share-button-flows-banner.png)
2. Pulse el botón que desea usar.
   
    El botón pulsado se agrega inmediatamente a la pestaña **Botones** de la aplicación Power Automate. A continuación, puede usar el botón en la pestaña **Botones**, al igual que cualquier otro botón que aparezca.
   
    ![nuevo botón compartido conmigo](./media/share-buttons/share-button-flows-buttons-shared-with-me.png)

## <a name="re-share-a-button"></a>Volver a compartir un botón
Puede compartir un vínculo a un botón que se ha compartido con usted.

1. Seleccione **...**  junto al botón que desea compartir.
2. Seleccione **Compartir vínculo de botón**.
   
    ![volver a compartir vínculo de botón](./media/share-buttons/re-share-button.png)
3. Seleccione la aplicación que desea usar para compartir el botón y, después, siga los pasos necesarios para enviar el botón a la persona con quién desea compartirlo.

## <a name="stop-using-a-shared-button"></a>Dejar de usar un botón compartido
Si ya no desea usar un botón compartido con usted, quítelo de la pestaña **Botones** mediante estos pasos:

1. En la pestaña **Botones**, pulse **...**  junto al botón que ya no desea utilizar.
   
    ![quitar botón](./media/share-buttons/share-button-flows-added-shared-button.png)
2. Pulse **Quitar** en el menú que aparece.

Eso es todo. El botón dejará de aparecer en la pestaña **Botones** de la aplicación Power Automate.

> [!NOTE]
> Después de quitar un botón compartido, puede agregarlo de nuevo seleccionando **Obtener más** en la pestaña **Botones**.
> 
> 

