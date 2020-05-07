---
title: Creación de un flujo automatizado con el conector de Common Data Service (entorno actual) | Microsoft Docs
description: Creación de flujos de trabajo mediante un conector de Common Data Service (entorno actual) y Power Automate
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
ms.date: 04/26/2020
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 96b97fe3e6090a2810c0fa0e1dfae2d4b890da62
ms.sourcegitcommit: e58c8e6954c8e666497a66dc945fdc16c7c845a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728548"
---
# <a name="create-an-automated-flow-by-using-common-data-service-current-environment"></a>Creación de un flujo automatizado mediante Common Data Service (entorno actual)

>[!IMPORTANT]
>Hay tres conectores disponibles para conectarse a Common Data Service. En este artículo, se describe el [conector de Common Data Service (entorno actual)](./connection-cds.md) recomendado para conectarse a Common Data Serivce. Si no puede usar el conector recomendado, también tiene disponibles el [conector de Common Data Service](./connection-cds.md) y el [conector de Dynamics 365](https://docs.microsoft.com/connectors/dynamicscrmonline/).


Para poder usar el conector de Common Data Service (entorno actual), debe [crear flujos que admitan la solución](./overview-solution-flows.md). 

Los flujos que cree podrán desencadenarse cuando se cree, se actualice o se elimine un registro de Common Data Service.

Además, puede realizar acciones de creación, actualización, recuperación y eliminación en registros dentro de Common Data Service.

## <a name="initiate-a-flow-with-common-data-service-current-environment"></a>Inicio de un flujo con Common Data Service (entorno actual)

Use el desencadenador **When a record is created, updated or deleted** (Cuando se cree, actualice o elimine un registro) para iniciar el flujo:

   ![Selección de un desencadenador](./media/cds-connector-native/native-trigger.png)

Después de seleccionar un desencadenador, deberá configurar lo siguiente:

- Una condición para el desencadenador.
- Nombre de la entidad.
- Ámbito del desencadenador.

### <a name="trigger-condition"></a>Condición desencadenadora

Puede agregar cualquiera de estas condiciones para determinar exactamente cuándo se desencadena el flujo.

   ![Selección de un desencadenador](./media/cds-connector-native/trigger-conditions.png)

### <a name="the-entity-name"></a>Nombre de la entidad

Seleccione cualquiera de las numerosas entidades que están disponibles para indicar la entidad en la que funciona el desencadenador.

   ![Selección de un desencadenador](./media/cds-connector-native/entity-names.png)

### <a name="scope"></a>Ámbito

Use los ámbitos para determinar si el flujo se ejecuta cuando usted, alguien de su unidad empresarial o cualquier usuario de su organización crea un registro.

![Elección de ámbito](./media/cds-connector-native/scopes.png)

Estos son los detalles de cada ámbito.

|Ámbito|Momento del desencadenador|
| --- | --- |
|Unidad de negocio|Se realiza una acción en un registro que es propiedad de la unidad de negocio|
|Organización|Cualquier usuario de la organización o la base de datos realiza una acción|
|Elemento principal: unidades de negocio secundarias|Se realiza una acción en un registro que es propiedad de la unidad de negocio o una unidad de negocio secundaria|
|Usuario|Se realiza una acción en un registro de su propiedad|


Los desencadenadores que se ejecutan cuando se actualiza un registro también pueden usar atributos de filtrado. Esto garantiza que el flujo solo se ejecute cuando se actualice cualquiera de los atributos definidos.

> [!IMPORTANT]
> Use atributos de filtrado para evitar que el flujo se ejecute innecesariamente.

Este flujo se desencadena cada vez que se actualiza el nombre o apellido de contacto que posee el usuario del flujo.

![Atributos de filtrado](./media/cds-connector-native/filtering-attributes.png)

## <a name="trigger-privileges"></a>Privilegios de desencadenador

Para crear un flujo que se desencadene en función de la creación, actualización o eliminación de un registro, el usuario debe tener permisos de nivel de usuario para crear, leer, escribir y eliminar en la entidad de **registro de devolución de llamadas**. Además, según los ámbitos definidos, el usuario puede necesitar al menos ese nivel de lectura en la misma entidad.  [Más información](https://docs.microsoft.com/power-platform/admin/database-security) sobre la seguridad del entorno.

## <a name="write-data-into-common-data-service"></a>Escritura de datos en Common Data Service

Para escribir datos en Common Data Service, use cualquiera de las acciones siguientes:

![Atributos de filtrado](./media/cds-connector-native/actions.png)

A continuación, se muestra un ejemplo de un flujo que envía una notificación con el nombre y los ingresos anuales cada vez que cualquier usuario del **ámbito** de la unidad empresarial **crea** una **cuenta**.

> ![Tarea de seguimiento](./media/cds-connector-native/example-flow.png)

## <a name="advanced-concepts"></a>Conceptos avanzados

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Escribir datos en los campos Cliente, Propietario y Referente a

Para escribir datos en los campos Cliente, Propietario y Referente a, deben rellenarse dos campos.

| Categoría de campo | Configuración de ejemplo |
| --- | --- |
| Referente a | Referente a = identificador del registro (por ejemplo, identificador de cuenta) y Tipo referente a seleccionados en la lista. |
| Cliente | Representa el identificador de registro y el tipo de cliente seleccionados en la lista. |
| Propietario | Representa el identificador del usuario o equipo del sistema y el tipo de propietario seleccionados en la lista. |

### <a name="enable-upsert-behavior"></a>Habilitar comportamiento de upsert

Puede aprovechar la acción **Actualizar un registro** para proporcionar acciones de upsert, lo que actualiza el registro si ya existe o crea uno nuevo. Para invocar una acción de upsert, proporcione la entidad y una clave GUID. Si el registro con el tipo especificado y la clave especificados existe, se produce una actualización. De lo contrario, se crea un registro con la clave especificada.

### <a name="trigger-behavior"></a>Comportamiento de desencadenador

Si tiene un desencadenador registrado en la actualización de un registro, el flujo se ejecuta para cada actualización *confirmada* de ese registro. El servicio invoca al flujo de forma asincrónica y con la carga que captura en el momento en que se produce la invocación.

> [!NOTE]
> Si tiene dos actualizaciones que se producen con una diferencia de segundos entre sí, el flujo se puede desencadenar más de una vez con el contenido más reciente con versiones.

Si hay un trabajo pendiente de trabajos del sistema en el entorno, se pueden retrasar las ejecuciones del flujo. Si se produce este retraso, el flujo se desencadena cuando se ejecuta el trabajo del sistema para iniciar el flujo.



