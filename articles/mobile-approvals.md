---
title: Aprobación de solicitudes en dispositivos móviles | Microsoft Docs
description: Use cualquier dispositivo móvil para aprobar las solicitudes creadas en Power Automate.
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
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 513200d18ac2a845cd63a6d269513f3bcb45118c
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193988"
---
# <a name="approve-requests-on-your-mobile-device-by-using-power-automate"></a>Aprobación de solicitudes en dispositivos móviles mediante Power Automate

Si un flujo le identifica como aprobador y ha instalado la aplicación móvil de Power Automate, recibirá una notificación push cada vez que se solicite que lo apruebe.

Este artículo le guía a través de varios escenarios comunes que es probable que encuentre al administra solicitudes de aprobación en la aplicación móvil de Power Automate.

> [!NOTE]
> Las imágenes de este tema son de un dispositivo Android; sin embargo, en iOS el proceso es similar.
> 
> 

## <a name="prerequisites"></a>Requisitos previos
Para completar este tutorial, se necesita:

* Un dispositivo [Android](https://aka.ms/flowmobiledocsandroid) o [iOS](https://aka.ms/flowmobiledocsios) que ejecute la aplicación móvil de Power Automate.
* Ser designado aprobador en un flujo de aprobación.
* Solicitudes pendientes de aprobación.

## <a name="view-pending-requests"></a>Visualización de solicitudes pendientes
1. Abra la aplicación móvil para Power Automate.
   
    ![iniciar la aplicación móvil](./media/mobile-approvals/open-app.png)
2. Seleccione **APROBACIONES** en la esquina superior derecha.
   
    ![seleccionar aprobaciones](./media/mobile-approvals/select-approvals.png)
3. Vea todas las aprobaciones pendientes:
   
    ![ver solicitudes de aprobación pendientes](./media/mobile-approvals/show-pending-approval-requests.png)

Si no hay solicitudes de aprobación pendientes, cree un [flujo de aprobación](modern-approvals.md), configúrese como aprobador y desencadene el flujo. Las solicitudes de aprobación aparecen en el centro de aprobaciones unos segundos después de que el flujo se desencadena y se envía una solicitud de aprobación.

## <a name="approve-requests-and-leave-an-optional-comment"></a>Aprobar solicitudes y dejar un comentario opcional
1. Si no lo ha hecho, siga los pasos anteriores para [ver las solicitudes pendientes](mobile-approvals.md#view-pending-requests).
2. Seleccione **APROBAR** en la solicitud que desea aprobar.
   
    ![seleccione aprobar](./media/mobile-approvals/select-approve.png)
3. (Opcional) seleccione **Agregar comentario (opcional)** .
   
    ![seleccione agregar una condición](./media/mobile-approvals/select-add-comment.png)
   
    Escriba un comentario en la pantalla **Agregar comentario**.
   
    ![escriba su comentario](./media/mobile-approvals/enter-comment-for-approval.png)
4. Seleccione **CONFIRMAR** en la esquina superior derecha.
   
    ![confirme que ha terminado](./media/mobile-approvals/tap-confirm-button.png)
   
    La pantalla de operación correcta se muestra después de que el flujo registra su decisión.
   
    ![pantalla de operación correcta](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>Rechazar solicitudes y dejar un comentario opcional
Siga los [pasos para aprobar una solicitud](mobile-approvals.md#approve-requests-and-leave-an-optional-comment), pero seleccione **RECHAZAR** en el segundo paso.

## <a name="learn-more"></a>Más información
[Creación de flujos de aprobación modernos](modern-approvals.md).

