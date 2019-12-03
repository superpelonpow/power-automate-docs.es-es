---
title: Creación de un flujo automatizado con Common Data Service | Microsoft Docs
description: Creación de flujos de trabajo mediante una conexión de Common Data Service y Power Automate
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/06/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2808fb064ae0910d184d1f785a528c6f44e601af
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74360288"
---
# <a name="create-an-automated-flow-by-using-common-data-service"></a>Creación de un flujo automatizado mediante Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Con el conector Common Data Service, puede crear flujos que se inicien mediante la creación y actualización de eventos dentro de la base de datos de Common Data Service. Además, puede realizar acciones de creación, actualización, recuperación y eliminación en registros dentro de la base de datos de Common Data Service.

## <a name="initiate-a-flow-from-common-data-service"></a>Inicio de un flujo desde Common Data Service

Puede usar cualquiera de los siguientes desencadenadores para iniciar el flujo:

- Cuando se selecciona un registro
- Al crear un registro
- Al eliminar un registro
- Al actualizar un registro


> [!div class="mx-imgBorder"]
> ![Selección de un desencadenador](./media/cds-connector/Triggers.png)

Si el desencadenador seleccionado requiere la selección de un entorno, puede elegir `(Current)`, que siempre usa la base de datos del entorno en el que se ejecuta Power Automate. Si quiere que el flujo siempre se desencadene en función de un evento de un entorno determinado, seleccione ese entorno.

> [!div class="mx-imgBorder"]
> ![Elección de entorno](./media/cds-connector/Environments.png)

Puede usar ámbitos para determinar si el flujo se ejecuta al crear un nuevo registro, si un usuario de la unidad de negocio crea un nuevo registro o si lo hace cualquier usuario de la organización.

> [!div class="mx-imgBorder"]
> ![Elección de ámbito](./media/cds-connector/Scopes.png)

|Ámbito|Momento del desencadenador|
| --- | --- |
|Unidad de negocio|Se realiza una acción en un registro que es propiedad de la unidad de negocio|
|Organización|Cualquier usuario de la organización o la base de datos realiza una acción|
|Elemento principal: unidad de negocio secundaria|Se realiza una acción en un registro que es propiedad de la unidad de negocio o una unidad de negocio secundaria|
|Usuario|Se realiza una acción en un registro de su propiedad|

Los desencadenadores que se ejecutan cuando se actualiza un registro también pueden usar atributos de filtrado. Esto garantiza que el flujo solo se ejecute cuando se actualice cualquiera de los atributos definidos.

> [!IMPORTANT]
> Use atributos de filtrado para evitar que el flujo se ejecute innecesariamente.

Este flujo se desencadena cada vez que se actualiza el nombre o apellido de contacto que posee el usuario del flujo.

> [!div class="mx-imgBorder"]
> ![Atributos de filtrado](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>Privilegios de desencadenador

Para crear un flujo que se desencadene en función de la creación, actualización o eliminación de un registro, el usuario debe tener permisos de nivel de usuario para crear, leer, escribir y eliminar en la entidad de registro de devolución de llamadas. Además, según los ámbitos definidos, el usuario puede necesitar al menos ese nivel de lectura en la misma entidad.  [Más información](https://docs.microsoft.com/power-platform/admin/database-security) sobre la seguridad del entorno.

## <a name="write-data-into-common-data-service"></a>Escritura de datos en Common Data Service

Para escribir datos en Common Data Service, use cualquiera de las acciones siguientes:

- Crear un nuevo registro
- Actualizar un registro

Este es un ejemplo de creación de una tarea de seguimiento cuando el usuario crea un nuevo registro de cuenta.  

> [!div class="mx-imgBorder"]
> ![Tarea de seguimiento](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>Conceptos avanzados

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Escribir datos en los campos Cliente, Propietario y Referente a

Para escribir datos en los campos Cliente, Propietario y Referente a, deben rellenarse dos campos.

| Categoría de campo | Configuración de ejemplo |
| --- | --- |
| Referente a | Referente a = identificador del registro (por ejemplo, identificador de cuenta) y Tipo referente a seleccionados en la lista. |
| Cliente | Representa el identificador de registro y el tipo de cliente seleccionados en la lista. |
| Propietario | Representa el identificador del usuario o equipo del sistema y el tipo de propietario seleccionados en la lista. |

### <a name="enable-upsert-behavior"></a>Habilitar comportamiento de upsert

Puede aprovechar el comando **Actualizar un registro** para proporcionar acciones de upsert, lo que actualiza el registro si ya existe o crea uno nuevo. Para invocar una acción de upsert, proporcione la entidad y una clave GUID. Si el registro con el tipo especificado y la clave especificados existe, se produce una actualización. De lo contrario, se crea un registro con la clave especificada.

### <a name="trigger-behavior"></a>Comportamiento de desencadenador

Si tiene un desencadenador registrado en la actualización de un registro, el flujo se ejecuta para cada actualización *confirmada* de ese registro. El servicio invoca al flujo de forma asincrónica y con la carga que captura en el momento en que se produce la invocación.

> [!NOTE]
> Si tiene dos actualizaciones que se producen con una diferencia de segundos entre sí, el flujo se puede desencadenar más de una vez con el contenido más reciente con versiones.

Si hay un trabajo pendiente de trabajos del sistema en el entorno, se pueden retrasar las ejecuciones del flujo.  Si se produce este retraso, el flujo se desencadena cuando se ejecuta el trabajo del sistema para invocar al flujo.

### <a name="call-any-common-data-service-action"></a>Llamar a cualquier acción de Common Data Service

Los flujos de trabajo automatizados pueden llamar a todas las acciones de Common Data Service, desde cumplimentar un pedido de venta hasta exportar un archivo de Microsoft Excel.

 ![Todas las acciones](./media/cds-connector/all-actions.png "todas las acciones")


