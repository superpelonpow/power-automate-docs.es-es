---
title: Preguntas acerca de la facturación y las mediciones | Microsoft Docs
description: Respuestas a las preguntas frecuentes sobre la facturación y la medición en Power Automate
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 3ea993f30f34a9997a1a3a3580b0151e93223d7a
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74356792"
---
# <a name="billing-and-metering-questions"></a>Preguntas acerca de la facturación y la medición
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

En este artículo se da respuesta a las preguntas frecuentes sobre la facturación y la medición en Power Automate.

>[!NOTE]
> A partir del 1 de octubre de 2019, Power Apps y Power Automate usarán un [nuevo modelo de licencia](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq). 

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>¿Dónde puedo encontrar los precios planes disponibles?

Consulte la [página de precios](https://flow.microsoft.com/pricing/).

## <a name="where-can-i-find-out-what-my-plan-is"></a>¿Dónde puedo encontrar averiguar cuál es mi plan?

Consulte la [página de precios](https://flow.microsoft.com/pricing/).

## <a name="how-do-i-switch-plans"></a>¿Cómo se cambiar de plan?

En el menú de navegación superior, seleccione **Información** > **Precios** y seleccione el plan al que quiera cambiar.

![Más información > Precios](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>¿Cómo sé cuánto he usado?

Si tiene un plan gratuito o un plan de evaluación, haga clic o pulse el icono del engranaje de la barra de navegación superior para mostrar su uso actual en el plan. 

![Botón Configuración](./media/billing-questions/settings.png)

Si tiene un plan de pago, las ejecuciones se agrupan entre todos los usuarios de la organización. Estamos trabajando en características que muestren la cuota disponible y el uso en una organización.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>¿Qué ocurre si mi uso supera los límites?

Power Automate acelera las ejecuciones de los flujos.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>¿Dónde puedo encontrar más información acerca de los límites de uso?

En el [página de precios](https://flow.microsoft.com/pricing/), consulte la sección de **preguntas más frecuentes**.

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>¿Qué sucede si intento realizar ejecuciones con demasiada frecuencia?

El plan determina la frecuencia con que se ejecutan los flujos. Por ejemplo, en los planes gratuitos, los flujos pueden ejecutarse cada 15 minutos. Si un flujo se desencadena menos de 15 minutos después de su última ejecución, se pone en cola hasta que hayan transcurrido los 15 minutos.

## <a name="what-counts-as-a-run"></a>¿Qué se considera una ejecución?

Cada vez que se desencadene un flujo, independientemente de que lo haga un desencadenador automático o se inicie manualmente, se considera una ejecución. Las comprobaciones de la existencia de datos nuevos no cuentan como ejecuciones.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>¿Hay diferencias entre las cuentas Microsoft y las cuentas profesionales o educativo de cara a la facturación?

Sí. Si inicia sesión con una cuenta Microsoft (por ejemplo, una cuenta que termine eh @outlook.com o @gmail.com), solo puede utilizar el plan gratuito. Para sacar provecho de las características del plan de pago, inicie sesión con una dirección de correo electrónico profesional o educativa.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>Al intentar realizar una actualización, se me indica que mi cuenta no es apta.

Para actualizar, use una cuenta profesional o educativa, o cree una [cuenta de prueba de Office 365](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/).

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Mi flujo se ha ejecutado muy pocas veces, ¿por qué me he quedado sin ejecuciones?

Ciertos flujos pueden ejecutarse con mayor frecuencia de la esperada. Por ejemplo, puede crear un flujo que le envíe una notificación push cada vez que su jefe le envíe un correo electrónico. Dicho flujo debe ejecutarse cada vez que reciba un correo electrónico (de cualquier persona), ya que el flujo debe comprobar si el correo electrónico procede de su jefe. Esta acción cuenta como su ejecución.

Para solucionar este problema coloque en el desencadenador todos los filtros que sean necesarios. En el ejemplo de notificación de inserción, expanda el menú **Opciones avanzadas** y proporcione la dirección de correo electrónico de su administrador en el campo **De**.

## <a name="other-limits-and-caveats"></a>Otros límites y advertencias

* Cada cuenta puede tener:
  * 250 flujos.
  * 15 conectores personalizados.
  * 20 conexiones por API y un total de 100 conexiones.
* Puede instalar una puerta de enlace solo en el entorno predeterminado.
* Algunos conectores externos, como Twitter, implementan la limitación de conexiones para controlar la calidad del servicio. Se produce un error en los flujos al estar en vigor la limitación. Si se producen errores en los flujos, revise los detalles de la ejecución con errores en el historial de ejecuciones del flujo.
