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
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195621"
---
# <a name="learn-all-about-data-groups"></a>Aprender todo sobre los grupos de datos

## <a name="what-is-a-data-group"></a>¿Qué es un grupo de datos?
Los grupos de datos son una manera sencilla de clasificar servicios dentro de una [directiva de prevención de pérdida de datos (DLP)](prevent-data-loss.md). Los dos grupos de datos disponibles son el grupo **Business data only** (Solo datos profesionales) y el grupo **No business data allowed** (Sin datos profesionales). Las organizaciones pueden determinar libremente qué servicios se colocan en un grupo de datos determinado. Una buena manera de clasificar servicios es colocarlos en grupos, según el impacto sobre la organización. De forma predeterminada, todos los servicios se colocan en el grupo de datos **No business data allowed** (No se permiten datos empresariales). Los servicios de un grupo de datos se administran al crear o modificar las propiedades de una directiva de prevención de pérdida de datos desde el centro de administración.

## <a name="how-data-is-shared-between-data-groups"></a>Cómo se comparten los datos entre grupos de datos
No es posible compartir datos entre servicios ubicados en grupos distintos. Por ejemplo, si incluye SharePoint y Salesforce en el grupo **Business data only** (Solo datos profesionales) y Facebook y Twitter en el grupo **No business data allowed** (Sin datos profesionales), no se podrá crear un flujo que transfiera datos entre SharePoint y Facebook. Si bien no se pueden compartir datos entre servicios de distintos grupos, sí es posible compartir datos entre los servicios de un mismo grupo. De este modo, si retomamos el ejemplo anterior, dado que SharePoint y Salesforce estaban incluidos en el mismo grupo de datos, los flujos que creen los usuarios finales podrán compartir datos entre estos dos servicios. Asimismo, los usuarios finales pueden crear flujos y Power Apps que compartan datos entre Facebook y Twitter. El punto clave es que los servicios de un grupo específico pueden compartir datos, mientras que los de grupos diferentes no pueden hacerlo.  

Además, se debe designar un grupo de datos como *predeterminado*. En principio, el grupo **No business data allowed** (Sin datos profesionales) es el *predeterminado* y todos los servicios se encuentran en ese grupo de datos. Un administrador puede cambiar el grupo de datos predeterminado a **Business data only** (Solo datos profesionales). **Nota**: todos los nuevos servicios que se añadan a un flujo se incluirán en el grupo *predeterminado* designado. Por este motivo, se recomienda que mantenga el grupo **No business data allowed** (Sin datos profesionales) como predeterminado y que añada manualmente servicios al grupo **Business data only** (Solo datos profesionales) después de que su organización haya evaluado el impacto de permitir que se compartan datos profesionales con el nuevo servicio.

## <a name="add-services-to-a-data-group"></a>Añadir servicios a un grupo de datos
En este tutorial, añadiremos SharePoint y Salesforce al grupo de datos **Business data only** (Solo datos profesionales) de una directiva de prevención de pérdida de datos. 

1. Seleccione el vínculo **+ Agregar** que se encuentra dentro del cuadro del grupo **Business data only** (Solo datos profesionales) de una directiva de prevención de pérdida de datos:    
   ![Imagen de Agregar](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Seleccione SharePoint y Salesforce y, a continuación, elija **Agregar servicios** para añadirlos al grupo Business data only (Solo datos profesionales):    
   ![Imagen de Agregar servicios](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Seleccione **Guardar directiva** en el menú de la parte superior:  
   ![Guardar directiva](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Observe que tanto SharePoint como Salesforce están ahora en el grupo Business data only (Solo datos profesionales):  
   ![grupo de datos empresariales actualizado](./media/introduction-to-data-groups/add-to-data-group-3.png)   

En este tutorial, ha añadido SharePoint y Salesforce al grupo de datos **Business data only** (Solo datos profesionales) de una directiva de prevención de pérdida de datos. Si una persona que forme parte del entorno de la directiva de prevención de pérdida de datos crea una aplicación que comparta datos entre SharePoint o Salesforce y cualquier servicio del grupo de datos **No business data allowed** (Sin datos profesionales), la aplicación no se podrá ejecutar.

## <a name="remove-services-from-a-data-group"></a>Eliminación de servicios de un grupo de datos
Puesto que todos los servicios deben estar en uno de los grupos de datos disponibles, para quitar un servicio de un grupo concreto, basta con añadir el servicio a otro grupo y, a continuación, guardar la directiva.  

## <a name="change-the-default-data-group"></a>Cambio del grupo de datos predeterminado
En este tutorial, se cambiará el grupo de datos predeterminado de **Sin datos profesiones** a **Business data only** (Solo datos profesionales).  

**Importante**: todos los nuevos servicios que se añadan a un flujo se incluirán en el grupo *predeterminado* designado. Por este motivo, se recomienda que mantenga el grupo **No business data allowed** (Sin datos profesionales) como predeterminado y que añada manualmente servicios al grupo **Business data only** (Solo datos profesionales).

1. Seleccione el botón **...** situado en la esquina superior derecha del grupo de datos que desee designar como predeterminado:    
   ![cambiar de grupo predeterminado](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Seleccione **Establecer como grupo predefinido**:  
   ![cambiar de grupo predeterminado](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Seleccione **Guardar directiva** en el menú de la parte superior:  
   ![cambiar el grupo predeterminado](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Observe que el grupo de datos ahora está designado como predeterminado:  
   ![cambiar el grupo predeterminado](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Pasos siguientes
* [Más información acerca de las directivas de prevención de pérdida de datos](prevent-data-loss.md)
* [Más información acerca de los entornos](environments-overview-admin.md)   

