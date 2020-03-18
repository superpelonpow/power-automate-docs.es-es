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
ms.openlocfilehash: 8470d927204f1ba40f801c806c34ca0c78336555
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193850"
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

## <a name="gateways"></a>Puertas de enlace
Las puertas de enlace son las siguientes:

* Actualmente no está disponible en la región de la India.
* Solo se admite en el entorno predeterminado, no en entornos personalizados.

## <a name="is-power-automate-available-in-national-clouds"></a>¿Power Automate está disponible en nubes nacionales?
Sí. [Más información](./us-govt.md).

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>¿Qué direcciones IP se usan en cada región?
Consulte [Límites y configuración](limits-and-config.md).

