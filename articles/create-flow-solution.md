---
title: Creación de flujos compatibles con la solución | Microsoft Docs
description: Aprenda cómo crear flujos compatibles con la solución.
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
ms.date: 11/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d74cbdb6c03d65a7902a81194491ef67feda6bb2
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297481"
---
# <a name="create-a-flow-in-a-solution"></a>Creación de un flujo en una solución


Los flujos que cree en una solución se conocen como flujos *compatibles con la solución*. Siga estos pasos para crear un flujo compatible con la solución.

## <a name="prerequisites"></a>Requisitos previos

Debe tener al menos una solución para poder crear un flujo compatible con la solución.

## <a name="create-the-flow"></a>Creación del flujo 

1. Inicie sesión en [Power Automate](https://flow.microsoft.com).
1. Seleccione **Soluciones** desde la barra de navegación.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Seleccione la solución en la que creará el flujo.

   ![](./media/create-flow-solution/new-solution-created.png)

1. Seleccione **+ Nuevo** y, a continuación, seleccione **Flujo**.

   ![](./media/create-flow-solution/select-new-flow.png)

   Power Automate se abre.

1. Utilice los conectores y desencadenadores disponibles para aumentar el flujo.

   En este ejemplo, crearemos un flujo simple que envía una notificación cuando un correo electrónico llega a su bandeja de entrada.
1. Busque y seleccione **Office 365 Outlook**.
1. Seleccione el desencadenador **Cuando llega un nuevo correo electrónico**.
1. Seleccione **+ Nuevo paso**.
1. Seleccione la acción **Send me a mobile notification** (Enviarme una notificación del servicio móvil).
1. Añada el token dinámico **Asunto** al campo **Texto** de la casilla **Send me a mobile notification** (Enviarme una notificación del servicio móvil).
1. Asigne un nombre al flujo y guárdelo.

   El flujo debe tener este aspecto:

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Seleccione **Soluciones** para ver el flujo de la solución:

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>Más información

* [Creación de una solución](./overview-solution-flows.md)
* [Exportación de soluciones](./export-flow-solution.md)
* [Importación de soluciones](./import-flow-solution.md)
* [Edición de un flujo compatible con la solución](./edit-solution-aware-flow.md)
* [Eliminación de un flujo compatible con la solución](./remove-solution-aware-flow.md)
