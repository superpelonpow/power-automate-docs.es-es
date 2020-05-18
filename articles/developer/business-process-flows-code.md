---
title: Uso de flujos de proceso de negocio con código | Microsoft Docs
description: Obtenga información sobre cómo trabajar mediante programación con flujos de proceso de negocio para crear procesos de negocio más eficaces y simplificados.
ms.custom: ''
ms.date: 07/09/2018
ms.reviewer: ''
ms.service: flow
ms.topic: article
ms.assetid: 67d8cf80-9f77-4804-97a1-cf9f61417e83
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: d65be1552c3e748e4910c4fb942a60322f6f1e19
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296579"
---
# <a name="work-with-business-process-flows-using-code"></a>Uso de flujos de proceso de negocio con código
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Un *flujo de proceso de negocio* permite crear ventas, servicios y otros procesos comerciales más eficaces y rentables. Crea una visualización de su proceso de negocio al colocar controles especiales en la parte superior de los formularios de entidad. Los usuarios son guiados a través de diversas fases de procesos de ventas, marketing o servicios de finalización. Cada proceso admite varias fases y pasos. Puede agregar o quitar pasos, cambiar el orden de las fases, o agregar nuevas entidades al flujo del proceso de negocio.  
  
Diferentes instancias de flujo de proceso de negocio pueden ejecutarse en paralelo con el mismo registro de entidades. Los usuarios pueden cambiar entre instancias de proceso de negocio simultáneo y reanudar el trabajo en una fase actual del proceso. 

En este tema se proporciona información sobre cómo puede mediante programación ejecutar flujos de proceso de negocio.

> [!NOTE]
> No tendrá que escribir código para trabajar con los flujos de proceso de negocio. Para obtener información sobre el uso de la interfaz de usuario para crear y administrar flujos de proceso de negocio, vea [Información general sobre flujos de proceso de negocio](../business-process-flows-overview.md).  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>Requisitos previos para el flujo de proceso de negocio 

Las entidades personalizadas y las entidades que han actualizado los formularios de la interfaz de usuario pueden participar en el flujo de proceso de negocio. Las entidades actualizadas de la interfaz de usuario tienen la propiedad de <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> definida en `true`. 

Para habilitar una entidad para el flujo de proceso de negocio, defina la propiedad de <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> en `true`.

> [!IMPORTANT]
>  La habilitación de una entidad para el flujo de proceso de negocio es un proceso unidireccional. No puede revertirlo.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>Definir flujo de proceso de negocio
  
Use el nuevo diseñador visual de flujo de proceso de negocio para definir un flujo de proceso de negocio. Más información: [Crear un flujo de proceso de negocio](../create-business-process-flow.md)

De forma predeterminada, un registro de flujo de proceso de negocio se crea en el estado `Draft`.  

Una definición de flujo de proceso de negocio se almacena en<xref:Microsoft.Dynamics.CRM.workflow> la entidad, así como la información de la fase del flujo de proceso de negocio se almacena en<xref:Microsoft.Dynamics.CRM.processstage> la entidad.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>Activar flujo de proceso de negocio  
 Para poder el flujo de proceso, debe activarlo. Para activarla, debe tener el privilegio `prvActivateBusinessProcessFlow` para la entidad `Workflow`. Use el mensaje de <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> para definir el estado del registro de entidad `Workflow` en `Activated`. Más información: [Realizar operaciones especializadas con Actualizar](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) 

 > [!NOTE]
 > También puede usar el diseñador de flujos de proceso de negocio para activar un flujo de proceso de negocio. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>Entidad de flujo de proceso de negocio 
 Una vez que se activa una definición de flujo de proceso de negocio cambia el estado del `Workflow` registrado de la entidad correspondiente o usando el diseñador de flujo de proceso de negocio, se crea una entidad personalizada con el nombre siguiente automáticamente para almacenar las instancias activadas de flujo de proceso de negocio: “*\<uniquename>*_*\<activesolutionprefix>*”, donde el uniquename se obtiene de nombre que especifique.  
  
 Por ejemplo, si especificó el nombre único de la definición de flujo de proceso de negocio como "My Custom BPF" y usa el editor predeterminado para la solución activa, el nombre de la entidad personalizada creada para almacenar las instancias de proceso será "new_mycustombpf".  
  
 Si el valor `uniquename` no está disponible para una definición de flujo de proceso de negocio, por ejemplo, si el flujo de proceso de negocio se ha importado como parte de la solución desde una versión anterior, el nombre predeterminado de la entidad personalizada será "`\<activesolutionprefix>_bpf_<GUID_BPF_Definition>`":  
  
> [!IMPORTANT]
>  Los registros de flujo de proceso de negocio de ejemplo usan las entidades del sistema para almacenar los registros de instancia de flujo de proceso de negocio correspondientes.  
>   
>  Pero en todas las definiciones de flujo de proceso de negocio que cree se usarán entidades personalizadas para almacenar sus registros de instancia como se explicó anteriormente. 

Puede recuperar el nombre de su entidad de flujo de procesos de negocio mediante una de las siguientes formas:

- **Uso de la interfaz de usuario**: Use la interfaz de usuario de personalización para examinar la entidad de flujo de proceso de negocio:

    ![](media/bpf-entity-name.png)
- **Uso de API web**: Use la solicitud siguiente:

    **Solicitud**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **Response**
    ```
    {  
    "@odata.context":"[Organization URI]/api/data/v9.0/$metadata#workflows(uniquename)",
    "value":[  
         {  
             "@odata.etag":"W/\"1084677\"",
             "uniquename":"new_mycustombpf",
             "workflowid":"2669927e-8ad6-4f95-8a9a-f1008af6956f"
         }
      ]
    }
    ```
- **Con el servicio de la organización**: use el siguiente ejemplo de código:

    ```c#
    QueryExpression query = new QueryExpression
    {
        EntityName = "workflow",
        ColumnSet = new ColumnSet("uniquename"),
        Criteria = new FilterExpression
        {
            Conditions =
            {
                new ConditionExpression
                {
                    AttributeName = "name",
                    Operator = ConditionOperator.Equal,
                    Values = { "My Custom BPF" }
                }
            }
        }
    };
    Workflow Bpf = (Workflow)_serviceProxy.RetrieveMultiple(query).Entities[0]; 
    ```
> [!NOTE]
> La propiedad <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> es `true` para entidades de flujo de proceso de negocio. Puede recuperar todas las entidades de flujo de proceso de negocio de la instancia ejecutando la siguiente solicitud de la API web:
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## <a name="manage-security-for-business-process-flows"></a>Administración de la seguridad de flujos de proceso de negocio

La entidad personalizada que se crea automáticamente al activar un flujo de proceso de negocio para almacenar las instancias de flujo de proceso de negocio cumple con el modelo de seguridad estándar para cualquier otra entidad personalizada en Common Data Service. Esto implica que los privilegios concedidos en estas entidades definen los permisos de runtime de los usuarios para los flujos de proceso de negocio.

La entidad personalizada de flujos de proceso de negocio tiene un ámbito de organización. Los privilegios normales de creación, recuperación, actualización y eliminación de esta entidad definen los permisos que tendrían los usuarios en función de sus roles asignados. De manera predeterminada, al crear la entidad personalizada de flujo de proceso de negocio, solo se otorgan permisos a los roles de seguridad de **Administrador del sistema** y de **Personalizador del sistema**, y debe otorgar permisos explícitamente a la nueva entidad de flujo de proceso de negocio (por ejemplo, **Mi BPF personalizado**) para otros roles de seguridad, según corresponda.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## <a name="create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances"></a>Creación, recuperación, actualización y eliminación de registros de entidades de flujo de proceso de negocio (instancias de proceso)  
 La entidad personalizada que se crea automáticamente al activar una definición de flujo de proceso de negocio almacena todas las instancias de la definición de flujo de proceso de negocio. La entidad personalizada admite la creación mediante programación estándar y la administración de registros (instancias de proceso) mediante la API web y el punto de conexión de CRM 2011.

> [!IMPORTANT]
> El cambio a otra instancia de proceso desde un registro de entidad solo se admite mediante la interfaz de usuario (cliente) o mediante programación siguiendo la información disponible en esta sección. Ya no puede usar el mensaje `SetProcess` (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> o <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) para cambiar procesos mediante programación (establecer otro flujo de proceso de negocio como instancia de proceso activa) en el registro de entidad de destino. 

 Pongamos como ejemplo un flujo de proceso de negocio de varias entidades, "Mi FPN personalizado", que cuenta con 3 fases: S1:Cuenta, S2:Cuenta y S3:Contacto. 

 ![](media/sample-bpf.png)
 
### <a name="retrieve-all-the-records-instances-for-a-business-process-flow-entity"></a>Recuperación de todos los registros (las instancias) de una entidad de flujo de proceso de negocio
 Si el nombre de la entidad de flujo de proceso de negocio es "nuevo_mifpnpersonalizado", use la siguiente consulta para recuperar todos los registros (las instancias del proceso) de la entidad de flujo de proceso de negocio:  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

En este momento, es posible que no obtenga ninguna instancia en la respuesta ya que no hay ninguna. Ejecute esta solicitud después de crear una instancia de la definición de flujo de proceso de negocio más adelante en este tema.

> [!NOTE]
> Para saber recuperar el nombre de la entidad de flujo de proceso de negocio, consulte la sección anterior [Entidad de flujo de proceso de negocio](#business-process-flow-entity).
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>Cree un registro de entidad de flujo de proceso de negocio (procese la instancia) 

Cree un registro de entidad de flujo de proceso de negocio (procese la instancia) mediante programación si desea cambiar a otro flujo de proceso de negocio para registros de entidad sin usar la interfaz de usuario. 

Para crear un registro de entidad de flujo de proceso de negocio, deberá especificar los siguientes valores: 
- Asocie el registro de la entidad de flujo de proceso de negocio a un registro de la entidad principal configurando la propiedad de un solo valor de navegación mediante `@odata.bind` anotación. Para averiguar el nombre de la propiedad de navegación que apunta al registro de la entidad principal para la definición del flujo de su proceso de negocio, utilice el [CSDL $metadata document](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document). 
- Asocie el registro de la entidad de flujo de proceso de negocio de una fase válida especificada en la definición de flujo de proceso de negocio configurando la propiedad de un solo valor de navegación mediante `@odata.bind` anotación. Para averiguar el nombre de la propiedad de navegación (generalmente `activestageid`) que apunta al registro de fase para la definición de flujo del proceso de negocio, utilice el [CSDL $metadata document](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document).

    Además, puede recuperar la información sobre todas las fases de una definición de flujo de proceso de negocio mediante la solicitud de API web siguiente suponiendo que el identificador de la definición de flujo de proceso de negocio es 2669927e-8ad6-4f95-8a9a-f1008af6956f:

    **Solicitud**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **Respuesta**

    ```http
    {
        "@odata.context": "[Organization URI]/api/data/v9.0/$metadata#processstages(stagename)",
        "value": [
            {
                "@odata.etag": "W/\"858240\"",
                "stagename": "S1",
                "processstageid": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b"
            },
            {
                "@odata.etag": "W/\"858239\"",
                "stagename": "S3",
                "processstageid": "a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a"
            },
            {
                "@odata.etag": "W/\"858238\"",
                "stagename": "S2",
                "processstageid": "19a11fc0-3398-4214-8522-cb2a97f66e4b"
            }
        ]
    }
    ```

A continuación, use la solicitud siguiente para crear una instancia de la definición de flujo de proceso de negocio de un registro de cuenta (ID=a176be9e-9a68-e711-80e7-00155d41e206) y la fase activa configurada como la primera fase de la instancia del proceso, S1 (ID=9a9185f5-b75b-4bbb-9c2b-a6626683b99b):

**Solicitud**

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(a176be9e-9a68-e711-80e7-00155d41e206)",
    "activestageid@odata.bind": "/processstages(9a9185f5-b75b-4bbb-9c2b-a6626683b99b)"    
}
```

**Respuesta**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

Tenga en cuenta que si desea crear una instancia de la definición de flujo de proceso de negocio con la fase activa como una fase ***distinta*** de la primera fase, también debe proporcionar `traversedpath` en relación a su solicitud. La trayectoria recorrida es la cadena delimitada por comas de identificadores de fase de proceso que representan las fases visitadas de la instancia de flujo de proceso de negocio. La solicitud siguiente crea una instancia de un registro de cuenta (ID=679b2464-71b5-e711-80f5-00155d513100) y la fase activa establecida como la segunda fase, S2 (ID=19a11fc0-3398-4214-8522-cb2a97f66e4b).

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(679b2464-71b5-e711-80f5-00155d513100)",
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"   
}
```

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>Cree un registro de entidad de flujo de proceso de negocio (procese la instancia)

Puede actualizar una instancia de proceso para pasar a la fase siguiente o anterior, abandonar una instancia de proceso, reactivar una instancia de proceso o finalizar una instancia de proceso. 

#### <a name="stage-navigation"></a>Navegación de páginas

Para navegar a una fase diferente, debe actualizar un registro de instancia de proceso para cambiar su ID de fase activa y, en consecuencia, actualizar la ruta atravesada. Tenga en cuenta que solo debe pasar a la fase siguiente o anterior al actualizar una instancia de flujo de proceso de negocio.

Para realizar la navegación por fases, necesitará la ID de la instancia de flujo del proceso empresarial que desea actualizar. Para recuperarse todas las instancias del flujo de proceso de negocio, vea [Recupere todos los registros (instancias) para una entidad de flujo de proceso de negocio](#retrieve-all-the-records-instances-for-a-business-process-flow-entity) anterior.

Si se presupone que el identificador de la instancia de proceso que desea actualizar es dc2ab599-306d-e811-80ff-00155d513100, use la solicitud siguiente para actualizar la fase activa de S1 a S2:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
Content-Type: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0

{
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"
}
```

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>Cambiar el estado de una instancia de proceso: Anular, Reactivar o Finalizar 

Una instancia de proceso puede tener uno de los siguientes estados: **Activar**, **Finalizar** o **Anular**. El estado está determinado por los siguientes atributos en el registro de la instancia del proceso:

- **statecode**: Muestra el estado de la instancia del proceso.

    |Value|Etiqueta|
    |-----|-----|
    |0    |Active|
    |1    |Inactivos|

- **statuscode**: Muestra información sobre el estado de la instancia del proceso.

    |Value|Etiqueta|
    |-----|-----|
    |1    |Active|
    |2    |Finalizada|
    |3    |Anulado|

Por lo tanto, para **Anular** una instancia de proceso, use la siguiente solicitud configure `statecode` y `statuscode` valores adecuados:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{ 
    "statecode" : "1", 
    "statuscode": "3" 
}
```
 
> [!NOTE]
> Puede anular una instancia de proceso en cualquier fase.

De forma similar, reactivar una instancia de procesos, reemplazar `statecode` y `statuscode` los valores en el código anterior con **0** y **1** respectivamente.

Por último, establecer un estado del proceso de la instancia como **Finalizado**, que sólo es posible en la fase última de una instancia de procesos, reemplace `statecode` y `statuscode` los valores en el código anterior con **0** y **2** respectivamente.

#### <a name="cross-entity-navigation"></a>Navegación entre entidades

Para la navegación entre entidades en este ejemplo, debe establecer la fase activa de la instancia de proceso en la última fase, S3 (ID=a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a), actualizar la ruta transversal en consecuencia y establecer un registro de contacto como el registro de entidad principal según la definición de flujo del proceso de negocio.

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{
    "activestageid@odata.bind": "/processstages(a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b,a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a",
    "bpf_contactid@odata.bind": "/contacts(0e3f10b0-da33-e811-80fc-00155d513100)"
}
``` 

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>Cree un registro de entidad de flujo de proceso de negocio (proceso de instancia)

Use la API web: Use la solicitud siguiente:

**Solicitud**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Respuesta**

Si ya existe la entidad, recibirá una respuesta con estado 204 para indicar que la eliminación fue correcta. Si no se encuentra la entidad, recibirá una respuesta con estado 404.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>Use los mensajes de RetrieveProcessInstances y de RetrieveActivePath

Use el mensaje de `RetrieveProcessInstances` (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> o <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) para recuperar todas las instancias de flujo de proceso de negocio para un registro de entidad en todas las definiciones de proceso de negocio. Las instancias de flujo de proceso de negocio devueltas para una entidad se ordenan basándose en el atributo `modifiedon` para la instancia. Por ejemplo, la instancia de flujo de proceso de negocio modificada recientemente será el *primer* registro en la colección devuelta. La instancia de flujo de proceso de negocio modificada más recientemente es la que está activa en la interfaz de usuario para un registro de entidad.  
  
Cada registro de instancia de flujo de proceso empresarial devuelto para un registro de entidad como resultado del uso del mensaje `RetrieveProcessInstances` almacena la ID de la fase activa en el atributo `processstageid` que se puede usar para encontrar la fase activa y luego pasar a la fase anterior o siguiente. Para ello, primero necesita buscar la ruta activa de una instancia de flujo de proceso de negocio y las fases disponibles en la instancia de flujo de proceso utilizando el mensaje `RetrieveActivePath` (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> o <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>).   
  
 Una vez que tenga la información de la fase activa y ruta de acceso activa para una instancia de flujo de proceso de negocio, puede usar la información para pasar a una fase anterior o siguiente en la ruta activa. La navegación hacia delante de fases debe hacerse en orden, es decir, solo debe avanzar a la siguiente fase en la ruta activa.   
  
 Para la muestra completa, ese código demuestra el uso de estos dos métodos y la navegación por fases utilizando el [Servicio de la organización](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata), consulte [Ejemplo: Trabajar con flujos de proceso de negocio](sample-work-business-process-flows.md). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Aplicar el flujo de proceso de negocio cuando se crea un registro de entidad

En esta sección se proporciona información sobre el comportamiento predeterminado para los flujos de proceso de negocio que se aplican automáticamente a nuevos registros de entidades creadas en Common Data Service, y cómo puede reemplazarlo para aplicar un flujo de proceso de negocio de su elección para nuevos registros de entidad.

De forma predeterminada, de una entidad que tiene varios flujos de proceso de negocio definidos, el sistema aplica un flujo de proceso de negocio al nuevo registro de entidad con la lógica de varias fases siguiente:
1. Identifique todos los flujos de proceso de negocio aplicables al nuevo registro de entidad basándose en el atributo **Workflow.PrimaryEntity** de los registros de la definición de flujo de proceso de negocio.
2. Identifique las definiciones de flujo de proceso de negocio a las que el usuario actual tiene acceso. Para obtener información acerca de cómo se determina y administra el acceso a un flujo de proceso de negocio, consulte [Administrar la seguridad de los flujos de proceso de negocio](#BPFSecurity), anteriormente en este tema.<br/>  
3. Todas las definiciones de flujo de proceso de negocio en el sistema están sujetas a un pedido global por entidad. El orden del flujo de proceso de negocio se almacena en el atributo **Workflow.ProcessOrder**. Las definiciones de flujo de proceso de negocio para una entidad se ordenan basándose en este pedido, y se selecciona el que tenga el menor el valor de pedido.
4. Por último, si el registro de entidad se crea a partir de una aplicación de negocio (módulo de la aplicación), se aplica un nivel más de filtrado para seleccionar el flujo de proceso de negocio que se aplicará automáticamente al nuevo registro de entidad. Cuando trabajan en una aplicación, los usuarios pueden tener acceso únicamente a las entidades, a los flujos de proceso de negocio, a las vistas y a los formularios pertinentes a los que tienen acceso en virtud de los roles de seguridad asignados a la aplicación de negocio. 
    - Si la aplicación de negocio no contiene ningún flujo de proceso de negocio, el flujo de proceso de negocio se aplica según se explica hasta el paso 3.
    - Si la aplicación de negocio tiene uno o varios flujos de proceso de negocio, solo corresponderían los flujos de proceso de negocio presentes en la aplicación. En este caso, cuando el usuario está trabajando en un contexto de la aplicación de negocio, la lista de flujos de proceso de negocio del paso 3 se filtra aún más para los que sean parte de la aplicación de negocio que se encuentra en el módulo de la aplicación, y se ordenan en función del pedido de proceso. 
    - Si no hay ningún flujo de proceso de negocio disponible en una aplicación de negocio para la entidad o uno al que el usuario tenga acceso, ningún flujo de proceso de negocio se aplica para el nuevo registro de entidad.

Puede anular la lógica predeterminada de los flujos de procesos de negocio que se aplicarán automáticamente a los nuevos registros de entidad. Para ello, establezca el atributo **ProcessId** de la entidad en uno de los siguientes valores cuando cree un nuevo registro de entidad:
- Establezca **Guid.Empty** para omitir la configuración de un flujo de proceso de negocio para nuevos registros de entidad. Es posible que desee hacerlo si crea registros de entidad de manera masiva, pero no desea que se les aplique el flujo de proceso de negocio.
- Establézcalo en una entidad específica de flujo de proceso de negocio (como una referencia de entidad). En este caso, el sistema aplicará el flujo de proceso de negocio especificado, en lugar de la lógica predeterminada.

Si no establece un valor para el atributo **ProcessId** cuando crea un nuevo registro de entidad, el sistema aplicará la lógica predeterminada que se explicó anteriormente.

> [!NOTE]
> Anular la lógica predeterminada de los flujos de procesos de negocio que se aplican automáticamente a los nuevos registros de entidades solo se admite mediante programación. No puede hacerlo con la UI.

## <a name="legacy-process-related-attributes-in-entities"></a>Legado de atributos relacionados con el proceso en las entidades

Los atributos heredados relacionados con el proceso (como **ProcessId**, **StageId**, y **TraversedPath**) en entidades habilitadas para flujos de procesos de negocios ya están en desuso. La manipulación de atributos relacionados con el proceso (como ***y***) en entidades habilitadas para flujos de proceso de negocio no garantiza la coherencia del estado del flujo de proceso de negocio, y no es un escenario admitido. La forma recomendada es usar los atributos de entidad de flujo de proceso de negocio como se ha explicado anteriormente en la sección [Crear, vuelva, actualice, o eliminar registros de entidad de flujo de proceso de negocio (las instancias de proceso)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances)

La única excepción a esto es mediante programación modificando el atributo **ProcessId** cuando se crea un registro de entidad para reemplazar la aplicación predeterminada del flujo de proceso de negocio al nuevo registro como se explica en la sección anterior: [Aplicar el flujo de proceso de negocio cuando se crea un registro de entidad](#ApplyBPF).

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>Compatibilidad con la programación del lado cliente para los flujos de proceso de negocio  
 Existe un objeto del lado cliente que puede usar para interactuar con los flujos de proceso de negocio en los scripts de formulario. Los flujos de proceso de negocio desencadenan eventos del lado del cliente cada vez que un proceso se aplica a un registro, cambia la fase o cambia su estado a `Active`, `Finished`, o `Aborted`. Más información: [formContext.data.process (referencia de la API de cliente)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md).  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>Número máximo de procesos, fases y pasos  
 Por cada entidad, el valor predeterminado para el número máximo de flujos de proceso de negocio activados es de 10. Puede especificar un valor distinto mediante el atributo `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity`. Sin embargo, si el valor es superior a 10, verá una disminución en el rendimiento del sistema cuando cambia procesos o abre un registro que tiene un flujo de proceso de negocio asignado. Esto puede resultar más apreciable si los procesos abarcan varias entidades.  
  
 Los siguientes valores no se pueden personalizar:  
  
-   El número máximo de fases por entidad en el proceso es 30.  
  
-   El número máximo de pasos en cada fase es 30.  
  
-   El número máximo de entidades que pueden participar en el flujo de proceso es 5.  

