---
title: Puerta de enlace de datos local | Microsoft Docs
description: Este artículo es una introducción general sobre la puerta de enlace de datos local para Power Automate.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2a0e2d3ff9fb39019ef4b8f37a7715229844c388
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297745"
---
# <a name="what-is-an-on-premises-data-gateway"></a>¿Qué es una puerta de enlace de datos local?


Una puerta de enlace de datos local actúa como un puente, para proporcionar una transferencia de datos rápida y segura entre los datos locales (los datos que no se encuentran en la nube) y varios servicios en la nube de Microsoft. Estos servicios en la nube incluyen Power BI, Power Apps, Power Automate, Azure Analysis Services y Azure Logic Apps. Al usar una puerta de enlace, las organizaciones pueden mantener bases de datos y otros orígenes de datos en sus redes locales, pero usar de forma segura esos datos locales en servicios en la nube.

## <a name="how-the-gateway-works"></a>Cómo funciona la puerta de enlace

![Información general de la puerta de enlace](media/gateway-reference/on-premises-data-gateway.png)

Para más información sobre cómo funciona la puerta de enlace, vea [Arquitectura de puerta de enlace de datos local](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="types-of-gateways"></a>Tipos de puertas de enlace

Hay dos tipos de puertas de enlace diferentes, cada una para un escenario distinto:

- **Puerta de enlace de datos local**: permite que varios usuarios se conecten a varios orígenes de datos locales. Puede usar una puerta de enlace de datos local con todos los servicios admitidos, con una sola instalación de puerta de enlace. Esta puerta de enlace está diseñada especialmente para escenarios complejos en los que varios usuarios acceden a varios orígenes de datos.

- **Puerta de enlace de datos local (modo personal)**: permite que un usuario se conecte a los orígenes y no pueda compartirlos con otros usuarios. Una puerta de enlace de datos local (modo personal) solo se puede usar con Power BI. Esta puerta de enlace está diseñada especialmente para los escenarios en los que usted es el único que crea informes y no necesita compartir ningún origen de datos con otros usuarios.

## <a name="use-a-gateway"></a>Uso de una puerta de enlace

Hay cuatro pasos principales para usar una puerta de enlace.

1. [Descargar e instalar la puerta de enlace](/data-integration/gateway/service-gateway-install) en un equipo local.
2. [Configurar](/data-integration/gateway/service-gateway-app) la puerta de enlace según el firewall y otros requisitos de red.
3. [Agregar administradores de puerta de enlace](/data-integration/gateway/service-gateway-manage) que también pueden administrar otros requisitos de red.
4. [Solucionar los problemas](/data-integration/gateway/service-gateway-tshoot) de la puerta de enlace en caso de errores.

## <a name="next-steps"></a>Pasos siguientes

- [Instalación de la puerta de enlace de datos local](/data-integration/gateway/service-gateway-install)
