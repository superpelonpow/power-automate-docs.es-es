---
title: Creación de un flujo desde un teléfono | Microsoft Docs
description: Cree un flujo desde una plantilla que, por ejemplo, envía una notificación push cuando se recibe correo desde la dirección que especifique
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 393ae5f6a86363610c26aea78a04748f34dc4f97
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193620"
---
# <a name="create-a-flow-from-your-phone-by-using-power-automate"></a>Creación de un flujo desde un teléfono mediante Power Automate

Cree un flujo desde un teléfono mediante una plantilla, que se puede encontrar de cualquiera de las tres formas siguientes: búsqueda en una lista de servicios, examen de categorías o especificación de palabras clave. Siga los pasos de este tema para crear un flujo que envíe una notificación push a su teléfono cuando reciba un correo electrónico de un administrador.

Si nunca ha usado Power Automate, [aquí puede obtener una visión general](getting-started.md).

## <a name="prerequisites"></a>Requisitos previos
* Una [cuenta para Power Automate](sign-up-sign-in.md).
* La aplicación móvil de Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows) en un [dispositivo compatible](getting-started.md#use-the-mobile-app). Los elementos gráficos de este tema reflejan la versión de iPhone de la aplicación, pero la interfaz en un dispositivo Android o Windows Phone es similar.
* Para utilizar la plantilla que se muestra en este tema, también necesitará:
  
  * Credenciales de Office 365.
  * Notificaciones push habilitadas en el teléfono.

## <a name="find-a-template"></a>Busqueda de una plantilla
1. Abra la aplicación móvil y pulse **Examinar** en la parte inferior de la pantalla.
   
    ![Icono Examinar](./media/mobile-create-flow/browse-icon.png)
   
    Puede utilizar cualquiera de estas acciones para buscar la plantilla:
   
   * Especifique una palabra clave en el cuadro de búsqueda de la parte superior de la pantalla.
   * Pulse cualquiera de las opciones de la lista de servicios.
   * Desplácese hacia abajo para mostrar varias categorías y, luego, pulse una plantilla de cualquiera de las categorías.
     
       ![Pestaña Examinar](./media/mobile-create-flow/browse-tab.png)
     
     A efectos de este tutorial, abrirá la plantilla que envía una notificación push cuando reciba un correo electrónico de un administrador.
2. En la lista de servicios, pulse **See all** (Ver todos).
   
    ![Mostrar lista de servicios](./media/mobile-create-flow/list-services.png)
3. Pulse el icono de **notificación push**.
   
    ![Notificaciones push](./media/mobile-create-flow/push-notifications.png)
4. En la barra de búsqueda, escriba **correo electrónico** y pulse la plantilla para enviar una notificación push cuando reciba un mensaje de un administrador.
   
    ![Elegir plantilla](./media/mobile-create-flow/choose-template.png)
5. En la pantalla que proporciona detalles acerca de la plantilla que ha seleccionado, pulse **Use this template** (Usar esta plantilla).
   
    ![Confirmar plantilla](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>Finalización del flujo
1. Si se le solicita, pulse **Sign in** (Iniciar sesión) y especifique las credenciales de Office 365 Outlook, Usuarios de Office 365, o ambos.
   
    ![Iniciar sesión en Office 365](./media/mobile-create-flow/office-signin.png)
   
    Al crear otros flujos se pueden usar las mismas conexiones.
2. En la esquina superior derecha, pulse **Next** (Siguiente).
   
    ![Pulsar Next (Siguiente)](./media/mobile-create-flow/next.png)
   
    La pantalla siguiente muestra el efecto desencadenante y todas las acciones resultantes.
   
    ![Desencadenar evento y acciones](./media/mobile-create-flow/flow-structure.png)
   
    Para esta plantilla, el correo nuevo desencadena el flujo, que recupera la información (incluida la dirección de un administrador) y le envía una notificación push cuando reciba correo de dicha dirección. Algunas plantillas requieren cierta personalización para funcionar correctamente, pero esta no.
3. (opcional) Cerca de la parte superior de la pantalla, escriba otro nombre para el flujo.
   
    ![Cambiar nombre de flujo](./media/mobile-create-flow/rename-flow.png)
4. En la esquina superior derecha, pulse **Create** (Crear).
   
    ![Crear flujo](./media/mobile-create-flow/create-flow.png)
   
    Se crea el flujo, que comprobará si ha llegado correo del administrador hasta que se pause o se elimine dicho flujo.

## <a name="next-steps"></a>Pasos siguientes
* [Monitor activity in Microsoft Flow from your phone](mobile-monitor-activity.md) (Supervisión de la actividad en Microsoft Flow desde un teléfono).
* [Manage flows in Microsoft Flow from your phone](mobile-manage-flows.md) (Administración de flujos en Microsoft Flow desde un teléfono).

