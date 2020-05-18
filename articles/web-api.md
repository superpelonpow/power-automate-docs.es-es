---
title: Los flujos se almacenan ahora en Common Data Service y usan la API web enriquecida
description: Los flujos se almacenan ahora en Common Data Service y usan la API web enriquecida.
author: stepsic-microsoft-com
ms.reviewer: deonhe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: business-applications
ms.technology: ''
ms.author: stepsic
audience: Power user
ms.openlocfilehash: f446b1b4147b8531ee808447a18058628c2ac0cf
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298361"
---
# <a name="power-automate-web-api"></a>API web de Power Automate


A partir de ahora, todos los flujos se almacenarán en Common Data Service y usarán la [API web enriquecida](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/perform-operations-web-api).

Este contenido cubre la administración de flujos incluidos en la pestaña **Soluciones** de Power Automate. Actualmente, estas API no admiten los flujos incluidos en **Mis flujos**.

## <a name="compose-http-requests"></a>Redactar solicitudes HTTP

Para empezar a crear las solicitudes, primero deberá crear la dirección URL. El formato de la dirección URL base de la API web de Power Automate es: `https://{Organization ID}.{Regional Subdomain}.dynamics.com/api/data/v9.1/`. Los dos parámetros son:

- **Organization ID** es un nombre único del entorno donde se almacenan los flujos. Este identificador de organización se puede ver en el conmutador de entorno, en la parte superior derecha de Power Automate. Cabe decir que **Organization ID** no es lo mismo que **Environment ID** (que es el GUID que aparece en la dirección URL del flujo).

     ![Conmutador de entorno](media/web-api/get-organization-id.png "Conmutador de entorno")

- **Regional Subdomain** depende de la ubicación de su entorno. Al iniciar sesión en Power Automate, puede ver la región de su entorno en la dirección URL de la página web. Use ese nombre de región para buscar el subdominio correspondiente en la siguiente tabla:

     ![Dirección URL de flujo](media/web-api/get-region-name.png "Dirección URL de flujo")

     | Región         | Subdominio   |
     | -------------- | ----------- |
     | Estados Unidos  | crm         |
     | Sudamérica  | crm2        |
     | Canadá         | crm3        |
     | Europa         | crm4        |
     | Asia Pacífico   | crm5        |
     | Australia      | crm6        |
     | Japón          | crm7        |
     | India          | crm8        |
     |  para la Administración Pública de Estados Unidos  | crm9        |
     | Reino Unido | crm11       |

La lista de instancias disponibles también se puede obtener mediante programación a través del método [Get Instances](https://docs.microsoft.com/rest/api/admin.services.crm.dynamics.com/instances/getinstances) de la API de Online Management.

Cada solicitud realizada a la API web debe tener los encabezados `Accept` y `Content-type` establecidos en `application/json`.

Por último, rellene el encabezado `Authorization` con un token de portador de Azure AD. Usted puede [aprender](https://docs.microsoft.com/powerapps/developer/common-data-service/authenticate-oauth) cómo adquirir un token de portador de Azure AD para Common Data Service. Por ejemplo, en esta solicitud:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
```

La respuesta contiene la lista de flujos desde dentro de ese entorno:

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#workflows",
    "value": [{
        "@odata.etag": "W/\"12116760\"",
        "category": 5,
        "statecode": 0,
        "workflowidunique": "00000000-0000-0000-0000-000000000001",
        "workflowid" : "00000000-0000-0000-0000-000000000002",
        "createdon": "2018-11-15T19:45:51Z",
        "_ownerid_value": "00000000-0000-0000-0000-000000000003",
        "modifiedon": "2018-11-15T19:45:51Z",
        "ismanaged": false,
        "name": "Sample flow",
        "_modifiedby_value": "00000000-0000-0000-0000-000000000003",
        "_createdby_value": "00000000-0000-0000-0000-000000000003",
        "type": 1,
        "description": "This flow updates some data in Common Data Service.",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"source\":\"NotSpecified\",\"id\":\"/providers/Microsoft.PowerApps/apis/shared_commondataservice\",\"tier\":\"NotSpecified\"}},\"definition\":{...}},\"schemaVersion\":\"1.0.0.0\"}"
    }]
}
```

## <a name="list-flows"></a>Lista de flujos

Tal y como se ha señalado arriba, se puede obtener la lista de flujos de trabajo con una llamada a `GET` en `workflows`. Cada flujo de trabajo tiene muchas propiedades, pero las más relevantes son las siguientes:

| Nombre de la propiedad     | Descripción                                              |
| ----------------- | -------------------------------------------------------- |
| categoría          | Categoría del flujo. Los distintos tipos son: 0 - flujos de trabajo clásicos de Common Data Service, 1 - cuadros de diálogo clásicos de Common Data Service, 2 - reglas de negocio, 3 - acciones clásicas de Common Data Service, 4 - flujos de procesos de negocio y 5 - flujos automatizados, instantáneos o programados. |
| statecode         | Estado del flujo. El estado puede ser **0** (desactivado) o **1** (activado).|
| workflowuniqueid  | Identificador único de esta instalación del flujo. |
| workflowid        | Identificador único de un flujo en todas las importaciones. |
| createdon         | Fecha en que se creó el flujo. |
| _ownerid_value    | Identificador único del usuario o el equipo que posee el flujo. Se trata de un identificador de la entidad systemusers en Common Data Service. |
| modifiedon        | Última vez que se actualizó el flujo. |
| ismanaged         | Indica si el flujo se ha instalado a través de una solución administrada. |
| nombre              | Nombre para mostrar que se le ha dado al flujo. |
| _modifiedby_value | Último usuario que actualizó el flujo. Se trata de un identificador de la entidad systemusers en Common Data Service. |
| _createdby_value  | Usuario que creó el flujo. Se trata de un identificador de la entidad systemusers en Common Data Service. |
| tipo              | Indica si el flujo es un flujo en ejecución o una plantilla que se puede usar para crear más flujos. 1 (flujo), 2 (activación) o 3 (plantilla). |
| descripción       | Descripción del flujo proporcionada por el usuario. |
| clientdata        | JSON codificado como cadena de un objeto que contiene el parámetro connectionReferences y la definición del flujo. |

También puede solicitar propiedades concretas, filtrar la lista de flujos y realizar otras muchas cosas, como se describe en la [documentación de la API de Common Data Service ](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/query-data-web-api). Por ejemplo, esta consulta devuelve únicamente los flujos automatizados, instantáneos o programados que están activados actualmente:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows?$filter=category eq 5 and statecode eq 1
Accept: application/json
Authorization: Bearer ey...
```

## <a name="create-a-flow"></a>Crear un flujo

Para crear un flujo, llame a `POST` en la colección `workflows`. Las propiedades necesarias en los flujos automatizados, instantáneos o programados son category, name, type, primaryentity y clientdata. Use `none` como primaryentity en estos tipos de flujos.

También puede especificar las propiedades description y statecode.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
        "category": 5,
        "statecode": 0,
        "name": "Sample flow name",
        "type": 1,
        "description": "This flow reads some data from Common Data Service.",
        "primaryentity":"none",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"connectionName\":\"shared-commondataser-00000000-0000-0000-0000-000000000004\",\"source\":\"Invoker\",\"id\":\"/providers/Microsoft.Power Apps/apis/shared_commondataservice\"}},\"definition\":{\"$schema\": \"https:\/\/schema.management.azure.com\/providers\/Microsoft.Logic\/schemas\/2016-06-01\/workflowdefinition.json#\",\"contentVersion\": \"1.0.0.0\",\"parameters\": {\"$connections\": {\"defaultValue\": {},\"type\": \"Object\"},\"$authentication\": {\"defaultValue\": {},\"type\": \"SecureObject\"}},\"triggers\": {\"Recurrence\": {\"recurrence\": {\"frequency\": \"Minute\",\"interval\": 1},\"type\": \"Recurrence\"}},\"actions\": {\"List_records\": {\"runAfter\": {},\"metadata\": {\"flowSystemMetadata\": {\"swaggerOperationId\": \"GetItems_V2\"}},\"type\": \"ApiConnection\",\"inputs\": {\"host\": {\"api\": {\"runtimeUrl\": \"https:\/\/firstrelease-001.azure-apim.net\/apim\/commondataservice\"},\"connection\": {\"name\": \"@parameters('$connections')['shared_commondataservice']['connectionId']\"}},\"method\": \"get\",\"path\": \"\/v2\/datasets\/@{encodeURIComponent(encodeURIComponent('default.cds'))}\/tables\/@{encodeURIComponent(encodeURIComponent('accounts'))}\/items\",\"queries\": {\"$top\": 1},\"authentication\": \"@parameters('$authentication')\"}}},\"outputs\": {}}},\"schemaVersion\":\"1.0.0.0\"}"
}
```

La sección más importante es `clientdata`, que contiene el parámetro connectionReferences que el flujo usa y la propiedad [definition](https://docs.microsoft.com/azure/logic-apps/logic-apps-workflow-definition-language) del flujo. El parámetro connectionReferences son las asignaciones a cada conexión que el flujo utiliza.

Hay tres propiedades:

| Nombre de la propiedad  | Descripción                                                 |
| -------------- | ----------------------------------------------------------- |
| connectionName | Identifica la conexión. Para ver la propiedad connectionName, vaya a la página **Conexiones** y, después, cópiela desde la dirección URL de la conexión. |
| origen         | `Embedded` o `Invoker`. `Invoker` solo es válido en los flujos instantáneos (aquellos en los que un usuario selecciona un botón para ejecutar el flujo) e indica que el usuario final proporcionará la conexión. En este caso, la propiedad connectionName solo se utiliza en el tiempo de diseño. Si la conexión es `Embedded`, significa que siempre se usa la propiedad connectionName que se especifique. |
| id.             | Identificador del conector. El identificador siempre comienza por `/providers/Microsoft.PowerApps/apis/` y le sigue el nombre del conector, que puede copiar desde la dirección URL de la conexión, o bien seleccionando el conector en la página **Conectores**. |

Una vez ejecutada la solicitud `POST`, recibirá el encabezado `OData-EntityId`, que contendrá la propiedad `workflowid` del nuevo flujo.

## <a name="update-a-flow"></a>Actualizar un flujo

Puede llamar a `PATCH` en el flujo de trabajo para actualizar, activar o desactivar un flujo. Use la propiedad `workflowid` para realizar estas llamadas. Por ejemplo, puede actualizar la descripción y el propietario del flujo con la siguiente llamada:

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "description" : "This flow will ensure consistency across systems.",
    "ownerid@odata.bind": "systemusers(00000000-0000-0000-0000-000000000005)",
}
```

> [!NOTE]
> La sintaxis para cambiar el propietario emplea el formato `odata.bind`. Esto significa que, en lugar de aplicar revisiones al campo \_ownerid_value directamente, se anexa `@odata.bind` al nombre de propiedad y, luego, se encapsula el identificador con `systemusers()`.

En otro ejemplo, puede activar un flujo con esta llamada:

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "statecode" : 1
}
```

### <a name="delete-a-flow"></a>Eliminar un flujo

Elimine un flujo con una sencilla llamada a `DELETE`:

```http
DELETE https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
```

> [!NOTE]
> No se puede eliminar un flujo que está activado. Primero deberá desactivarlo (vea **Actualizar un flujo** más arriba) o, de lo contrario, aparecerá el error: `Cannot delete an active workflow definition.`

## <a name="get-all-users-with-whom-a-flow-is-shared"></a>Obtener todos los usuarios con los que se comparte un flujo

Para obtener una lista de los usuarios con acceso al flujo, se usa una *función* en Common Data Service. Esta función toma un solo parámetro `Target`:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/RetrieveSharedPrincipalsAndAccess(Target=@tid)?@tid={'@odata.id':'workflows(00000000-0000-0000-0000-000000000002)'}
Accept: application/json
Authorization: Bearer ey...
```

El parámetro `Target` es una cadena similar a JSON con una única propiedad denominada `@odata.id`. Reemplace el identificador del flujo de trabajo en el ejemplo anterior. Se devuelve lo siguiente:

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.RetrieveSharedPrincipalsAndAccessResponse",
    "PrincipalAccesses": [
        {
            "AccessMask": "ReadAccess",
            "Principal": {
                "@odata.type": "#Microsoft.Dynamics.CRM.systemuser",
                "ownerid": "00000000-0000-0000-0000-000000000005"
            }
        }
    ]
}
```

## <a name="share-or-unshare-a-flow"></a>Compartir o dejar de compartir un flujo

Puede compartir un flujo mediante la acción `GrantAccess`.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/GrantAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "PrincipalAccess": {
        "Principal": {
            "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
            "ownerid" : "00000000-0000-0000-0000-000000000005"
        },
        "AccessMask": "ReadAccess"
    }
}
```

El parámetro `AccessMask` es un campo con los siguientes valores relativos a los distintos niveles de permiso:

| Nombre         | Descripción                                          |
| ------------ | ---------------------------------------------------- |
| Ninguno         | Sin acceso.                                           |
| Acceso de lectura   | Derecho a leer el flujo.                          |
| WriteAccess  | Derecho a actualizar el flujo.                        |
| DeleteAccess | Derecho a eliminar el flujo.                        |
| ShareAccess  | Derecho a compartir el flujo.                         |
| AssignAccess | Derecho para cambiar el propietario del flujo.           |

Puede combinar varios permisos usando comas; por ejemplo, para proporcionar la capacidad tanto de leer como de actualizar un flujo, se pasaría `ReadAccess,WriteAccess`.

También puede *dejar de compartir* un flujo con la acción `RevokeAccess`. Veamos un ejemplo:

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/RevokeAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "Revokee": {
        "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
        "ownerid" : "00000000-0000-0000-0000-000000000005"
    }
}
```

`RevokeAccess` quita todos los permisos concedidos en `AccessMask`.

## <a name="export-flows"></a>Exportar flujos

Use la acción `ExportSolution` para exportar flujos a un archivo .zip. Primero, agregue los flujos que quiera a una [solución](https://flow.microsoft.com/blog/solutions-in-microsoft-flow/).

Una vez que los flujos están en una solución, llame a la siguiente acción:

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ExportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "SolutionName" : "Awesome solution 1",
    "Managed": false
}
```

`ExportSolution` devuelve una cadena con codificación en Base64 en la propiedad `ExportSoutionFile`.

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.ExportSolutionResponse",
    "ExportSolutionFile": "UEsDBBQAAgAI..."
}
```

Puede guardar este archivo en el control de código fuente o usar el sistema de administración o distribución de versiones que quiera.

## <a name="import-flows"></a>Importar flujos

Llame a la acción `ImportSolution` para importar una solución.

| Nombre de la propiedad                    | Descripción                               |
| -------------------------------- | ----------------------------------------- |
| OverwriteUnmanagedCustomizations | Si no hay instancias existentes de estos flujos en Common Data Service, esta marca se debe establecer en `true` para importarlos. En caso contrario, no se sobrescribirán. |
| PublishWorkflows                 | Indica si los flujos de trabajo clásicos de Common Data Service se activarán con la importación. Esta configuración no es válida con ningún otro tipo de flujo. |
| ImportJobId                      | Proporciona un GUID nuevo y único para realizar un seguimiento del trabajo de importación. |
| CustomizationFile                | Archivo ZIP con codificación en Base64 que contiene la solución. |

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ImportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "OverwriteUnmanagedCustomizations": false,
    "PublishWorkflows" : true,
    "ImportJobId" : "00000000-0000-0000-0000-000000000006",
    "CustomizationFile" : "UEsDBBQAAgAI..."
}
```

Como la importación es una operación de larga ejecución, la respuesta a la acción ImportSolution será `204 No content`. Para llevar un seguimiento del progreso, llame a `GET` en el objeto `importjobs`, lo que le proporcionará el `ImportJobId` que incluyó en la acción `ImportSolution` original.

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/importjobs(00000000-0000-0000-0000-000000000006)
Accept: application/json
Authorization: Bearer ey...
```

Esta llamada devuelve el estado de la operación de importación, incluidos `progress` (porcentaje de finalización), `startedon` y `completedon` (si la importación ha finalizado).

Cuando la importación finalice correctamente, deberá configurar las conexiones del flujo, ya que `connectionNames` probablemente sea diferente en el entorno de destino (si es que existen conexiones). Si está configurando nuevas conexiones en el entorno de destino, el propietario de los flujos deberá crearlas en Microsoft Power Automate. Si las conexiones ya están configuradas en el nuevo entorno, puede usar una acción `PATCH` en el `clientData` del flujo con los nombres de las conexiones.
