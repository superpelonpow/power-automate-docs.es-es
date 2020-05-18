---
title: Introducción a los flujos compatibles con la solución | Microsoft Docs
description: Aprenda sobre las ventajas de la creación de flujos en soluciones.
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
ms.openlocfilehash: 56b90ebdf7f3655763b7e40c60b985f06604c47b
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298295"
---
# <a name="overview"></a>Información general


Cuando hospeda sus flujos en una [solución](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview), se convierten en portátiles, lo que facilita su traslado y el de todos sus componentes de un entorno a otro. Un caso típico de uso es que un fabricante de software independiente desarrolle flujos en un entorno de espacio aislado y luego los mueva a un entorno de prueba. Después de la prueba, el fabricante de software independiente movería los flujos a un entorno de producción para los clientes que compran estos flujos. Este proceso es mucho más fácil cuando se crean los flujos en las soluciones y, a continuación, se desplazan las soluciones y su contenido.

Se crea dentro de una solución de flujos se conocen como flujos *compatibles con la solución*. Puede agregar varios flujos en una única solución.

> [!NOTE] 
> No se puede mover flujos no compatibles con la solución (flujos que no se han creado en una solución) a una solución.

## <a name="prerequisites"></a>Requisitos previos

Debe tener los siguientes componentes para crear soluciones y flujos compatibles con la solución:

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- Un entorno con la versión 9.1.0.267 o posterior.

  Para comprobar la versión, vaya al [Centro de administración de Power Automate](https://admin.flow.microsoft.com) y seleccione sucesivamente **Entornos**, seleccione el entorno en el que esté interesado y, a continuación, seleccione la pestaña **Detalles**.

## <a name="create-a-solution"></a>Crear una solución

Siga estos pasos para crear una solución:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com).
1. Seleccione **Soluciones** desde la barra de navegación.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. Seleccione **+ Nueva solución**.

   ![](./media/overview-solution-flows/select-new-solution.png)

1. Proporcione toda la información necesaria para la nueva solución, incluidos **Nombre para mostrar**, **Editor**, **Versión** y **Nombre**. También es una buena idea proporcionar una descripción de la solución.

   ![](./media/overview-solution-flows/new-solution.png)

1. Seleccione **Guardar y cerrar** en el menú de la parte superior.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   La nueva solución podría aparecer como esta imagen:

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > Seleccione **Soluciones** para actualizar la lista de soluciones si no aparece la nueva solución.

## <a name="learn-more"></a>Más información

- [Creación de un flujo en una solución](./create-flow-solution.md)
- [Exportación de soluciones](./export-flow-solution.md)
- [Importación de soluciones](./import-flow-solution.md)
- [Edición de un flujo compatible con la solución](./edit-solution-aware-flow.md)
- [Eliminación de un flujo compatible con la solución](./remove-solution-aware-flow.md)
