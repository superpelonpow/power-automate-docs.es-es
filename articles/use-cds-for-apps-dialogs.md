---
title: Uso de cuadros de diálogo de Common Data Service para procesos guiados (en desuso) | Microsoft Docs
description: Los cuadros de diálogo son los procesos sincrónicos o interactivos que recopilan y procesan información mediante guiones paso a paso para dirigir a los usuarios a través de un proceso
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
ms.service: flow
ms.assetid: d17f8ae2-854b-4f67-a115-5a03d4f0b8ce
caps.latest.revision: 25
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 69b8d448a3bb2636f4804fe75645467ca6bd081d
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195874"
---
# <a name="use-common-data-service-dialogs-for-guided-processes-deprecated"></a>Uso de cuadros de diálogo de Common Data Service para procesos guiados (en desuso)


[Los cuadros de diálogo están en desuso](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). Debe reemplazar los cuadros de diálogo con aplicaciones de lienzo o flujos de proceso de negocio. Más información: [Reemplazo de cuadros de diálogo con aplicaciones de lienzo o flujos de proceso de negocio](replace-dialogs.md) 

Los cuadros de diálogo son los procesos sincrónicos o interactivos de Common Data Service en los que se recopila y procesa información mediante guiones paso a paso para dirigir a los usuarios a través de un proceso. Por ejemplo, puede crear cuadros de diálogo que actúen como una guía para los representantes de servicios para la resolución y remisión de casos. De forma similar, puede crear cuadros de diálogo para estandarizar los procesos de ventas como la calificación de oportunidades y la puntuación de clientes potenciales.

## <a name="differences-between-workflows-and-dialogs"></a>Diferencias entre flujos de trabajo y cuadros de diálogo

En la tabla siguiente se proporciona información sobre las diferencias entre los flujos de trabajo y los cuadros de diálogo de Common Data Service.  


| Flujos de trabajo     |    Cuadros de diálogo      |
|---------------|--------------|
|                                                                                                  Los puede iniciar un usuario o se pueden automatizar.                                                                                                   |                                                                                          Los debe iniciar un usuario.                                                                                          |
|                                  Son procesos asincrónicos o en tiempo real, y no requieren la entrada del usuario para ejecutarse hasta su finalización. Los procesos asincrónicos se ejecutan en segundo plano mientras que los procesos en tiempo real se ejecutan de forma inmediata.                                   | Son procesos en tiempo real que requieren la entrada del usuario para ejecutarse hasta su finalización. Al ejecutar estos procesos, se le presenta una interfaz de tipo asistente para que pueda realizar las selecciones adecuadas para ejecutar los procesos. |
|                                                    La entidad en la que se almacenan los detalles sobre un flujo de trabajo asincrónico en ejecución es `AsyncOperation`, mientras que `Process` se usa para un flujo de trabajo en tiempo real.                                                     |                                                       La entidad en la que se almacena la información generada por un cuadro de diálogo en ejecución es `ProcessSession`.                                                       |
|                  Los flujos de trabajo admiten desencadenadores. Para obtener una lista de los desencadenadores admitidos, vea [Tipos, desencadenadores, entidades y acciones compatibles para procesos](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes).                   |                                                                                   Los desencadenadores no se admiten para los cuadros de diálogo.                                                                                    |
  
### <a name="see-also"></a>Vea también
[Reemplazo de cuadros de diálogo con aplicaciones de lienzo o flujos de proceso de negocio](replace-dialogs.md)
