---
title: Creación de lógica de negocios personalizada mediante procesos con Power Apps | Microsoft Docs
description: Obtenga información sobre los distintos tipos de lógica de negocios que puede usar en la aplicación.
ms.custom: ''
ms.date: 05/01/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: 0b4e6602-5701-4859-81cc-6f6fe50901b2
caps.latest.revision: 44
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: af51cc703dbb42296493237bdd25387c6c15720c
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194747"
---
# <a name="create-custom-business-logic-through-processes"></a>Creación de lógica de negocios personalizada mediante procesos


La definición y aplicación de procesos de negocio coherentes es uno de los principales motivos por el que los usuarios utilizan aplicaciones basadas en modelos. Los procesos coherentes ayudan a asegurarse de que los usuarios del sistema se puedan centrar en su trabajo y no en recordar realizar un conjunto de pasos manuales. Los procesos pueden ser simples o complejos, y cambian con el tiempo.  
  
Power Apps incluye varios tipos de procesos, cada uno diseñado para un propósito diferente:  
  
-   Flujos de proceso de negocio  
  
-   Flujos de tarea móvil  
  
-   Flujos de trabajo  
  
-   Acciones  
  
 Al igual que los procesos, también se pueden crear reglas de negocio y recomendaciones. Para obtener más información, vea [Crear reglas de negocio y recomendaciones para aplicar lógica en un formulario](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form).  

> [!NOTE]
>  El uso de procesos puede afectar a los requisitos de licencia para Power Apps y los flujos. Para obtener más información, vea [Requisitos de licencia para entidades](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses). 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Cuándo usar los flujos de proceso de negocio  
 Puede usar un flujo de proceso de negocio cuando quiera que el personal se desplace por las mismas fases y siga los mismos pasos para interactuar con un cliente. Por ejemplo, puede usar un flujo de proceso de negocio si quiere que todos los usuarios controlen las solicitudes de servicio de cliente del mismo modo, o bien para requerir que el personal obtenga la aprobación de una factura antes de enviar un pedido.  
  
 En el entorno se incluyen varios flujos de proceso de negocio listos para usarse para tareas comunes de venta, servicio y marketing tareas que puede utilizar tal cual o sin apenas cambios. O bien, puede crear los suyos propios. Vea el tema siguiente para obtener más información sobre los flujos de proceso de negocio:  
  
-   [Crear un flujo de proceso de negocio](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Cuándo usar los flujos de trabajo  
 Puede usar los flujos de trabajo para automatizar los procesos de negocio en segundo plano. Los flujos de trabajo se inician normalmente mediante eventos del sistema para que el usuario no tenga que ser consciente de que se están ejecutando. Los flujos de trabajo que funcionan en segundo plano son "asincrónicos". Los flujos de trabajo también se pueden configurar para que los usuarios los inicien de forma manual, si quiere automatizar tareas comunes, como el envío automático de un correo electrónico de confirmación a un cliente cuando se envíe un pedido. Los flujos de trabajo que funcionan en tiempo real son "sincrónicos". Para obtener más información sobre los flujos de trabajo, vea [Procesos de flujo de trabajo](workflow-processes.md).  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Cuándo usar las acciones  
 Puede usar las acciones cuando quiera automatizar una serie de comandos en el sistema. Las acciones expanden el vocabulario disponible para los desarrolladores para expresar los procesos de negocio. Una acción usa los verbos principales que proporciona el sistema, como Create (Crear), Update (Actualizar), Delete (Eliminar) y Assign (Asignar), para crear verbos más expresivos como Approve (Aprobar), Escalate (Escalar), Route (Enrutar) o Schedule (Programar). Si cambia la definición de un proceso de negocio, alguien que no sea un desarrollador puede modificar la acción para que no sea necesario cambiar el código.  Para obtener más información sobre las acciones, vea [Acciones](create-actions.md)  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-power-automate"></a>Cuándo usar Power Automate  
 Use Power Automate cuando tenga que crear flujos de trabajo automatizados que realicen acciones entre el entorno y su aplicación o servicio favorito, como Dynamics 365, Twitter, Dropbox, Google Services, Office 365 y SharePoint. Puede desencadenar un flujo en función de una acción específica, o bien invocarlo desde dentro de la aplicación. Más información: [Usar Power Automate para automatizar procesos entre servicios](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>¿Dónde se crean los procesos?  
 Hay dos rutas de acceso para navegar a los procesos:  
  
- Abra [el Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) y vaya a **Componentes > Procesos.** Esta ruta de acceso proporciona un acceso cómodo cuando se realiza otro trabajo de personalización con las herramientas de personalización.  

- **[Configuración](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Procesos.** Esta ruta de acceso permite usar las vistas definidas para la entidad Proceso, incluidas las vistas personalizadas.  
  
 Los flujos de proceso de negocio individuales también se pueden modificar con el botón **Editar proceso** de la barra de comandos del formulario en el que el flujo de proceso de negocio está activo.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>¿Quién puede crear procesos?  
 Solo los usuarios con el rol de seguridad Administrador del sistema, Personalizador del sistema o Director general pueden crear procesos que se apliquen a todo el entorno. Los usuarios con otros roles pueden crear procesos con nivel de acceso limitado. Por ejemplo, los usuarios con el nivel de acceso Usuario pueden crear flujos de trabajo para su propio uso con los registros que poseen.  
  
 En la tabla siguiente se muestra el nivel de acceso de los procesos en función de los roles de seguridad predeterminados.  
  
|||  
|-|-|  
|**Rol de seguridad**|**Nivel de acceso**|  
|Director general|Organización|  
|Administrador del sistema|Organización|  
|Personalizador del sistema|Organización|  
|Vicepresidente de Marketing|Elemento principal: unidades de negocio secundarias|  
|Vicepresidente de ventas|Elemento principal: unidades de negocio secundarias|  
|Administrador de servicios|Unidad de negocio|  
|Director de marketing|Unidad de negocio|  
|Jefe de ventas|Unidad de negocio|  
|Administrador de programación|Unidad de negocio|  
|Representante del servicio de atención al cliente|Usuario|  
|Profesional de marketing|Usuario|  
|Comercial|Usuario|  
|Programador|Usuario|  
  
> [!NOTE]
>  Aunque los usuarios puedan crear flujos de proceso de negocio, flujos de trabajo en tiempo real o procesos de acción, deberán tener los privilegios **Activar flujos de proceso de negocio** o **Activar procesos en tiempo real** para activarlos.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>Más información sobre los flujos de trabajos y las acciones  
 Los procesos pueden comprobar condiciones, aplicar la lógica de creación de ramas y realizar acciones. Realizan estas acciones en una serie de pasos. En la tabla siguiente se describen los pasos disponibles en los procesos de flujo de trabajo y acción. Para obtener más información, vea los temas de cada tipo de proceso.  
  
|Paso|Tipo de proceso|Descripción|  
|----------|------------------|-----------------|  
|**Fase**|Flujo de trabajo, acción|Las fases facilitan la lectura de la lógica de flujo de trabajo y la explican. Pero las fases no afectan a la lógica ni al comportamiento de los flujos de trabajo. Si un proceso tiene fases, todos los pasos del proceso se deben incluir en una fase.|  
|**Condición de comprobación**|Flujo de trabajo, acción|Una instrucción "si \<condición> entonces" lógica.<br /><br /> Puede comprobar los valores del registro en el que se ejecuta el flujo de trabajo, cualquiera de los registros vinculados a ese registro en una relación de varios a uno, o bien todos los registros creados por los pasos anteriores. En función de estos valores, puede definir pasos adicionales cuando la condición es `true`.|  
|**Rama condicional**|Flujo de trabajo, acción|Una instrucción "else-if-then" lógica, el editor usa el texto "De lo contrario, si \<condición> entonces:"<br /><br /> Seleccione una condición de comprobación que haya definido previamente y puede agregar una rama condicional para definir pasos adicionales cuando la condición de comprobación devuelve `false`.|  
|**Acción predeterminada**|Flujo de trabajo, acción|Una instrucción "else" lógica. El editor usa el texto "De lo contrario:"<br /><br /> Seleccione una condición de comprobación, una rama condicional, una condición de espera o una rama de espera paralela que haya definido previamente y puede usar una acción predeterminada para definir pasos para todos los casos que no coincidan con los criterios definidos en los elementos de la condición o la rama.|  
|**Condición de espera**|Solo para el flujo de trabajo en segundo plano|Permite que un flujo de trabajo en segundo plano se detenga hasta que se cumplan los criterios definidos por la condición. El flujo de trabajo se inicia de nuevo de forma automática cuando se han cumplido los criterios de la condición de espera.|  
|**Rama de espera paralela**|Solo para el flujo de trabajo en segundo plano|Define una condición de espera alternativa para un flujo de trabajo en segundo plano con un conjunto correspondiente de pasos adicionales que solo se ejecutan cuando se cumple el criterio inicial. Puede usar las ramas de espera paralelas para crear límites de tiempo en la lógica del flujo de trabajo. Ayudan a evitar que el flujo de trabajo espere de forma indefinida hasta que se cumplan los criterios definidos en una condición de espera.|  
|**Asignar valor**|Acción|Establece un valor en una variable o parámetro de salida en el proceso.|  
|**Crear registro**|Flujo de trabajo, acción|Crea un registro para una entidad y asigna valores a los atributos.|  
|**Actualizar registro**|Flujo de trabajo, acción|Puede actualizar el registro en el que se ejecuta el flujo de trabajo, cualquiera de los registros vinculados a ese registro en una relación de varios a uno, o bien todos los registros creados por los pasos anteriores.|  
|**Asignar registro**|Flujo de trabajo, acción|Puede asignar el registro en el que se ejecuta el flujo de trabajo, cualquiera de los registros vinculados a ese registro con una relación de varios a uno, o bien todos los registros creados por los pasos anteriores.|  
|**Enviar correo electrónico**|Flujo de trabajo, acción|Envía un correo electrónico. Puede elegir crear un mensaje de correo electrónico o usar una plantilla de correo electrónico configurada para la entidad del registro en el que se ejecuta el flujo de trabajo, todas las entidades que tienen una relación de varios a uno con la entidad, o bien la entidad para los registros creados por los pasos anteriores.|  
|**Iniciar flujo de trabajo secundario**|Flujo de trabajo, acción|Inicia un proceso de flujo de trabajo que se ha configurado como un flujo de trabajo secundario.|  
|**Cambiar estado**|Flujo de trabajo, acción|Cambia el estado del registro en el que se ejecuta el flujo de trabajo, cualquiera de los registros vinculados a ese registro con una relación de varios a uno, o bien todos los registros creados por los pasos anteriores.|  
|**Detener flujo de trabajo**|Flujo de trabajo, acción|Detiene el flujo de trabajo o la acción actual. Puede establecer un estado de **Correcto** o **Cancelado**, y especificar un mensaje de estado.|  
|**Paso personalizado**|Flujo de trabajo, acción|Proporciona extensiones para los elementos lógicos disponibles de forma predeterminada. Los pasos pueden incluir condiciones, acciones, otros pasos o una combinación de estos elementos. Los desarrolladores pueden crear pasos de flujo de trabajo personalizados. De forma predeterminada, no hay ningún paso personalizado disponible.|

  

