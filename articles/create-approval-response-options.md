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
ms.openlocfilehash: ea98043ee9ab952cfd929a100cb76e42508b84bc
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194218"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Creación de opciones de respuesta personalizadas para flujos de aprobación


Supongamos que quiere enviar una solicitud de aprobación cada vez que un empleado carga un informe de gastos en SharePoint y, luego, permitir que el aprobador responda con una de estas tres opciones: Aceptar, Se necesita más información o Rechazar.


## <a name="prerequisites"></a>Requisitos previos

- Una cuenta de Power Automate.
- Una lista de SharePoint para que los empleados inserten sus informes de gastos.

## <a name="create-approval-flow"></a>Creación de un flujo de aprobación
1. Inicie sesión en [Power Automate](https://flow.microsoft.com).
1. En la barra de navegación izquierda, seleccione **Mis flujos**.
1. Seleccione **Nuevo** > **Crear desde cero**.

    ![Opción Crear desde cero](media/create-approval-response-options/create-approval-response-options.png)

1. En la pantalla que se abre, seleccione **Crear desde cero**. 

    ![Seleccionar Crear desde cero](media/create-approval-response-options/create-from-blank.png)

1. Busque **sharepoint** y, luego, seleccione **Cuando se crea un elemento** en la lista de desencadenadores. 

1. Rellene los campos **Dirección del sitio** y **Nombre de lista**. 

1. Seleccione **Nuevo paso**, busque **Aprobación** y, luego, seleccione **Iniciar y esperar una aprobación (V2)** .

1. En la tarjeta **Iniciar y esperar una aprobación (V2)** , seleccione la lista **Tipo de aprobación**.

    ![Tipo de aprobación](media/create-approval-response-options/select-approval-type.png)

1. Seleccione **Respuestas personalizadas: esperar una respuesta (Premium)** .

    ![Respuestas personalizadas](media/create-approval-response-options/select-custom-responses.png)

    A continuación, creará las respuestas personalizadas que los aprobadores usarán cuando respondan a una solicitud de aprobación de los gastos de un empleado.


1. En el cuadro **Response options Item - 1** (Elemento de opciones de respuesta: 1), escriba **Aceptar** y, luego, seleccione **Agregar nuevo elemento**. 

    ![Respuesta personalizada 1](media/create-approval-response-options/enter-response-1.png)

1. En el cuadro **Response options Item - 2** (Elemento de opciones de respuesta: 2), escriba **Aceptar** y, luego, seleccione **Agregar nuevo elemento**.

    ![Respuesta personalizada 2](media/create-approval-response-options/enter-response-2.png)

1. En el cuadro **Response options Item - 3** (Elemento de opciones de respuesta: 3), escriba **Se necesita más información**.

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
