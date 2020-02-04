---
title: Diseño de flujos con Microsoft Visio | Microsoft Docs
description: Aproveche los conocimientos de Visio de su organización para compilar modelos comunes como punto de partida para crear flujos.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/25/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b22a3b4c3efe294cfd3afa2359c46ee960d1c021
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74370155"
---
# <a name="design-flows-in-microsoft-visio"></a>Diseño de flujos en Microsoft Visio
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

El diseñador de Power Automate es una potente herramienta en la que puede configurar todos los detalles de la lógica. Sin embargo, a veces es posible que desee simplemente esbozar la lógica del flujo antes de empezar a crearlo. Para ello, utilice Microsoft Visio directamente desde Power Automate.

>[!TIP]
> Muchos procesos comparten un modelo común pero tienen pequeñas variaciones en toda la organización. Puede ahorrar tiempo dentro de la organización utilizando Visio para crear un modelo de flujo de trabajo principal que otros usuarios ajustarán entonces con parámetros especializados.

## <a name="prerequisites"></a>Requisitos previos

- Una cuenta de Power Automate.
- La aplicación de escritorio de Microsoft Visio (versión en inglés).
- Experiencia en el uso de Microsoft Visio.

## <a name="design-a-workflow-in-visio"></a>Diseño de un flujo de trabajo en Visio

1. Inicie sesión en [Power Automate](https://flow.microsoft.com).
1. Seleccione **Plantillas** en el panel de la izquierda.

     ![Selección de plantillas en el panel de la izquierda](./media/visio-flows/templates-from-left-panel.png)

1. Seleccione **Visio** en la lista.

     ![Filtrado por plantillas de Visio](./media/visio-flows/select-visio.png) 

1. Seleccione la plantilla **Diagrama de BPMN de flujo básico** en la lista de plantillas de **Visio** que se muestra.

     ![Selección de una plantilla de Visio](./media/visio-flows/visio-templates.png) 

     >[!IMPORTANT]
     >Visio le advierte de que los archivos de Internet podrían dañar el dispositivo. Si está seguro de lo que hace, seleccione **Sí** en el mensaje de advertencia.

     ![Advertencia sobre archivos de Internet](./media/visio-flows/visio-warning.png)

1. Se inicia el diseñador de Visio.

     ![Vista del diseñador de Visio](./media/visio-flows/visio-designer.png)


1. Use las formas básicas de BPMN para [diseñar el flujo de trabajo](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a).

   ![Formas básicas de BPMN](./media/visio-flows/bpmn-basic-shapes.png)

## <a name="prepare-to-export-your-workflow-to-power-automate"></a>Preparación para exportar el flujo de trabajo a Power Automate

Siga estos pasos para preparar el flujo de trabajo de modo que pueda exportarlo a Power Automate.

1. Seleccione la pestaña **Proceso**.
1. Seleccione **Prepararse para la exportación** desde el grupo de iconos **Power Automate**.

   ![Selección de icono de preparación para la exportación](./media/visio-flows/prepare-export-icon.png)
   
   Se abre el grupo **Prepararse para la exportación**.

   ![Grupo de prepararse para la exportación](./media/visio-flows/prepare-export-group.png)

1. En la pestaña **Asignación de Flow** del grupo **Prepararse para la exportación**, asigne el diagrama de BPMN a los controles de Power Automate. 

1. En la pestaña **Desencadenadores y acciones** del grupo **Prepararse para la exportación**, asigne el diagrama de BPMN a los desencadenadores y las acciones de Power Automate. Para ello, seleccione cada una de las formas y, a continuación, seleccione un desencadenador o una acción para representar esa forma en Power Automate.

El flujo de trabajo está listo para exportarse cuando esté todo listo en el control **Prepararse para la exportación**.

![Sin problemas](./media/visio-flows/prepare-export-no-issues.png) 

## <a name="export-your-workflow"></a>Exportación del flujo de trabajo
1. Seleccione el botón **Exportar a Flow** para exportar el diagrama de flujo de trabajo a Power Automate.
1. Asigne un nombre al flujo y haga clic en el botón **Crear flujo**.
   
   ![Creación del flujo](./media/visio-flows/export-create-flow.png)

1. Debería ver un informe que notifique que todo se ha ejecutado correctamente similar a este.

    ![Correcto](./media/visio-flows/export-create-flow-success.png)

Ahora puede ejecutar o realizar modificaciones en el flujo desde el diseñador de Power Automate, al igual que cualquier otro flujo.

>[!TIP]
> Use las capacidades de uso compartido y comentarios de Visio para colaborar con varias partes interesadas y crear rápidamente un flujo de trabajo completo.

## <a name="learn-more"></a>Más información

- [Introducción a Power Automate](getting-started.md) 
- [Compilación de flujos de varios pasos](multi-step-logic-flow.md)
- [Diseño de un flujo con Microsoft Visio](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a)

     
