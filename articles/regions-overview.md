---
title: Información general de las regiones para Power Automate | Microsoft Docs
description: Información general con preguntas y respuestas acerca de las regiones de Power Automate
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/07/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a87845247f57e58edf7170dc3e8da721db7d275e
ms.sourcegitcommit: 27ee91452be26cf5c96397c39f9f5b8bede14cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "3299153"
---
# <a name="faq-for-regions-in-power-automate"></a>P+F de regiones en Power Automate

Este documento proporciona una lista de preguntas más frecuentes acerca de Power Automate.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>¿Cómo averiguar donde se implementa el flujo?
El flujo se implementa en la [región](https://azure.microsoft.com/regions/) que hospeda el [entorno](environments-overview-admin.md). Por ejemplo, si su entorno se crea en la región de Europa, el flujo se implementa en los centros de datos de Europa.

Los administradores pueden identificar la región si inician sesión en el [Centro de administración](https://admin.flow.microsoft.com) de Power Automate. La pestaña **Entornos** enumera todos los entornos existentes y sus regiones.

![ver entornos](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>¿Qué regiones hay disponibles?
* Estados Unidos
* Europa
* Asia
* Australia
* India
* Japón
* Canadá
* Sudamérica
* Reino Unido
* Gobierno de EE. UU. (GCC)
* Francia

## <a name="what-features-are-specific-to-a-given-region"></a>¿Qué características son específicas de una región determinada?

Los entornos se pueden crear en distintas regiones y enlazarse a esa ubicación geográfica. Cuando se crea un flujo en un entorno, dicho flujo se implementa en los centros de datos de dicha ubicación geográfica. Esto es aplicable a cualquier elemento que cree en ese entorno, incluidos Common Data Service, flujos, conexiones, puertas de enlace, aplicaciones y conectores personalizados.

Para un rendimiento óptimo, cree el entorno en la región más cercana a los usuarios. Por ejemplo, si los usuarios están en Europa, cree el entorno en la región de Europa. Si los usuarios están en Estados Unidos, cree el entorno en la región de Estados Unidos.

## <a name="region-mappings-for-power-automate-and-gateways"></a>Asignaciones de región para Power Automate y puertas de enlace

La región en la que está instalada la puerta de enlace debe estar asignada a la región de Power Automate. No se admiten límites entre regiones geográficas. 

Esta es la información de asignación:

Power Platform región|Región de la puerta de enlace
-----|-----
Estados Unidos, incluida la versión preliminar|Centro de EE. UU., Este de EE. UU. 2, Centro-norte de EE. UU., Centro-sur de EE. UU., Oeste de EE. UU. 2, Centro-oeste de EE. UU. y Oeste de EE. UU.
Asia|Asia oriental, sudeste asiático
Australia|Australia oriental, Sudeste de Australia
Canadá|Canadá central, Canadá este
Europa|Norte de Europa, Oeste de Europa
Francia|Centro de Francia, Sur de Francia
India|Centro de la India, India del Sur, Oeste de la India
Japón|Japón oriental, Japón occidental
Sudamérica|Sur de Brasil
Reino Unido|Sur de Reino Unido, Oeste de Reino Unido

## <a name="is-power-automate-available-in-national-clouds"></a>¿Está Power Automate disponible en nubes nacionales?
Sí. [Más información](./us-govt.md).

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>¿Qué direcciones IP se usan en cada región?
Consulte [Límites y configuración](limits-and-config.md).

