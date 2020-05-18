---
title: Crear un flujo de tareas móviles con Power Apps | MicrosoftDocs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 72a4e33dafd7c2237799357cc993d9815dd36012
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297019"
---
# <a name="create-a-mobile-task-flow"></a>Creación de un flujo de tareas móvil


Diseñe un flujo en Dynamics 365 para teléfonos o tabletas en función de las tareas comunes que realicen los usuarios. Por ejemplo, si periódicamente tienen que realizar una serie de pasos de seguimiento después de las reuniones con los clientes, cree un flujo de tareas. Cuando los usuarios pulsan en la nueva tarea en su aplicación móvil, les guiará de principio a fin de modo que no olviden un paso importante.  
  
 Los flujos de tareas pueden usar formularios y lógica de varias entidades, y pueden tener lógica de formulario que se ejecute en todas las páginas del flujo de tareas.  
  
## <a name="create-a-task-flow"></a>Creación de un flujo de tareas
  
1. Asegúrese de que tiene el rol de seguridad Administrador del sistema o Personalizador del sistema, o permisos equivalentes. El director, vicepresidente o director ejecutivo (CEO) y los roles de seguridad también pueden crear flujos de tareas móviles. 
  
2. Abra el [Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) y haga clic en **Procesos**.  
  
3.  En la barra de herramientas **Acciones**, seleccione **Nueva**.  
  
4.  En el cuadro de diálogo **Crear proceso**, complete los campos obligatorios:  
  
    -   Escriba un nombre del proceso.  
  
    -   En la lista **Categoría**, seleccione **Flujo de proceso de negocio**.  
  
    -   En la lista **Entidad**, seleccione la entidad que desee.  
  
5.  Haga clic en la opción **Ejecutar proceso como un flujo de tareas (solo móvil)**.  
  
6.  Seleccione **Aceptar**.
  
     El Diseñador de flujo de tareas se abrirá en una nueva ventana.  
  
     ![Ventana del diseñador de flujos de tareas](media/task-flow-designer-window.png "Ventana del diseñador de flujos de tareas") 
  
7.  Si los usuarios progresan desde una página a otra en orden, arrastre el componente **Página** desde la pestaña **Componentes** a la derecha de la pantalla y colóquelo en el signo + en el punto adecuado. Para agregar un nombre para una página, seleccione la página, seleccione la pestaña **Propiedades**, escriba un nuevo nombre y, luego, seleccione **Aplicar**.  
  
8.  Para agregar una rama al flujo de tarea, arrastre el componente **Condición** desde la pestaña **Componentes** y colóquelo en el signo + en el punto adecuado. Para establecer las propiedades para la condición, seleccione la condición, establezca las propiedades en la pestaña **Propiedades** y después seleccione **Aplicar**.  
  
    > [!NOTE]
    >  Cuando agregue páginas y condiciones al flujo de tareas, verá un minimapa en la esquina inferior izquierda de la ventana que muestra todas las páginas y condiciones del flujo de tareas.  
  
9. Para agregar un campo, etiqueta, o etiqueta de sección a una página, arrastre **Campo**, **Etiqueta**o **Etiqueta de sección** desde la pestaña **Componentes** a la página adecuada. Para cambiar las propiedades de uno de estos elementos, seleccione el elemento, establezca las propiedades en la pestaña **Propiedades** y después seleccione **Aplicar**.  
  
10. Para validar el flujo de tareas, seleccione **Validar** en la barra de acciones.  
  
11. Para guardar el proceso como borrador, seleccione **Guardar** en la parte superior de la pantalla. (Mientras un proceso sea borrador no se podrá usar.)  
  
12. Para activar el flujo de tareas para que pueda usarse, seleccione **Activar**.  
  
> [!TIP]
>  A continuación se proporcionan algunas sugerencias a tener presentes mientras trabaja en el flujo de tareas en la ventana del diseñador:  
>   
> -  Para realizar una instantánea de todo en la ventana de flujo de tareas, seleccione **Instantánea** en la barra de acciones.  
> -  Para conectar un componente válido a otro componente válido en el diseñador, seleccione **Conector** en la barra de acciones.  
> -  Puede crear las imágenes en la pantalla más grandes o más pequeñas seleccionando los botones **Aumentar el nivel de zoom** o **Disminuye el nivel de zoom** en la esquina superior derecha de la pantalla. Seleccione el botón **Ajustar al lienzo** para aumentar las imágenes hasta el tamaño mayor que se ajuste a la pantalla.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Crear un flujo de proceso de negocio](create-business-process-flow.md)   

