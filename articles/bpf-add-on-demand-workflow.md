---
title: Adición de un flujo de trabajo a petición a un flujo de proceso de negocio
description: ''
author: MSFTMAN
ms.author: Deonhe
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
ms.service: flow
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: 26c79c20-2987-476e-983a-406e0db13034
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: bb8ca7efb83a863f3031dd18d0d9bd67ae3c5c07
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297129"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>Adición de un flujo de trabajo a petición a un flujo de proceso de negocio


Puede desencadenar flujos de trabajo a petición desde dentro de un flujo de proceso de negocio. Por ejemplo, puede agregar un flujo de trabajo a petición a un flujo de proceso de negocio para que se cree una actividad, como una tarea o un correo electrónico, siempre que se complete una fase. 

Un flujo de trabajo se activa en función de la ubicación donde se coloque en el diseñador de flujos de proceso de negocio.
- Procesos de fase a petición. Cuando el flujo de trabajo se coloca en una fase de flujo de proceso de negocio, el flujo de trabajo se desencadena al entrar o salir de la fase. 
- Procesos globales a petición. Cuando el flujo de trabajo se coloca en el área **Flujos de trabajo globales**, se desencadena al activar o archivar el proceso (cuando el estado cambia a aplicado, finalizado, reactivado o abandonado). 

Tenga en cuenta los requisitos siguientes al agregar un flujo de trabajo a un flujo de proceso de negocio.
- Para los flujos de trabajo que se agregan a una fase: solo se pueden usar flujos de trabajo activos a petición creados para la misma entidad de la fase donde se agrega el flujo de trabajo.  
- Para los flujos de trabajo globales: solo se pueden usar flujos de trabajo activos y a petición creados para la entidad primaria del flujo de proceso de negocio.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>Adición de un flujo de trabajo a petición a una fase de flujo de proceso de negocio

Para agregar un flujo de trabajo a petición desde el Diseñador de flujos de proceso de negocio, arrastre el componente de flujo de trabajo a una fase del proceso o a la sección de flujos de trabajo globales. 

En el sitio de [PowerApps](https://make.powerapps.com) seleccione **Controlado por modelos** (parte inferior izquierda del panel de navegación). 

Abra el Diseñador de flujos de proceso de negocio. Puede hacerlo de dos maneras.
- Si el flujo de proceso de negocio ya se ha agregado a una aplicación, vaya a **Aplicaciones**, haga clic en **...** al lado de la aplicación que quiera seleccionar y después seleccione **Editar**. En el Diseñador de aplicaciones, seleccione el flujo de proceso de negocio y luego haga clic en ![Abrir el Diseñador de flujos de proceso de negocio](media/dynamics365-open-designer.PNG).  
- En caso contrario, abra el [Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer), haga clic en **Procesos** en el panel de navegación de la izquierda y, después, seleccione el flujo de proceso de negocio que quiera. 

Decida si quiere que el flujo de trabajo a petición se desencadene mediante uno de los siguientes eventos de flujo de proceso de negocio. 
- Procesos de fase a petición. Desencadena el flujo de trabajo al entrar o salir de la fase. 
- Procesos globales a petición. Desencadena el flujo de trabajo al activar o archivar el proceso (cuando el estado cambia a aplicado, finalizado, reactivado o abandonado). 

En el ejemplo siguiente, se agrega un flujo de trabajo a petición denominado **My on demand workflow** (Mi flujo de trabajo a petición) a la **Fase 1** del flujo de proceso de negocio. 

1. Expanda la fase 1 para mostrar la sección **Proceso desencadenado**. 
2. Haga clic en la pestaña **Componentes** y arrastre **Flujo de trabajo** a la sección **Proceso desencadenado**.
    ![Adición del flujo de trabajo a una fase](media/add-workflow-to-bpf-1.png) Como alternativa, puede arrastrar **Flujo de trabajo** a la sección **Flujos de trabajo globales**, lo que lo desencadena cuando se activa o se archiva el proceso.
 ![Adición del flujo de trabajo a la activación o archivado del proceso](media/add-workflow-to-bpf-global.png)
3. En el cuadro de búsqueda de la pestaña **Propiedades**, escriba y busque el nombre del flujo de trabajo a petición que quiera agregar a la fase de flujo de proceso de negocio y, después, haga clic en **Aplicar**.
    ![Escriba el nombre y haga clic en Aplicar](media/add-workflow-to-bpf-2.png)
4. En la pestaña **Propiedades**, bajo **Desencadenador** seleccione **Entrada de fase** o **Salida de fase**.  
    ![Selección del desencadenador de flujo de trabajo](media/workflow-trigger.png)
   
    Como alternativa, al colocar el flujo de trabajo en la sección **Flujos de trabajo globales**, las opciones de desencadenador son **Proceso aplicado**, **Proceso reactivado**, **Proceso abandonado** y **Proceso finalizado**.

5. Haga clic en **Actualizar** en la barra del diseñador de flujos de proceso de negocio.
 
## <a name="next-steps"></a>Pasos siguientes
[Uso de procesos de flujo de trabajo para automatizar los procesos que no requieren interacción del usuario](workflow-processes.md) <br/>
[Tutorial: Crear un flujo de proceso de negocio para estandarizar procesos](create-business-process-flow.md) <br/>
[Business process flow automation in Dynamics 365 (Automatización de flujos de proceso de negocios en Dynamics 365)](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
