---
title: Creación de flujos de aprobación con respuestas personalizadas | Microsoft Docs
description: Cree flujos de aprobación con respuestas personalizadas.
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
ms.date: 05/04/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- maker
ms.openlocfilehash: dc2eaf9ac0ffc0edb10f5cb096ee98dad6aac55d
ms.sourcegitcommit: 9cca2a2fca8371ab883b12011c1c4485ceb9c761
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "3299439"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Creación de opciones de respuesta personalizadas para flujos de aprobación


Supongamos que quiere enviar una solicitud de aprobación cada vez que un empleado carga un informe de gastos en SharePoint y, luego, permitir que el aprobador responda con una de estas tres opciones: Aceptar, Se necesita más información o Rechazar.


## <a name="prerequisites"></a>Requisitos previos

- Una cuenta de Power Automate.
- Una lista de SharePoint para que los empleados inserten sus informes de gastos.

## <a name="create-approval-flow"></a>Creación de un flujo de aprobación
1. Inicie sesión en [Power Automate](https://flow.microsoft.com).
1. En la barra de navegación izquierda, seleccione **Mis flujos**.
1. Seleccione **Nuevo** > **Automatizar desde cero**.

    ![Opción Crear desde cero](media/create-approval-response-options/create-approval-response-options.png)

1. En la pantalla que se abre, especifique un nombre para su flujo en **Nombre de flujo**. 
  
1. Buscar **SharePoint** en **Elija el desencadenador del flujo**, seleccione **Cuando se crea un artículo** de la lista de desencadenadores, y luego seleccione **Crear**.

   ![Seleccionar Crear desde cero](media/create-approval-response-options/create-from-blank.png)

1. Rellene los campos **Dirección del sitio** y **Nombre de lista** de SharePoint. 

   >[!TIP]
   >Seleccione **Escribir valor personalizado** en el campo **Dirección del sitio** antes de escribir texto en **Dirección del sitio**.

1. Seleccione **Nuevo paso**, busque **Aprobación** y, luego, seleccione **Iniciar y esperar una aprobación**.

1. En la tarjeta **Iniciar y esperar una aprobación**, seleccione la lista **Tipo de aprobación**.

1. Seleccione **Respuestas personalizadas: esperar una respuesta**.

    ![Tipo de aprobación](media/create-approval-response-options/select-approval-type.png)

    A continuación, creará las respuestas personalizadas que los aprobadores usarán cuando respondan a una solicitud de aprobación de los gastos de un empleado.


1. En el cuadro **Elemento de opciones de respuesta**, escriba **Aceptar** y, luego, seleccione **Agregar nuevo elemento**. 

    ![Respuesta personalizada 1](media/create-approval-response-options/enter-response-1.png)

1. En el cuadro **Elemento de opciones de respuesta**, escriba **Aceptar** y, luego, seleccione **Agregar nuevo elemento**.

1. En el cuadro **Elemento de opciones de respuesta**, escriba **Se necesita más información**.

    ![Respuesta personalizada 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Rellene la información de los campos **Título**, **Asignado a** (correo electrónico del aprobador) y **Detalles** (los detalles que contendrá la solicitud de aprobación).

    Este es un ejemplo de los datos que podría incluir para su organización.

    ![Detalles de las respuestas personalizadas](media/create-approval-response-options/enter-title-assigned-to-details.png)


Ahora que ha creado las respuestas personalizadas, quizás le interese realizar diferentes acciones en el flujo, en función de la respuesta del aprobador.


## <a name="use-approval-responses"></a>Uso de las respuestas de aprobación 

Si la respuesta a la solicitud es **Aceptar**, puede que quiera enviar un correo electrónico al departamento de contabilidad para pedirles que reembolsen los gastos al empleado. 

Si la respuesta es **Rechazar**, puede que quiera enviar un correo electrónico al empleado para informarle de que la solicitud se ha rechazado.

Y, por último, si la respuesta del aprobador es **Se necesita más información**, puede que quiera enviar un correo electrónico al empleado para solicitarle que proporcione más información.

Para realizar cualquiera de estas acciones en el flujo, agregue [**Condición**](add-condition.md) o una acción **Cambiar** al flujo y, luego, seleccione el campo **Resultados** de la solicitud de aprobación en el selector de contenido dinámico. Asegúrese de confirmar si el valor es Aceptar, Se necesita más información o Rechazar.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Respuesta a las solicitudes de aprobación con una respuesta personalizada

Los aprobadores reciben solicitudes de aprobación en el correo electrónico. Las solicitudes también se muestran en el centro de aprobación de Power Automate. 

![Correo electrónico de solicitud de aprobación](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>Más información
- Creación de [flujos de aprobador único](modern-approvals.md)
- Creación de [flujos de aprobador secuenciales.](sequential-modern-approvals.md)
