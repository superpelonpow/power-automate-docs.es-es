---
title: Información acerca de cómo agregar otros propietarios a un flujo y crear flujos de equipo | Microsoft Docs
description: Power Automate simplifica la automatización de tareas repetitivas. Puede agregar usuarios o grupos como propietarios y colaborar con ellos para diseñar y administrar los flujos.
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
ms.date: 04/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 697f41960a62c7da2eee9bc34bb174d39ed2c44b
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195082"
---
# <a name="create-team-flows"></a>Creación de flujos de equipo

Cree un flujo de equipo mediante la adición de otros usuarios de su organización como propietarios. Todos los propietarios de un flujo de equipo pueden realizar estas acciones:

* Ver el historial del flujo (es decir, todas las ejecuciones).
* Administrar las propiedades del flujo (por ejemplo, parar iniciar o detener el flujo, agregar propietarios o actualizar las credenciales de una conexión).
* Editar la definición del flujo (por ejemplo, para agregar o quitar una acción o condición).
* Agregar y quitar otros propietarios (pero no el creador del flujo).
* Eliminar el flujo.

Si es creador o propietario de un flujo de equipo, verá que aparece indicado en la pestaña **Flujos del equipo** de [Power Automate](https://flow.microsoft.com).

![pestaña flujos del equipo](./media/create-team-flows/addowner5.png)

> [!NOTE]
> Las conexiones compartidas **solo** se pueden usar en el flujo en el que se crearon.
> 
> 

Los propietarios pueden usar los servicios de un flujo, pero no modificar las credenciales de una conexión que haya creado otro propietario.

## <a name="prerequisites"></a>Requisitos previos
Para crear un flujo de equipo, debe tener un [plan de pago de Power Automate](https://flow.microsoft.com/pricing/). Además, debe ser el creador o el propietario para poder agregar o quitar propietarios de un flujo de equipo.

## <a name="create-a-team-flow"></a>Creación de un flujo de equipo
Siga estos pasos para crear un flujo de equipo o para agregar más propietarios a un flujo de equipo.

1. Inicie sesión en [Power Automate](https://flow.microsoft.com) y seleccione **Mis flujos**.
2. Seleccione el icono de personas del flujo que desea modificar:
   
    ![icono de equipo](./media/create-team-flows/addowner1.png)
3. Escriba el nombre, la dirección de correo electrónico o el nombre de grupo de la persona o grupo que desea agregar como propietario:
   
    ![buscar el usuario](./media/create-team-flows/addowner2.png)
4. En la lista que aparece, seleccione el usuario que desea que sea propietario:
   
    ![seleccionar el usuario](./media/create-team-flows/addowner3.png)
   
     El usuario o grupo que ha seleccionado se convierte en propietario del flujo:
   
    ![nuevo propietario](./media/create-team-flows/addowner4.png)
   
     Ya se ha creado el flujo del equipo.

## <a name="add-a-list-as-a-co-owner"></a>Agregar una lista como copropietario

Puede agregar listas de SharePoint como copropietario a un flujo para que todos los usuarios con acceso de edición a la lista obtengan automáticamente acceso de edición para el flujo. Una vez que se haya compartido el flujo, solo tendrá que distribuir un vínculo que dirija a este.

> [!TIP]
> Utilice una lista cuando el flujo está conectado a SharePoint, y un grupo en otros casos.
>

## <a name="remove-an-owner"></a>Eliminación de un propietario

> [!IMPORTANT]
> Al quitar un propietario cuyas credenciales se usan para acceder a los servicios de Power Automate, debe actualizar las credenciales de esas conexiones para que el flujo siga funcionando correctamente.
> 
> 

1. Seleccione el icono de personas del flujo que desea modificar:
   
    ![seleccionar icono de personas](./media/create-team-flows/removeowner1.png)
2. Seleccione el icono **Eliminar** del propietario que desea quitar:
   
    ![seleccionar Eliminar](./media/create-team-flows/removeowner2.png)
3. En el cuadro de diálogo de confirmación, seleccione **Quitar este propietario**:
   
    ![confirmar eliminación](./media/create-team-flows/removeowner3.png)
4. &mdash; El usuario o grupo que quitó ya no aparece como propietario del flujo:
   
    ![usuario eliminado](./media/create-team-flows/removeowner4.png)


## <a name="update-connection-owner"></a>Actualización del propietario de la conexión

Es posible que deba cambiar el propietario de una conexión en un flujo si quita el propietario existente. Siga estos pasos para cambiar el propietario de un flujo:

1. Seleccione **Datos** en el panel de la izquierda.
1. Seleccione **Conexiones**.
1. Busque la conexión que desea actualizar y selecciónela.
1. Seleccione **...** (más comandos) en la conexión que ha seleccionado y, luego, seleccione **Cambiar cuenta**.
1. Siga los pasos para usar una cuenta diferente para la conexión.

## <a name="embedded-and-other-connections"></a>Conexiones insertadas y otras

Las conexiones que se usan en un flujo se dividen en dos categorías:

* **Insertadas**: estas conexiones se utilizan en el flujo.
* **Otras**: estas conexiones se han definido para un flujo, pero no se utilizan en él.

Si una conexión deja de usarse en un flujo, aparecerá en la lista de **Otras** conexiones, donde permanecerá hasta que un propietario vuelva a incluirla en el flujo.

Siga los pasos para [actualizar el propietario de una conexión](./create-team-flows.md#update-connection-owner) con el fin de realizar cambios en las conexiones insertadas.

La lista de conexiones aparece debajo de la lista de propietarios en las propiedades de un flujo:

![conexiones incrustadas](./media/create-team-flows/embeddedconnections.png)

