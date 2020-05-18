---
title: Crear la lógica de negocios personalizada con procesos con Power Apps | MicrosoftDocs
description: Obtenga información sobre los diferentes tipos de lógica de negocios que puede usar en su aplicación
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
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298119"
---
# <a name="create-custom-business-logic-through-processes"></a>Crear una lógica de negocios personalizada con procesos


Definir y forzar procesos de negocio coherentes es una de las principales razones por las que las personas utilizan aplicaciones basadas en modelos. Los procesos coherentes garantizan a los usuarios que usan el sistema que puedan concentrarse en su trabajo y no en recordar realizar un conjunto de pasos manuales. Los procesos pueden ser simples o complejos, y pueden cambiar con el tiempo.  
  
Power Apps incluye varios tipos de procesos, cada uno diseñado con un objetivo:  
  
-   Flujos de proceso de negocio  
  
-   Flujos de tareas móviles  
  
-   Flujos de trabajo  
  
-   Acciones  
  
 De manera similar a los procesos, también puede crear reglas de negocio y recomendaciones. Para obtener más información, vea [Crear reglas de negocio y recomendaciones para aplicar lógica en un formulario](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form).  

> [!NOTE]
>  El uso de procesos puede afectar los requisitos de licencia para Power Apps y los flujos. Para obtener más información, vea [Requisitos de licencia para entidades](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses). 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Cuándo usar flujos de proceso de negocio  
 Use un flujo de proceso de negocio cuando desee que el personal recorra las mismas fases y siga los mismos pasos para interactuar con un cliente. Por ejemplo, use un proceso de negocio si desea que todo el mundo administre las solicitudes de servicio al cliente de la misma forma, o para requerir que el personal obtenga aprobación para una factura antes de enviar un pedido.  
  
 En el entorno se incluyen varios flujos de proceso de negocio listos para usarse para tareas comunes de venta, servicio y marketing tareas que puede utilizar tal cual o sin apenas cambios. O bien, puede crear los suyos propios. Vea el tema siguiente para obtener más información sobre los flujos de proceso de negocio:  
  
-   [Crear un flujo de proceso de negocio](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Cuándo usar los flujos de trabajo  
 Puede usar los flujos de trabajo para automatizar los procesos de negocio en segundo plano. Los flujos de trabajo suelen ser eventos iniciados por el sistema, por lo que el usuario no tiene que ser consciente de que se están ejecutando. Los flujos de trabajo que trabajan en segundo plano son “asincrónicos.” Los flujos de trabajo también se pueden configurar para que las personas los inicien manualmente. cuando desee automatizar tareas comunes, como enviar automáticamente un correo electrónico de confirmación a un cliente cuando envía un pedido. Los flujos de trabajo que trabajan en tiempo real son “sincrónicos.” Para obtener más información acerca de flujos de trabajo, consulte [Procesos de flujo de trabajo](workflow-processes.md)  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Cuándo usar acciones  
 Use acciones cuando desee automatizar a una serie de comandos del sistema. Las acciones expanden el vocabulario disponible para que los desarrolladores expresen procesos de negocio. Los verbos básicos como crear, actualizar, eliminar y asignar que proporciona el sistema, una acción los utiliza para crear verbos más expresivos como aprobar, escalar, distribuir o programar. Si la definición de un proceso de negocio cambia, los usuarios que no son programadores pueden editar la acción para que el código no se tenga que cambiar.  Para obtener más información sobre las acciones, vea [Acciones](create-actions.md)  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-power-automate"></a>Cuándo usar Power Automate  
 Utilice Power Automate cuando necesite crear flujos de trabajo automatizados que realicen acciones entre su entorno y su aplicación o servicio de preferencia, como Dynamics 365, Twitter, Dropbox, los servicios de Google, Office 365 y SharePoint. Puede desencadenar un flujo en función de una acción específica, o bien invocarlo desde dentro de la aplicación. Más información: [Usar Microsoft Power Automate para automatizar procesos entre servicios](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>¿Dónde se crean los procesos?  
 Hay dos rutas de acceso para navegar a los procesos:  
  
- Abra [el Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) y vaya a **Componentes > Procesos.** Esta ruta de acceso proporciona un acceso cómodo cuando se realiza otro trabajo de personalización con las herramientas de personalización.  

- **[Configuración](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Procesos.** Esta ruta de acceso permite usar las vistas definidas para la entidad Proceso, incluidas las vistas personalizadas.  
  
 Los flujos individuales de proceso de negocio también se pueden editar con el botón **Editar proceso** en la barra de comandos para el formulario donde está activo el flujo de proceso de negocio.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>¿Quién puede crear procesos?  
 Solo los usuarios con el rol de seguridad Administrador del sistema, Personalizador del sistema o Director general pueden crear procesos que se apliquen a todo el entorno. Los usuarios con otros roles pueden crear procesos con nivel de acceso limitado. Por ejemplo, los usuarios con el nivel de acceso de usuario pueden crear flujos de trabajo para uso personal con registros de su propiedad.  
  
 La siguiente tabla muestra el nivel de acceso de procesos basados en roles de seguridad predeterminados.  
  
|||  
|-|-|  
|**Rol de seguridad**|**Nivel de acceso**|  
|Administrador general|Organización|  
|Administrador del sistema|Organización|  
|Personalizador del sistema|Organización|  
|Vicepresidente de marketing|Primario: unidades de negocio secundarias|  
|Vicepresidente de ventas|Primario: unidades de negocio secundarias|  
|Jefe del servicio de bicicletas de |Unidad de negocio|  
|Administrador de marketing|Unidad de negocio|  
|Administrador de ventas|Unidad de negocio|  
|Administrador de programación|Unidad de negocio|  
|Representante del servicio al cliente|Usuario|  
|Profesional de marketing|Usuario|  
|Comercial|Usuario|  
|Programador|Usuario|  
  
> [!NOTE]
>  Mientras que los usuarios pueden crear flujos de proceso de negocio, flujos de trabajo en tiempo real o procesos de acción, deberán tener los privilegios **Activar flujos de proceso de negocio** o **Activar procesos en tiempo real** para poder activarlos.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>Más sobre flujos de trabajo y acciones  
 Los procesos pueden comprobar condiciones, aplicar lógica de bifurcación y realizar acciones. Realizan estas acciones en una serie de pasos. La siguiente tabla describe los pasos disponibles en los procesos de flujo de trabajo y acción. Para obtener más detalles, consulte los temas para cada tipo de proceso.  
  
|Paso|Tipo de proceso|Descripción|  
|----------|------------------|-----------------|  
|**Fase**|Flujo de trabajo, acción|Las fases simplifican la lectura de la lógica del flujo de trabajo y la explican. Sin embargo, las fases no afectan a la lógica ni al comportamiento de los flujos de trabajo. Si un proceso tiene fases, todos los pasos del proceso deben estar incluidos en una fase.|  
|**Condición de comprobación**|Flujo de trabajo, acción|Una instrucción lógica "if-\<condition> then".<br /><br /> Puede comprobar los valores del registro en el que se ejecuta el flujo de trabajo, cualquiera de los registros vinculados a ese registro en una relación N:1 o cualquier registro creado por pasos anteriores. Según esos valores puede definir pasos adicionales cuando la condición se cumpla (cuando sea `true`).|  
|**Rama condicional**|Flujo de trabajo, acción|Una instrucción lógica de tipo "else-if-then", el editor utiliza el texto "De lo contrario, si \<condición> entonces:"<br /><br /> Seleccione una condición de comprobación que haya definido anteriormente y podrá agregar una rama condicional para definir pasos adicionales cuando la condición de comprobación devuelva `false`.|  
|**Acción predeterminada**|Flujo de trabajo, acción|Una instrucción lógica de tipo "else". el editor usa el texto "De lo contrario:"<br /><br /> Seleccione una condición de comprobación, rama condicional, condición de espera o rama de espera paralela que haya definido anteriormente y podrá usar una acción predeterminada para definir los pasos para todos los casos que no cumplan los criterios definidos en elementos de condición o de rama.|  
|**Condición de espera**|Flujo de trabajo en segundo plano solo|Habilita un flujo de trabajo en segundo plano para que se ponga en pausa hasta que se hayan cumplido los criterios definidos por la condición. El flujo de trabajo se vuelve a iniciar automáticamente cuando cumple los criterios en la condición de espera.|  
|**Rama de espera paralela**|Flujo de trabajo en segundo plano solo|Define una condición de espera alternativa para un flujo de trabajo en segundo plano con un conjunto correspondiente de pasos adicionales que se realizan solo cuando se cumple el criterio inicial. Puede usar ramas de espera paralelas para crear límites de tiempo en la lógica de flujo de trabajo. Ayudan a evitar que el flujo de trabajo espere indefinidamente hasta que se hayan cumplido los criterios definidos en una condición de espera.|  
|**Asignar valor**|Acción|Define un valor en una variable o un parámetro de salida del proceso.|  
|**Crear registro**|Flujo de trabajo, acción|Crea un nuevo registro para una entidad y asigna valores a los atributos.|  
|**Actualizar registro**|Flujo de trabajo, acción|Puede actualizar el registro en el que se ejecuta el flujo de trabajo, cualquiera de los registros vinculados a ese registro en una relación N:1 o cualquier registro creado por pasos anteriores.|  
|**Asignar registro**|Flujo de trabajo, acción|Puede asignar el registro en el que se ejecuta el flujo de trabajo, cualquiera de los registros vinculados a ese registro con una relación N:1 o cualquier registro creado por pasos anteriores.|  
|**Enviar correo**|Flujo de trabajo, acción|Envía un mensaje de correo electrónico. Puede elegir crear un nuevo mensaje de correo electrónico o usar una plantilla de correo electrónico configurada para la entidad de registro en la que se ejecuta el flujo de trabajo o cualquier entidad que tenga una relación N:1 con la entidad o la entidad de los registros creados por pasos anteriores.|  
|**Iniciar flujo de trabajo secundario**|Flujo de trabajo, acción|Inicia un proceso de flujo de trabajo que se ha configurado como un flujo de trabajo secundario.|  
|**Cambiar estado**|Flujo de trabajo, acción|Cambia el estado del registro en el que se ejecuta el proceso, cualquiera de los registros vinculados a ese registro con una relación N:1 o cualquier registro creado por pasos anteriores.|  
|**Detener flujo de trabajo**|Flujo de trabajo, acción|Detiene el flujo de trabajo o la acción actuales. Puede establecer un estado **Correcto** o **Cancelado** y especificar un mensaje de estado.|  
|**Paso personalizado**|Flujo de trabajo, acción|Proporciona extensiones a los elementos lógicos disponibles de forma predeterminada. Los pasos pueden incluir condiciones, acciones, otros pasos o una combinación de estos elementos. Los desarrolladores pueden crear pasos de flujo de trabajo personalizados. De forma predeterminada, no hay ningún paso personalizado disponible.|

  

