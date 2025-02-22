---
title: Invocar acciones personalizadas desde un flujo de trabajo | MicrosoftDocs
description: Obtenga información sobre cómo invocar una acción personalizada desde un flujo de trabajo
ms.custom: ''
ms.date: 11/22/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
author: Mattp123
ms.assetid: 1fd5d39e-3dc8-4d1a-8b4b-ccaa303f4bbb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a35523209e3db8444da71c0757db29fa21de08b3
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297921"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Invocar acciones personalizadas desde un flujo de trabajo


Los flujos de trabajo tienen numerosas funciones que admiten escenarios empresariales. Llamar a acciones básicas de operaciones de datos para un registro, como crear, actualizar y eliminar, desde un flujo de trabajo resuelve bastante escenarios empresariales. Sin embargo, si combina las funciones de los flujos de trabajo con la capacidad de las acciones personalizadas invocadas directamente desde un flujo de trabajo, agregará una serie nueva y completa de escenarios de negocio a la aplicación sin necesidad de escribir código.  
  
 Veamos el escenario en el que una acción personalizada se invoca desde un flujo de trabajo. Se invocará una acción personalizada para solicitar la aprobación del administrador cuando el descuento para una oportunidad concreta supere el 20 %.  
  
<a name="action"></a>   
## <a name="example-create-a-custom-action-using-the-opportunity-entity"></a>Ejemplo: Creación de una acción personalizada mediante la entidad de oportunidad
  
1. En el [Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) haga clic en **Procesos**.  
  
2.  En la barra de navegación, elija **Nuevo**. Asigne un nombre al proceso y seleccione la categoría **Acción**.  
  
 Para solicitar una aprobación para el descuento, estamos usando una acción personalizada llamada **Proceso de aprobación**. Hemos agregado un parámetro de entrada, **SpecialNotes**y un paso **Enviar correo electrónico** para crear un nuevo mensaje y enviar una solicitud de aprobación del administrador, como se indica aquí.  
  
 ![Adición de un paso: enviar correo electrónico](media/enable-custom-action-approval-proces-sadd-email.png "Adición de un paso: enviar correo electrónico")  
  
 Para configurar el correo electrónico, elija **Establecer propiedades**. Cuando se abre el formulario, use el **Asistente de formulario** para agregar notas especiales y otra información al correo electrónico, según se resalta en la captura de pantalla. Para agregar notas especiales, coloque el cursor donde desea que aparezcan en el mensaje y, a continuación, en el **Asistente de formulario**, en **Buscar**, seleccione **Argumentos** en la primera lista desplegable y elija **SpecialNotes** en la segunda lista desplegable, y después elija **Aceptar**.  
  
 ![Configurar el correo electrónico](media/enable-custom-action-approval-process-setup-email.png "Configurar el correo electrónico")  
  
 Antes de poder invocar la acción desde un flujo de trabajo, tendrá que activarla. Una vez que haya activado la acción, puede ver sus propiedades eligiendo **Ver propiedades**.  
  
 ![Activar acción personalizada: proceso de aprobación](media/enable-custom-action-approval-process-activate-action.png "Activar acción personalizada: proceso de aprobación")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Invocación de una acción personalizada desde un flujo de trabajo  
  
1. En el [Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) haga clic en **Procesos**.   
  
2.  En la barra de navegación, elija **Nuevo**. Asigne un nombre al proceso y seleccione la categoría **Flujo de trabajo**.  
  
 Hemos creado un flujo de trabajo que invoca la acción personalizada **Proceso de aprobación** cada vez que se requiere la aprobación del administrador para un descuento de más del 20% para una oportunidad.  
  
 ![Establecimiento de propiedades de acción desde el flujo de trabajo](media/enable-custom-action-from-workflow.png "Establecimiento de propiedades de acción desde el flujo de trabajo")  
  
 Puede establecer las propiedades de entrada de la acción eligiendo **Establecer propiedades**. Hemos agregado un nombre de la cuenta relacionada con las oportunidades en las notas especiales. En el **Asistente de formulario**, en **Buscar**, seleccione **Cuenta** en la primera lista desplegable, seleccione **Nombre de cuenta** en la segunda lista desplegable y, a continuación, elija **Aceptar**. La propiedad **Destino** es necesaria y la rellena el sistema. La **{Oportunidad(Opportunity)}** en la propiedad **Destino** es la misma oportunidad en la que se ejecuta el flujo de trabajo de llamada. Como alternativa, puede usar la búsqueda para seleccionar una oportunidad específica para la propiedad de destino.  
  
 ![Establecer parámetros de entrada para la acción ApprovalProcess](media/enable-customaction-workflow-set-properties.png "Establecer parámetros de entrada para la acción ApprovalProcess")  
  



