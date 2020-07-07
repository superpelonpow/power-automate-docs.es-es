---
title: Crear de un flujo de recordatorio para elementos de SharePoint | Microsoft Docs
description: Cree flujos que le recuerden las fechas de vencimiento de los elementos de SharePoint.
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
ms.date: 04/06/2020
ms.author: deonhe
ms.openlocfilehash: b5930ca6fa663d92497ec48b3cc6220d8c891d44
ms.sourcegitcommit: 71f9b72d551887324c92b122dadd1b4dd584bc4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "3299285"
---
# <a name="sharepoint-remind-me"></a>Recuérdamelo en SharePoint


Las listas y bibliotecas de SharePoint le permitían definir columnas de metadatos personalizadas para realizar el seguimiento de fechas. Gracias a la integración de Power Automate con SharePoint, puede crear fácilmente flujos de recordatorio según las columnas DateTime de SharePoint. Con los flujos de recordatorio, recibirá una alerta de correo electrónico personal un número determinado de días antes de una fecha sobre cualquier documento o elemento de SharePoint.

## <a name="prerequisites"></a>Requisitos previos
- Acceso a Microsoft SharePoint Online.
- Una lista o una biblioteca de SharePoint con una columna DateTime.
- Obtenga acceso a Power Automate.

## <a name="create-a-reminder-flow"></a>Creación de un flujo de recordatorio

 1. Cree una [lista de SharePoint](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) con al menos una columna DateTime en la vista actual. 
 1. Seleccione **Automatizar** > **Establecer un recordatorio** > **Date deactivated** (Fecha de desactivación) (esta es la columna con el valor de DateTime del recordatorio).

     ![Seleccionar el flujo de recordatorio](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. De forma opcional, es posible que tenga que iniciar sesión en los servicios que esta plantilla de Power Automate usa.
     
1. Seleccione **Continuar**.

1. Rellene el campo **Nombre de flujo** y, en la entrada de la columna DateTime de la tarjeta **Establecer un recordatorio**, indique con cuántos días de antelación quiere recibir la alerta de recordatorio.

    ![Establecer los detalles del flujo de recordatorio](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. Seleccione **Crear** en la tarjeta **Establecer un recordatorio**.

1. Recibirá el mensaje siguiente, que indica que se ha creado el flujo:

    ![Flujo de recordatorio creado](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Confirmación de los recordatorios recibidos

Recibirá un recordatorio por correo electrónico, según la entrada **Recordármelo con varios días de antelación** que hiciera en la tarjeta **Establecer un recordatorio** del flujo creado anteriormente. 

## <a name="edit-your-flow"></a>Edición del flujo

El flujo de recordatorio es como cualquier otro flujo, por lo que puede acceder a él y editarlo en [Power Automate](https://flow.microsoft.com).

## <a name="learn-more"></a>Más información

- Empezar a utilizar [Power Automate](https://flow.microsoft.com).
- Establecer un [flujo de recordatorio](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) en SharePoint.


