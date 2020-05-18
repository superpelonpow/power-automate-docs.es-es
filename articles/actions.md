---
title: Uso de las acciones | Microsoft Docs
description: Con las acciones, puede realizar operaciones como Crear, Actualizar, Eliminar, Asignar o Realizar acción. Internamente, una acción crea un mensaje personalizado
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c165213949d72fa9e7aacbc28d076969677a8802
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296667"
---
# <a name="use-actions"></a>Uso de las acciones


Las acciones abren una gama de posibilidades para crear la lógica de negocios. Con las acciones, puede realizar operaciones como Crear, Actualizar, Eliminar, Asignar o Realizar acción. Internamente, una acción crea un mensaje personalizado. Los programadores hacen referencia a estas acciones como "mensajes". Cada uno de estos mensajes se basa en las acciones realizadas en un registro de entidad. Si el objetivo de un proceso es crear un registro y, a continuación, actualizarlo y asignarlo, hay tres pasos independientes. Cada paso está definido por las capacidades de la entidad, no necesariamente el proceso de negocio.  
  
Las acciones ofrecen la capacidad de definir un solo verbo (o mensaje) que corresponda a una operación que debe realizar para su negocio. Estos nuevos mensajes son impulsados por un proceso o comportamiento, a diferencia de lo que se puede hacer con una entidad. Los mensajes pueden corresponder a verbos como Escalar, Convertir, Programar, Enrutar o Aprobar, en función de lo que necesite. La adición de estos verbos ayuda a proporcionar un vocabulario más rico para que pueda definir con fluidez sus procesos de negocio. Puede aplicar este vocabulario más rico desde clientes o integraciones, en lugar de tener que escribir la acción dentro de los clientes. Esto también facilitar el proceso porque puede administrar y registrar el éxito o error de la acción completa como una sola unidad.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Mensajes configurables  
 Una vez que se define y se activa una acción, un programador puede usar el mensaje como un de los demás mensajes proporcionados por la plataforma. Sin embargo, una diferencia importante es que ahora un usuario que no sea programador puede aplicar cambios en el proceso a realizar al usar el mensaje. Puede configurar la acción para editar los pasos a medida que los procesos de negocio cambian. Ningún código personalizado que use el mensaje necesita cambiarse, ya que los argumentos de procesos no cambian.  
  
 Los procesos del flujo de trabajo y los complementos continúan proporcionando capacidades similares para definir la automatización. Los procesos de flujo de trabajo siguen ofreciendo la característica para que un usuario que no sea desarrollador aplique cambios. Pero la diferencia se encuentra en la composición de los procesos de negocio y en la forma en que un programador puede escribir su código. Una acción es un mensaje que funciona en el mismo nivel que cualquiera de los mensajes proporcionados por la plataforma. Los desarrolladores pueden registrar complementos para las acciones.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Mensajes globales 
 
 A diferencia de los procesos del flujo de trabajo de Common Data Service o los [complementos](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in), una acción no tiene que asociarse con una entidad específica. Puede definir acciones "globales" a las que se puede llamar de forma independiente.

## <a name="next-steps"></a>Pasos siguientes

[Creación de una acción personalizada](create-actions.md)  
  

