---
title: Envío de datos adjuntos con solicitudes de aprobación | Microsoft Docs
description: Aprenda a crear flujos que envíen datos adjuntos con solicitudes de aprobación.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/15/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1506902cdd6afe90d7e12a910e2e14519cae7554
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296953"
---
# <a name="create-approval-flows-with-attachments"></a>Creación de flujos de aprobación con datos adjuntos

En algunas ocasiones, necesitará obtener la aprobación de un archivo para fines empresariales. Afortunadamente, puede usar las aprobaciones de Power Automate para hacerlo. Por ejemplo, supongamos que es un contable y quiere obtener la aprobación de una factura: puede crear un flujo instantáneo que le permita enviar el archivo para su aprobación simplemente pulsando un botón y seleccionando el archivo que quiere enviar.

En este artículo, aprenderá a crear un flujo de aprobación que envía datos adjuntos que el aprobador debe revisar antes de decidir si se debe aprobar la solicitud.

## <a name="create-the-flow"></a>Creación del flujo

1. Iniciar sesión en Power Automate.
1. Seleccione **Mis flujos** > **Nuevo** > **Instantáneo: desde cero**.

    ![Nuevo flujo instantáneo en blanco](./media/approval-attachments/new-instand-blank.png)

1. Asigne un nombre al flujo > búsquelo y, después, seleccione **Desencadenar un flujo manualmente** y, luego, seleccione **Crear**.

    ![Asignación de un nombre al flujo y selección de un desencadenador](./media/approval-attachments/name-flow-trigger.png)

1. Seleccione el desencadenador **Desencadenar un flujo manualmente** > **Agregar una entrada** > **Archivo**.

     En los pasos anteriores se configura el flujo para que, cuando se ejecute el flujo, solicite un archivo del usuario para desencadenar el flujo.

1. Seleccione **Nuevo paso**.
1. Busque **Aprobaciones** y seleccione **Iniciar y esperar una aprobación**.
1. Seleccione **Aprobar o rechazar: primero en responder** en la lista **Tipo de aprobación** de la tarjeta **Iniciar y esperar una aprobación**.
1. Proporcione esta información en la tarjeta **Iniciar y esperar una aprobación**:

   - **Título**: esta es una descripción breve que indica al aprobador de qué trata la solicitud.
   - **Asignado a**: la persona a la que se envía la solicitud.
   - **Detalles**: este texto se muestra en la solicitud de aprobación.

     ![La tarjeta de solicitud de aprobación](./media/approval-attachments/approval-request-card.png)

1. Seleccione **Mostrar opciones avanzadas** para mostrar los campos en los que se proporcionará información sobre el archivo adjunto a la solicitud.
1. Proporcione un nombre de archivo en **Nombre de datos adjuntos: 1**

   >[!TIP]
   >Debe incluir la extensión de archivo que coincida con el tipo de archivo que se carga.

1. Proporcione el contenido del archivo que se enviará al aprobador en el cuadro **Contenido de los datos adjuntos: 1**. 

   Una manera sencilla de hacerlo es usa el elemento **Contenido del archivo** en la lista de contenido dinámico que aparece al seleccionar el cuadro **Contenido de los datos adjuntos: 1**.

     ![Opciones avanzadas de la tarjeta de solicitud de aprobación](./media/approval-attachments/approval-request-card-advanced-options.png)

1. Seleccione **Guardar** para guardar el flujo.

## <a name="test-your-flow"></a>Prueba del flujo

Para probar el flujo, seleccione **Probar** y, luego, cargue un archivo .xlsx.

1. Seleccionar **Prueba**.
1. Seleccione **Realizaré la acción del desencadenador**.

     ![Prueba del flujo](./media/approval-attachments/test-flow.png)

1. Seleccione **Probar** > **Continuar** para iniciar la prueba.
1. Seleccione **Importar**.

     ![](./media/approval-attachments/import-file.png)
1. Busque el archivo, selecciónelo y, a continuación, seleccione **Abrir** para cargar el archivo o la imagen que va a enviar para su aprobación.

1. Haga clic en **Ejecutar flujo**.

   Verá que se inicia la ejecución de la prueba.

     ![La prueba se inicia](./media/approval-attachments/test-started.png)

1. Seleccione **Página de ejecuciones de flujo** para supervisar el estado de la prueba.

## <a name="approve-the-request"></a>Aprobación de la solicitud

La persona a la que envía la solicitud de aprobación recibe un correo electrónico, similar a esta imagen, donde puede ver los datos adjuntos y, a continuación, **Aprobar** o **Rechazar** la solicitud:

![Vista del correo electrónico de solicitud](./media/approval-attachments/approval-request-mail.png)

>[!TIP]
>Los aprobadores también pueden revisar las solicitudes en el centro de aprobaciones.

## <a name="learn-more"></a>Más información

En la mayoría de los flujos de aprobación, querrá notificar la decisión a la persona que solicita la aprobación. Siga el [artículo sobre las aprobaciones modernas](modern-approvals.md#add-an-email-action-for-approvals) para aprender a agregar una **condición** a un flujo de aprobación para realizar acciones específicas en función del **resultado** de la solicitud.

