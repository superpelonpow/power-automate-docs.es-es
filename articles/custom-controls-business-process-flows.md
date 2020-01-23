---
title: Uso de controles personalizados en flujos de procesos de negocio | Microsoft Docs
description: Aprenda a usar los controles personalizados en los pasos de flujos de procesos de negocio.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/15/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: cd312fea655dfc652cf92a440801da2fdb17ebe4
ms.sourcegitcommit: c6c4150daadbcc38ef1a33a5903df531b8461ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75942986"
---
# <a name="use-custom-controls-in-business-process-flows"></a>Uso de controles personalizados en flujos de procesos de negocio

Los flujos de procesos de negocio proporcionan una manera guiada de realizar el trabajo en forma de fases y pasos. Las fases indican dónde se encuentra en el proceso, mientras que los pasos son elementos de acción que conducen a un resultado deseado. Los pasos de un proceso de negocio se enlazan a los campos de Common Data Service. Además de las visualizaciones predeterminadas del tipo de campo (cuadros de texto, listas desplegables, etc.), puede usar controles personalizados para agregar visualizaciones enriquecidas (como controles deslizantes, botones radiales, el control LinkedIn, etc.) a los pasos de los flujos de procesos de negocio y ofrecer experiencias atractivas para quienes usan su proceso de negocio.

## <a name="adding-custom-controls-to-a-business-process"></a>Incorporación de controles personalizados a un proceso de negocio

Supongamos que quiere agregar un botón radial para el paso **Presupuesto estimado** y un conmutador para el paso **Identificar el responsable de toma de decisiones** del proceso de cliente potencial a ventas de la oportunidad. 

![Información general](./media/custom-controls/overview.png)

Estos son los pasos que debe seguir para agregar controles personalizados a un flujo de proceso de negocio:

1. Configure los controles personalizados en un formulario de entidad relacionado.
1. Genere y exporte el formulario de flujo de procesos de negocio.
1. Copie las configuraciones de controles personalizados en el formulario de flujo de procesos de negocio desde el formulario de entidad relacionado.
1. Vuelva a importar las personalizaciones a Common Data Service.

Siga estos pasos para obtener [un tutorial detallado sobre cómo agregar controles personalizados](https://powerusers.microsoft.com/t5/Power-Automate-Community-Blog/Preview-Custom-Controls-in-Business-Process-Flows/ba-p/263237) a los flujos de procesos de negocio.






