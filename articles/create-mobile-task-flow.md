---
title: Creación de un flujo de tareas móvil con Power Apps | Microsoft Docs
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
ms.openlocfilehash: 22736d826c6e0448e3d1272aed1b3d4f78fdb23b
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74362082"
---
# <a name="create-a-mobile-task-flow"></a>Creación de un flujo de tareas móvil
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Diseñe un flujo en Dynamics 365 para teléfonos o tabletas en función de las tareas comunes que realicen los usuarios. Por ejemplo, si periódicamente tienen que realizar una serie de pasos de seguimiento después de las reuniones con los clientes, cree un flujo de tareas. Cuando los usuarios pulsen en la nueva tarea en su aplicación móvil, les guiará de principio a fin, para que no olviden un paso importante.  
  
 Los flujos de tareas pueden usar formularios y lógica de varias entidades, y pueden tener lógica de formulario que se ejecute en todas las páginas del flujo de tareas.  
  
## <a name="create-a-task-flow"></a>Creación de un flujo de tareas
  
1. Asegúrese de que tiene el rol de seguridad Administrador del sistema o Personalizador del sistema, o permisos equivalentes. El director, vicepresidente o director ejecutivo (CEO) y los roles de seguridad también pueden crear flujos de tareas móviles. 
  
2. Abra el [Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) y haga clic en **Procesos**.  
  
3.  En la barra de herramientas **Acciones**, haga clic en **Nuevo**.  
  
4.  En el cuadro de diálogo **Crear proceso**, rellene los campos obligatorios:  
  
    -   Escriba un nombre de proceso.  
  
    -   En la lista **Categoría**, seleccione **Flujo de proceso de negocio**.  
  
    -   En la lista **Entidad**, seleccione la entidad que quiera.  
  
5.  Haga clic en la opción **Ejecutar proceso como un flujo de tareas (solo móvil)** .  
  
6.  Seleccione **Aceptar**.
  
     El Diseñador de flujo de tareas se abrirá en una nueva ventana.  
  
     ![Ventana del diseñador de flujos de tareas](media/task-flow-designer-window.png "Ventana del diseñador de flujos de tareas") 
  
7.  Si los usuarios van a avanzar en orden desde una página a otra, arrastre el componente **Página** desde la pestaña **Componentes** en el lado derecho de la pantalla y colóquelo sobre el signo + en el lugar apropiado. Para agregar un nombre para una página, seleccione la página, haga clic en la pestaña **Propiedades**, escriba un nombre nuevo y, después, haga clic en **Aplicar**.  
  
8.  Para agregar una rama al flujo de tareas, arrastre el componente **Condición** desde la pestaña **Componentes** y colóquelo sobre el signo + en el lugar apropiado. Para establecer las propiedades de la condición, seleccione la condición, establezca las propiedades en la pestaña **Propiedades** y, después, haga clic en **Aplicar**.  
  
    > [!NOTE]
    >  A medida que agregue páginas y condiciones al flujo de tareas, verá un minimapa en la esquina inferior izquierda de la ventana en el que se muestran todas las páginas y condiciones del flujo de tareas.  
  
9. Para agregar un campo, una etiqueta o una etiqueta de sección a una página, arrastre **Campo**, **Etiqueta** o **Etiqueta de sección** desde la pestaña **Componentes** a la página correspondiente. Para cambiar las propiedades de uno de estos elementos, seleccione el elemento, establezca las propiedades en la pestaña **Propiedades** y, después, haga clic en **Aplicar**.  
  
10. Para validar el flujo de tareas, haga clic en **Validar** en la barra de acciones.  
  
11. Para guardar el proceso como un borrador, haga clic en **Guardar** en la parte superior de la pantalla. (Mientras un proceso sea un borrador, los demás usuarios no podrán usarlo).  
  
12. Para activar el flujo de tareas para que los usuarios lo puedan utilizar, haga clic en **Activar**.  
  
> [!TIP]
>  Estas son algunas sugerencias que debe tener en cuenta cuando trabaje con el flujo de tareas en la ventana del diseñador:  
>   
> -  Para realizar una instantánea de todo el contenido de la ventana del flujo de tareas, haga clic en **Instantánea** en la barra de acciones.  
> -  Para conectar un componente válido a otro componente válido en el diseñador, haga clic en **Conector** en la barra de acciones.  
> -  Puede ampliar o reducir las imágenes en la pantalla si hace clic en los botones **Aumentar el nivel de zoom** o **Disminuir el nivel de zoom** en la esquina superior derecha de la pantalla. Haga clic en el botón **Ajustar al lienzo** para ampliar las imágenes hasta el tamaño más grande que quepa en la pantalla.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Crear un flujo de proceso de negocio](create-business-process-flow.md)   

