---
title: Crear un flujo automatizado con el conector de Common Data Service (entorno actual) | Microsoft Docs
description: Crear flujos de trabajo utilizando un conector de Common Data Service (entorno actual) y Power Automate
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
ms.locfileid: "3331117"
---
# <a name="create-an-automated-flow-by-using-common-data-service-current-environment"></a>Crear un flujo automatizado mediante Common Data Service (entorno actual)

>[!IMPORTANT]
>Hay tres conectores disponibles para conectarse a Common Data Service. Este artículo cubre el [conector de Common Data Service (entorno actual)](./connection-cds.md) recomendado para conectarse a Common Data Serivce. El [conector de Common Data Service](./connection-cds.md)y [Dynamics 365 Connector](https://docs.microsoft.com/connectors/dynamicscrmonline/) también están disponibles para su uso si no puede usar el conector recomendado.


Debe [crear flujos que reconozcan las soluciones](./overview-solution-flows.md) para usar el conector de Common Data Service (entorno actual). 

Los flujos que crea pueden desencadenarse cuando un registro de Common Data Service se crea, actualiza o elimina.

Además, puede realizar acciones de creación, actualización, recuperación y eliminación en registros dentro de Common Data Service.

## <a name="initiate-a-flow-with-common-data-service-current-environment"></a>Iniciar un flujo con Common Data Service (entorno actual)

Use el desencadenador **Cuando un registro de se crea, actualiza o elimina** para iniciar su flujo:

   ![Selección de un desencadenador](./media/cds-connector-native/native-trigger.png)

Después de seleccionar un desencadenador, deberá configurar:

- Una condición para el desencadenador.
- Nombre de la entidad.
- El alcance del desencadenador.

### <a name="trigger-condition"></a>Condición de desencadenador

Puede agregar cualquiera de estas condiciones para determinar con precisión cuándo se desencadena su flujo.

   ![Selección de un desencadenador](./media/cds-connector-native/trigger-conditions.png)

### <a name="the-entity-name"></a>El nombre de entidad

Seleccione cualquiera de las numerosas entidades que están disponibles para indicar la entidad en la que opera su desencadenador.

   ![Selección de un desencadenador](./media/cds-connector-native/entity-names.png)

### <a name="scope"></a>Scope

Use ámbitos para determinar si su flujo se ejecuta cuando usted, alguien en su unidad de negocios o cualquier usuario de su organización crean un registro.

![Elegir ámbito](./media/cds-connector-native/scopes.png)

Aquí están los detalles de cada ámbito.

|Scope|Momento del desencadenador|
| --- | --- |
|Unidad de negocio|Se realiza una acción en un registro que es propiedad de la unidad de negocio|
|Organización|Cualquier usuario de la organización o la base de datos realiza una acción|
|Elemento principal: unidad de negocio secundaria|Se realiza una acción en un registro que es propiedad de la unidad de negocio o una unidad de negocio secundaria|
|Usuario|Se realiza una acción en un registro de su propiedad|


Los desencadenadores que se ejecutan cuando se actualiza un registro también pueden usar atributos de filtrado. Esto garantiza que el flujo solo se ejecute cuando se actualice cualquiera de los atributos definidos.

> [!IMPORTANT]
> Use atributos de filtrado para evitar que el flujo se ejecute innecesariamente.

Este flujo se desencadena cada vez que se actualiza el nombre o apellido de contacto que posee el usuario del flujo.

![Atributos del filtro](./media/cds-connector-native/filtering-attributes.png)

## <a name="trigger-privileges"></a>Privilegios de desencadenador

Para crear un flujo que se desencadene en función de la creación, actualización o eliminación de un registro, el usuario debe tener permisos de nivel de usuario para crear, leer, escribir y eliminar en la entidad de **Registro de devolución de llamadas**. Además, según los ámbitos definidos, el usuario puede necesitar al menos ese nivel de lectura en la misma entidad.  [Más información](https://docs.microsoft.com/power-platform/admin/database-security) sobre la seguridad del entorno.

## <a name="write-data-into-common-data-service"></a>Escribir datos en Common Data Service

Para escribir datos en Common Data Service, use cualquiera de las acciones siguientes:

![Atributos del filtro](./media/cds-connector-native/actions.png)

Este es un ejemplo de un flujo que envía una notificación con el nombre y los ingresos anuales cada vez que una **cuenta** se **crea** por cualquier persona en el **ámbito** de la unidad de negocios.

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



