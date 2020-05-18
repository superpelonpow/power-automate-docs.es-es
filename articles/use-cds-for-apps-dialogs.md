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
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298427"
---
# <a name="use-common-data-service-dialogs-for-guided-processes-deprecated"></a>Uso de cuadros de diálogo de Common Data Service para procesos guiados (en desuso)


[Los cuadros de diálogo están en desuso](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). Debe reemplazar los cuadros de diálogo con aplicaciones de lienzo o flujos de proceso de negocio. Más información: [Sustituir diálogos por flujos de proceso de negocio o aplicaciones de lienzo](replace-dialogs.md) 

Los diálogos son los procesos sincrónicos o interactivos en Common Data Service que recopilan y procesan la información mediante el uso de scripts paso a paso para guiar a los usuarios a través de un proceso. Por ejemplo, puede crear diálogos que actúen como guía para los representantes de servicio para la resolución del caso y la elevación del caso. De forma similar, puede crear cuadros de diálogo para estandarizar los procesos de ventas como la calificación de oportunidades y la puntuación de clientes potenciales.

## <a name="differences-between-workflows-and-dialogs"></a>Diferencias entre flujos de trabajo y cuadros de diálogo

En la siguiente tabla se proporciona información sobre las diferencias entre flujos de trabajo y diálogos en Common Data Service.  


| Flujos de trabajo     |    Diálogos      |
|---------------|--------------|
|                                                                                                  Los puede iniciar un usuario o se pueden automatizar.                                                                                                   |                                                                                          Debe iniciarlo un usuario.                                                                                          |
|                                  Son procesos asincrónicos o en tiempo real, y no requieren la entrada del usuario para ejecutarse hasta completarse. Los procesos asincrónicos se ejecutan en segundo plano mientras los procesos en tiempo real se ejecutan inmediatamente.                                   | Los procesos en tiempo real requieren la entrada del usuario para ejecutarse hasta completarse. Al ejecutar estos procesos, se presenta una interfaz de asistente para hacer las selecciones correspondientes para ejecutar los procesos. |
|                                                    La entidad que almacena los detalles acerca de un flujo de trabajo asincrónico en ejecución es `AsyncOperation` mientras `Process` se usa para un flujo de trabajo en tiempo real.                                                     |                                                       La entidad que almacena la información generada por un diálogo en ejecución es la entidad `ProcessSession`.                                                       |
|                  Los desencadenadores son compatibles con flujos de trabajo. Para obtener una lista de los desencadenadores admitidos, vea [Tipos, desencadenadores, entidades y acciones compatibles para procesos](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes).                   |                                                                                   Los desencadenadores no se admiten para los cuadros de diálogo.                                                                                    |
  
### <a name="see-also"></a>Vea también
[Reemplazo de cuadros de diálogo con aplicaciones de lienzo o flujos de proceso de negocio](replace-dialogs.md)
