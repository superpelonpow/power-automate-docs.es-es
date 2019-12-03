---
title: Creación de flujos desde el panel de inicio de OneDrive para la Empresa | Microsoft Docs
description: Cree flujos desde el panel de inicio de OneDrive para la Empresa.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/25/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d7af2e8171a460159905edc4fed0ad1a3427343a
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74374985"
---
# <a name="create-flows-from-the-onedrive-for-business-launch-panel"></a>Creación de flujos desde el panel de inicio de OneDrive para la Empresa
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

De manera similar al [Panel de inicio de Power Automate en SharePoint](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/), puede ejecutar flujos en archivos específicos en OneDrive para la Empresa. 

Esta característica permite que la persona que ejecuta el flujo use sus propias credenciales, lo que se aplica especialmente a los flujos creados por un departamento de TI. 

Los usuarios también pueden obtener solicitudes de entradas en tiempo de ejecución como **Approver** (Aprobador) o **Message** (Mensaje), que puede ser de tipo texto, archivo, correo electrónico, booleano o número.

En este tutorial, vamos a crear un flujo sencillo que usa una de las muchas [plantillas de OneDrive para la Empresa](https://flow.microsoft.com/search/?q=OneDrive) para solicitar la aprobación de un archivo por parte del administrador del solicitante.

## <a name="create-a-flow-that-requests-manager-approval-for-a-file-in-onedrive-for-business"></a>Creación de un flujo que solicita la aprobación de un administrador para un archivo en OneDrive para la Empresa

1. Inicie sesión en OneDrive para la Empresa.
1. Busque y seleccione el archivo en el que quiere crear el flujo.
1. Seleccione el vínculo **Mostrar acciones** (tres puntos).
1. Seleccione **Flujo** > **Crear un flujo**.

     ![Crear flujo](./media/onedrive-launch-panel/create-flow.png) 

1. Seleccione una de las plantillas.

    En este ejemplo, seleccione la plantilla **Request my manager's approval for the selected file** (Solicitar la aprobación de mi administrador para el archivo seleccionado).

     >[!TIP]
     >Inicie sesión en cualquier conector que solicita que inicie sesión.

1. Seleccione **Continuar**.
1. Haga los cambios que quiera en la plantilla y, luego, guarde el flujo con un nombre que recuerde fácilmente.

## <a name="run-the-flow"></a>Ejecución del flujo

1. Inicie sesión en OneDrive para la Empresa.
1. Busque y seleccione el archivo en el que se va a solicitar la aprobación del administrador.
1. Seleccione el vínculo **Mostrar acciones** (tres puntos).
1. Seleccione **Flujo**. Verá el flujo que creó anteriormente.
1. Seleccione el flujo que creó anteriormente.

     ![Ejecución del flujo](./media/onedrive-launch-panel/run-flow.png)


>[!TIP]
>Aunque en este tutorial se muestra cómo crear un flujo a partir de una plantilla, también puede crear un flujo desde cero para usar cualquiera de los cientos de conectores disponibles en Power Automate.

## <a name="learn-more"></a>Más información

- [Introducción a Power Automate](getting-started.md) 
- [Compilación de flujos de varios pasos](multi-step-logic-flow.md)
