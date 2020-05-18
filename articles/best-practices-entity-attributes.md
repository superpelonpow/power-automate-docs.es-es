---
title: Procedimientos recomendados para el uso de atributos de entidad de flujo de proceso de negocio | Microsoft Docs
description: Conozca los procedimientos recomendados para usar los atributos de entidad de flujo de proceso de negocio.
ms.custom: ''
ms.date: 04/23/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Business Process Flows
helpviewer_keywords:
- flow
- process flow
- business process flow
- process
- workflow
author: msftman
ms.author: deonhe
manager: kvivek
ms.openlocfilehash: b9a4a2968a251efd360a043d23e837eaeb746e4e
ms.sourcegitcommit: 71f9b72d551887324c92b122dadd1b4dd584bc4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "3299263"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>Procedimientos recomendados para usar los atributos de flujo de proceso de negocio



Los atributos de las entidades relacionados con los procesos heredados están en desuso Estos son algunos procedimientos recomendados para usar el atributo *Fase activa* (activestageid) de la entidad de flujo de proceso de negocio. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>Informe sobre la fase activa de un flujo de proceso de negocio

Supongamos que quiere obtener una vista de la canalización de ventas e informar sobre la fase activa en la que se encuentra el **Proceso de cliente potencial a ventas de la oportunidad**.

Anteriormente, para informar sobre los procesos de negocio por fase, se podía definir una vista en cada entidad relacionada del flujo de proceso de negocio y, luego, informar sobre el campo *Fase activa* (activestageid).

Con el desuso del campo *Fase activa* (activestageid) en las entidades relacionadas, hay dos maneras de informar sobre los flujos de proceso de negocio.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Opción 1: vistas y gráficos sobre la entidad de flujo de proceso de negocio **(recomendada)**

En las versiones 9.0 y posteriores, cada flujo de proceso de negocio crea su propia entidad Common Data Service, normalmente con el mismo nombre que el flujo de proceso de negocio. Para informar sobre el flujo de proceso de negocio, seleccione la entidad correspondiente al flujo de proceso de negocio sobre el que desea informar y, luego, cree vistas y gráficos, como hacía antes.

En nuestro ejemplo, siga estos pasos para ir a la entidad **Proceso de cliente potencial a ventas de la oportunidad**:
1. Vaya a [https://make.powerapps.com](https://make.powerapps.com).
1. Seleccione los **datos**.
1. Seleccione las **entidades**.
1. Establezca el filtro en **Todo**.
1. Busque la entidad **Proceso de cliente potencial a ventas de la oportunidad** y selecciónela.

   ![entidad de proceso de cliente potencial a ventas de la oportunidad](media/best-practices-entity-attributes/lead-opportunity-process.png)

Aquí, puede definir vistas y gráficos del mismo modo que en cualquier otra entidad.

![detalles de la entidad del proceso de traducción](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

Una ventaja de este enfoque es que puede usar una vista o un gráfico para informar sobre los flujos de proceso de negocio que abarcan varias entidades.

Además, como la entidad de flujo de proceso de negocio no es diferente a ninguna otra entidad personalizada de Common Data Service, puede agregarle campos personalizados para realizar el seguimiento de la información adicional que necesite.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Opción 2: copia de la fase activa en una entidad relacionada

Como alternativa, para continuar informando de la entidad relacionada, cree un flujo para copiar el campo *Fase activa* (activestageid) de la entidad de flujo de proceso de negocio en un campo personalizado de las entidades de Common Data Service relacionadas.

Estos son algunos aspectos que hay que tener en cuenta al usar este enfoque:

1.  Es posible tener más de un flujo de proceso de negocio en ejecución en una sola entidad. Con este enfoque, es mejor tener un campo personalizado que almacene la fase activa de cada flujo de proceso de negocio que se ejecute en la entidad. Este enfoque garantiza la integridad del informe.

1.  Como los informes se generan desde la entidad relacionada, no es posible crear una vista única que informe sobre los flujos de proceso de negocio que abarquen varias entidades.

## <a name="using-the-active-stage-to-run-logic"></a>Uso de la fase activa para ejecutar la lógica

Estos son algunos casos en los que podría interesarle ejecutar la lógica que se basa en la fase activa:

### <a name="using-the-active-stage-to-run-client-side-logic"></a>Uso de la fase activa para ejecutar la lógica del lado cliente

A medida que se usa el proceso de negocio, son muchas las cosas que podría interesarle hacer automáticamente. Por ejemplo:

-   Cambiar el flujo de proceso de negocio activo en función de la información recién disponible en el formulario o el flujo de proceso de negocio.

-   Mover la fase activa a la fase siguiente o anterior, en función de los valores que los usuarios especificaron para los pasos o los campos del formulario.

-   Ocultar o mostrar pestañas y campos del formulario en función de la fase seleccionada.

-   Mostrar mensajes informativos y ejecutar cálculos según los flujos de proceso de negocio activos, la fase activa o seleccionada o eventos como mover la fase activa.

> [!TIP]
> En escenarios como estos, use el conjunto admitido de [API de cliente](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) para los flujos de proceso de negocio.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>Uso de la fase activa para ejecutar la lógica del lado servidor

Puede haber casos en los que la automatización basada en el flujo de proceso de negocio se deba realizar en el lado del servidor. Por ejemplo:

-   Enviar un correo electrónico a un usuario si la fase **Calificar** del **Proceso de ventas de la oportunidad** está activa durante más de 15 días.

-   Crear automáticamente un conjunto de actividades pertinentes para la fase activa del **Proceso de ventas de la oportunidad** cada vez que cambia.

-   Finalizar automáticamente el **Proceso de ventas de la oportunidad** cuando se complete la actividad de llamada telefónica de cierre.

> [!TIP]
> Use los flujos de trabajo clásicos de Common Data Service o los flujos que defina en la entidad en el flujo de proceso de negocio.
> 

Para compilar un flujo de trabajo clásico de Common Data Service que cree actividades para revisiones de soluciones internas y para realizar un seguimiento con el cliente en la fase **Proponer** de **Proceso de ventas de la oportunidad**, siga estos pasos:

1. Créelo en la entidad **Proceso de ventas de la oportunidad** y establézcalo para que se ejecute cada vez que cambia el campo **Fase activa** de la entidad. 
1. Defina una condición para comprobar si el campo **Fase activa** es igual a **Proponer**. 
1. Cree un registro de citas y de llamadas telefónicas para la revisión interna de la solución y para la llamada del cliente que se va a revisar, respectivamente.

   ![seguimiento de la fase de cierre](media/best-practices-entity-attributes/close-stage-followup.png)
