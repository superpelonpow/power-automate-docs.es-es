---
title: Información general de las regiones para Power Automate | Microsoft Docs
description: Información general con preguntas y respuestas acerca de las regiones de Power Automate
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/28/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4c8b2b02cf87abb54a587d9358a4c1f462ceb724
ms.sourcegitcommit: bba5bd4ae3879b6bf1521d8ed636374fe09709e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "80524545"
---
# <a name="faq-for-regions-in-power-automate"></a>Preguntas más frecuentes sobre las regiones en Power Automate

En este documento se proporciona una lista de preguntas más frecuentes sobre Power Automate.

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
Los entornos se pueden crear en distintas regiones y enlazarse a esa ubicación geográfica. Cuando se crea un flujo en un entorno, dicho flujo se implementa en los centros de datos de dicha ubicación geográfica. Esto es aplicable a cualquier elemento que cree en ese entorno, incluidos Common Data Model, flujos, conexiones, puertas de enlace, aplicaciones y conectores personalizados.

Para un rendimiento óptimo, cree el entorno en la región más cercana a los usuarios. Por ejemplo, si los usuarios están en Europa, cree el entorno en la región de Europa. Si los usuarios están en Estados Unidos, cree el entorno en la región de Estados Unidos.

## <a name="region-mappings-for-power-automate-and-gateways"></a>Asignaciones de regiones para Power Automate y puertas de enlace

La región en la que está instalada la puerta de enlace debe estar asignada a la región de Power Automate. No se admiten límites entre regiones geográficas. 

Esta es la información de asignación:

Región de Power Platform|Región de la puerta de enlace
-----|-----
Estados Unidos, incluida la versión preliminar|Centro de EE. UU., Este de EE. UU. 2, Centro-norte de EE. UU., Centro-sur de EE. UU., Oeste de EE. UU. 2, Centro-oeste de EE. UU. y Oeste de EE. UU.
Asia|Este de Asia y Sudeste de Asia
Australia|Este de Australia, Sudeste de Australia
Canadá|Centro de Canadá y Este de Canadá
Europa|Norte de Europa y Oeste de Europa
Francia|Centro de Francia, Sur de Francia
India|Centro de la India, India del Sur, Oeste de la India
Japón|Japón Oriental, Japón Occidental
Sudamérica|Sur de Brasil
Reino Unido|Sur de Reino Unido y Oeste de Reino Unido

## <a name="is-power-automate-available-in-national-clouds"></a>¿Power Automate está disponible en nubes nacionales?
Sí. [Más información](./us-govt.md).

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>¿Qué direcciones IP se usan en cada región?
Consulte [Límites y configuración](limits-and-config.md).

