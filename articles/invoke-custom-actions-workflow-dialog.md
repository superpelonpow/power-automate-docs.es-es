---
title: Invocación de acciones personalizadas desde un flujo de trabajo | Microsoft Docs
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
ms.openlocfilehash: 15cbfdf61a25287714f0244639ec4a3246bd845c
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74355435"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Invocación de acciones personalizadas desde un flujo de trabajo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Los flujos de trabajo tienen numerosas funciones que admiten escenarios empresariales. Llamar a acciones básicas de operaciones de datos para un registro, como crear, actualizar y eliminar, desde un flujo de trabajo resuelve bastante escenarios empresariales. Pero si se combinan las funciones de los flujos de trabajo con la eficacia de las acciones personalizadas que se invocan directamente desde dentro de un flujo de trabajo, se agrega una gama de escenarios empresariales completamente nueva para la aplicación sin necesidad de escribir código.  
  
 Veamos el escenario en el que se invoca una acción personalizada desde un flujo de trabajo. Se invocará una acción personalizada para solicitar la aprobación del administrador cuando el descuento para una oportunidad concreta supere el 20 %.  
  
<a name="action"></a>   
## <a name="example-create-a-custom-action-using-the-opportunity-entity"></a>Ejemplo: Creación de una acción personalizada mediante la entidad de oportunidad
  
1. En el [Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) haga clic en **Procesos**.  
  
2.  En la barra de navegación, haga clic en **Nuevo**. Asigne un nombre al proceso y elija la categoría **Acción**.  
  
 Para solicitar una aprobación para el descuento, se va a usar una acción personalizada denominada **Proceso de aprobación**. Se ha agregado un parámetro de entrada, **SpecialNotes** y un paso **Enviar correo electrónico** para crear un mensaje y enviar una solicitud de aprobación del administrador, como se muestra aquí.  
  
 ![Adición de un paso &#45; enviar correo electrónico](media/enable-custom-action-approval-proces-sadd-email.png "Adición de un paso: enviar correo electrónico")  
  
 Para configurar el mensaje de correo electrónico, haga clic en **Establecer propiedades**. Cuando se abra el formulario, use el **Asistente de formulario** para agregar notas especiales y otra información al correo electrónico, como se resalta en la captura de pantalla. Para agregar las notas especiales, coloque el cursor donde quiera que aparezcan en el mensaje y, después, en el **Asistente de formulario**, en **Buscar**, seleccione **Argumentos** en la primera lista desplegable, **SpecialNotes** en la segunda y, después, haga clic en **Aceptar**.  
  
 ![Configuración del correo electrónico](media/enable-custom-action-approval-process-setup-email.png "Configuración del correo electrónico")  
  
 Antes de poder invocar la acción desde un flujo de trabajo, tendrá que activarla. Después de activar la acción, puede ver sus propiedades si hace clic en **Ver propiedades**.  
  
 ![Activar acción personalizada &#45; proceso de aprobación](media/enable-custom-action-approval-process-activate-action.png "Activar acción personalizada: proceso de aprobación")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Invocación de una acción personalizada desde un flujo de trabajo  
  
1. En el [Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) haga clic en **Procesos**.   
  
2.  En la barra de navegación, haga clic en **Nuevo**. Asigne un nombre al proceso y elija la categoría **Flujo de trabajo**.  
  
 Se crea un flujo de trabajo que invoca la acción personalizada **Proceso de aprobación** cuando se requiera la aprobación del administrador para obtener un descuento superior al 20 % para una oportunidad.  
  
 ![Establecimiento de propiedades de acción desde el flujo de trabajo](media/enable-custom-action-from-workflow.png "Establecimiento de propiedades de acción desde el flujo de trabajo")  
  
 Puede establecer las propiedades de entrada de la acción si hace clic en **Establecer propiedades**. En las notas especiales se ha agregado el nombre de la cuenta relacionada con la oportunidad. En el **Asistente de formulario**, en **Buscar**, seleccione **Cuenta** en la primera lista desplegable, elija **Nombre de cuenta** en la segunda y, después, haga clic en **Aceptar**. La propiedad **Destino** es necesaria y la rellena el sistema. La **{Oportunidad(Oportunidad)}** de la propiedad **Destino** es la misma oportunidad en la que se ejecuta el flujo de trabajo que realiza la llamada. Como alternativa, puede usar la búsqueda para seleccionar una oportunidad específica para la propiedad de destino.  
  
 ![Establecer parámetros de entrada para la acción ApprovalProcess](media/enable-customaction-workflow-set-properties.png "Establecer parámetros de entrada para la acción ApprovalProcess")  
  



