---
title: Grupos de datos para Power Automate | Microsoft Docs
description: Introducción a los grupos de datos para Microsoft Power Apps y Power Automate.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/26/2016
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: ca3271f7c61c6835c856bc363f64882802f1556f
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298185"
---
# <a name="learn-all-about-data-groups"></a>Toda la información acerca de los grupos de datos

## <a name="what-is-a-data-group"></a>¿Qué es un grupo de datos?
Los grupos de datos son una forma sencilla para clasificar servicios dentro de una [directiva de prevención de pérdida de datos (DLP)](prevent-data-loss.md). Los dos grupos de datos disponibles son el grupo **Solo datos profesionales** y el grupo **No se permiten datos profesionales** . Las organizaciones pueden determinar libremente qué servicios se colocan en un grupo de datos determinado. Una buena forma de clasificar los servicios es colocarlos en grupos en función del impacto en la organización. De forma predeterminada, todos los servicios están colocados en el grupo de datos **No se permiten datos profesionales**. Usted administra los servicios a un grupo de datos al crear o modificar las propiedades de una directiva DLP del centro de administración.

## <a name="how-data-is-shared-between-data-groups"></a>¿Cómo se comparten los datos entre grupos de usuarios?
Los datos no se pueden compartir entre los servicios que se encuentran en distintos grupos. Por ejemplo, si incluye SharePoint y Salesforce en el grupo **Solo datos profesionales** y Facebook y Twitter en el grupo **No se permiten datos empresariales**, no se podrá crear un flujo que transfiera datos entre SharePoint y Facebook. Aunque no se pueden compartir datos entre servicios de diferentes grupos, puede compartirlos entre los servicios de un grupo concreto. De este modo, si retomamos el ejemplo anterior, dado que SharePoint y Salesforce estaban incluidos en el mismo grupo de datos, los flujos que creen los usuarios finales podrán compartir datos entre estos dos servicios. Asimismo, los usuarios finales podrán crear flujos y Power Apps que compartan datos entre Facebook y Twitter. El punto clave es que los servicios de un grupo específico pueden compartir datos, mientras que los de grupos diferentes no pueden hacerlo.  

Además, debe designarse un grupo de datos como el grupo *predeterminado*. Inicialmente, el grupo **No se permiten datos empresariales** es el grupo *predeterminado* y todos los servicios se encuentran en el grupo de datos. Un administrador puede cambiar el grupo de datos predeterminado al grupo de datos **solo datos empresariales**. **Nota**: todos los nuevos servicios que se añadan a un flujo se incluirán en el grupo *predeterminado* designado. Por este motivo, le recomendamos que mantenga **No se permite datos profesionales** como el grupo predeterminado y que agregue manualmente servicios al grupo **Solo datos profesionales** después de que su organización haya evaluado el impacto de permitir que los datos profesionales se compartan con el nuevo servicio.

## <a name="add-services-to-a-data-group"></a>Agregar servicios a un grupo de datos
En este tutorial, agregaremos SharePoint y Salesforce al grupo de datos **Solo datos profesionales** de una directiva prevención de pérdida de datos (DLP). 

1. Seleccione el vínculo **+ Agregar** que se encuentra dentro del cuadro de grupo **Solo datos profesionales** de una directiva de DLP:    
   ![Agregar imagen](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Seleccione SharePoint y Salesforce y, a continuación, seleccione **Agregar servicios** para agregar ambos al grupo de solo datos profesionales:    
   ![Agregar imagen de servicios](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Seleccione **Guardar directiva** desde el menú de la parte superior:  
   ![Guardar directiva](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Tenga en cuenta que SharePoint y Salesforce ahora están en el grupo de solo datos profesionales:  
   ![grupo de datos profesionales actualizado](./media/introduction-to-data-groups/add-to-data-group-3.png)   

En este tutorial, ha agregado SharePoint y Salesforce al grupo de datos **Solo datos profesionales** de una directiva de DLP. Si una persona que forme parte del entorno de la directiva de prevención de pérdida de datos crea una aplicación que comparta datos entre SharePoint o Salesforce y cualquier servicio del grupo de datos **Sin datos profesionales**, la aplicación no se podrá ejecutar.

## <a name="remove-services-from-a-data-group"></a>Quitar servicios de un grupo de datos
Puesto que todos los servicios deben estar en uno de los grupos de datos disponibles, para quitar un servicio de un grupo determinado, simplemente agregue el servicio a otro grupo y luego guarde la directiva.  

## <a name="change-the-default-data-group"></a>Cambiar el grupo de datos predeterminado
En este tutorial, cambiaremos el grupo de datos predeterminado del grupo de datos **No se permiten datos profesionales** al grupo de datos **Solo datos profesionales**.  

**Importante**: todos los nuevos servicios que se añadan a un flujo se incluirán en el grupo *predeterminado* designado. Por este motivo, le recomendamos que mantenga **No se permiten datos profesionales** como el grupo predeterminado y que agregue manualmente servicios al grupo **Solo datos profesionales**.

1. Seleccione **...** que se encuentra en la esquina superior derecha del grupo de datos que desee designar como el grupo de datos predeterminado:    
   ![cambiar grupo predeterminado](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Seleccione **Establecer como grupo predeterminado**:  
   ![cambiar grupo predeterminado](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Seleccione **Guardar directiva** desde el menú de la parte superior:  
   ![cambiar grupo predeterminado](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Tenga en cuenta que el grupo de datos ahora está designado como el grupo de datos predeterminado:  
   ![cambiar grupo predeterminado](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Pasos siguientes
* [Más información sobre las directivas de prevención de pérdida de datos (DLP)](prevent-data-loss.md)
* [Más información acerca de los entornos](environments-overview-admin.md)   

