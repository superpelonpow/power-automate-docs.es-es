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
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74363278"
---
# <a name="work-with-business-process-flows-using-code"></a>Uso de flujos de proceso de negocio con código
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Un *flujo de proceso de negocio* permite crear procesos de negocio de ventas, servicio y otros tipos más eficaces y simplificados. Crea una visualización del proceso de negocio mediante la colocación de controles especiales en la parte superior de los formularios de entidad. Se guía a los usuarios por las distintas fases de ventas, marketing o procesos de servicio hacia su finalización. Cada proceso admite varias fases y pasos. Puede agregar o quitar pasos, cambiar el orden de las fases, o bien agregar entidades nuevas al flujo de proceso de negocio.  
  
Se pueden ejecutar varias instancias de flujo de proceso de negocio simultáneamente sobre el mismo registro de entidad. Los usuarios pueden cambiar entre instancias de proceso de negocio simultáneas y reanudar su trabajo en una etapa actual del proceso. 

En este tema se proporciona información sobre cómo trabajar mediante programación con los flujos de proceso de negocio.

> [!NOTE]
> No tendrá que escribir código para trabajar con los flujos de proceso de negocio. Para obtener información sobre el uso de la interfaz de usuario para crear y administrar flujos de proceso de negocio, vea [Información general sobre flujos de proceso de negocio](../business-process-flows-overview.md).  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>Requisitos previos para el flujo de proceso de negocio 

En el flujo de proceso de negocio pueden participar entidades personalizadas y entidades que tengan formularios de interfaz de usuario actualizados. Las entidades de interfaz de usuario actualizada tienen la propiedad <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> establecida en `true`. 

Para habilitar una entidad para el flujo de proceso de negocio, establezca la propiedad <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> en `true`.

> [!IMPORTANT]
>  La habilitación de una entidad para el flujo de proceso de negocio es un proceso unidireccional. No se puede revertir.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>Definición de un flujo de proceso de negocio
  
Use el diseñador visual de flujos de proceso de negocio para definir un flujo de proceso de negocio. Más información: [Creación de un flujo de proceso de negocio](../create-business-process-flow.md)

De forma predeterminada, un registro de flujo de proceso de negocio se crea en el estado `Draft`.  

La definición de un flujo de proceso de negocio se almacena en la entidad <xref:Microsoft.Dynamics.CRM.workflow> y la información de fases para el flujo de proceso de negocio en la entidad <xref:Microsoft.Dynamics.CRM.processstage>.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>Activación de un flujo de proceso de negocio  
 Antes de poder usar el flujo de proceso, tendrá que activarlo. Para activarlo, debe tener el privilegio `prvActivateBusinessProcessFlow` para la entidad `Workflow`. Use el mensaje <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> para establecer el estado del registro de la entidad `Workflow` en `Activated`. Más información: [Realizar operaciones especializadas con Actualizar](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) 

 > [!NOTE]
 > También puede usar el diseñador de flujos de proceso de negocio para activar un flujo de proceso de negocio. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>Entidad de flujo de proceso de negocio 
 Después de activar una definición de flujo de proceso de negocio cambiando el estado del registro de la entidad `Workflow` correspondiente o mediante el diseñador de flujos de proceso de negocio, se crea automáticamente una entidad personalizada con el nombre siguiente para almacenar las instancias de flujo de proceso de negocio activadas: " *\<prefijo\_d\e_la\_solución\_activa>* _ *\<nombre\_único>* ", donde "nombre\_único" se deriva del nombre que especifique.  
  
 Por ejemplo, si especifica "Mi FPN personalizado" como el nombre de la definición de flujo de proceso de negocio y usa el publicador predeterminado (nuevo) para la solución activa, el nombre de la entidad personalizada que se crea para almacenar las instancias del proceso será "new_mi fpnpersonalizado".  
  
 Si el valor `uniquename` no está disponible para una definición de flujo de proceso de negocio, por ejemplo, si el flujo de proceso de negocio se ha importado como parte de la solución desde una versión anterior, el nombre predeterminado de la entidad personalizada será "`\<activesolutionprefix>_bpf_<GUID_BPF_Definition>`":  
  
> [!IMPORTANT]
>  Los registros de flujo de proceso de negocio de ejemplo usan las entidades del sistema para almacenar los registros de instancia de flujo de proceso de negocio correspondientes.  
>   
>  Pero en todas las definiciones de flujo de proceso de negocio que cree se usarán entidades personalizadas para almacenar sus registros de instancia como se explicó anteriormente. 

Puede recuperar el nombre de la entidad de flujo de proceso de negocio mediante cualquiera de las maneras siguientes:

- **Mediante la interfaz de usuario**: use la interfaz de usuario de personalización para ir a la entidad de flujo de proceso de negocio:

    ![](media/bpf-entity-name.png)
- **Mediante la API web**: use la solicitud siguiente:

    **Solicitud**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **Respuesta**
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

La entidad personalizada que se crea automáticamente al activar un flujo de proceso de negocio para almacenar instancias de flujo de proceso de negocio se ajusta al modelo de seguridad estándar del mismo modo que para cualquier otra entidad personalizada de Common Data Service. Esto implica que los privilegios concedidos en estas entidades definen los permisos de runtime de los usuarios para los flujos de proceso de negocio.

La entidad de flujo de proceso de negocio personalizada tiene el ámbito de la organización. Los privilegios normales de creación, recuperación, actualización y eliminación de esta entidad definen los permisos que tendrían los usuarios en función de sus roles asignados. De forma predeterminada, cuando se crea la entidad de flujo de proceso de negocio personalizada, solo los roles de seguridad **Administrador del sistema** y **Personalizador del sistema** tienen acceso a esta. Además, deberá conceder explícitamente permisos para la nueva entidad de flujos de proceso de negocio (por ejemplo, **Mi FPN personalizado**), a otros roles de seguridad según sea necesario.

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

En este momento, es posible que no obtenga ninguna instancia en la respuesta ya que no hay ninguna. Ejecute esta solicitud después de crear una instancia de una definición de flujo de proceso de negocio más adelante en este tema.

> [!NOTE]
> Para saber cómo recuperar el nombre de la entidad de flujo de proceso de negocio, vea la sección anterior, [Entidad de flujo de proceso de negocio](#business-process-flow-entity).
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>Creación de un registro de entidad de flujo de proceso de negocio (instancia de proceso) 

Puede crear un registro de la entidad de flujo de proceso de negocio (instancia de proceso) mediante programación si quiere cambiar a otro flujo de proceso de negocio para un registro de entidad sin usar la interfaz de usuario. 

Para crear un registro de entidad de flujo de proceso de negocio, tendrá que especificar los valores siguientes: 
- Para asociar el registro de entidad de flujo de proceso de negocio a un registro de entidad principal, establezca la propiedad de navegación de un solo valor mediante la anotación `@odata.bind`. Para averiguar el nombre de propiedad de navegación que apunta al registro de entidad principal para la definición del flujo de proceso de negocio, use el [documento $metadata de CSDL](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document). 
- Para asociar el registro de entidad de flujo de proceso de negocio a una fase válida especificada en la definición del flujo de proceso de negocio, establezca la propiedad de navegación de un solo valor mediante la anotación `@odata.bind`. Para averiguar el nombre de propiedad de navegación (normalmente `activestageid`) que apunta al registro de fase para la definición del flujo de proceso de negocio, use el [documento $metadata de CSDL](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document).

    Además, puede recuperar información sobre todas las fases de una definición de flujo de proceso de negocio mediante la solicitud de API Web siguiente, suponiendo que el identificador de la definición del flujo de proceso de negocio sea 2669927e-8ad6-4f95-8a9a-f1008af6956f:

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

A continuación, use la solicitud siguiente para crear una instancia de la definición de flujo de proceso de negocio para un registro de cuenta (ID=a176be9e-9a68-e711-80e7-00155d41e206) y establezca la fase activa como la primera de la instancia de proceso, S1 (ID=9a9185f5-b75b-4bbb-9c2b-a6626683b99b):

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

Tenga en cuenta que si quiere crear una instancia de la definición de flujo de proceso de negocio con la fase activa establecida como una fase ***distinta*** a la primera, también tendrá que proporcionar `traversedpath` en la solicitud. La ruta recorrida es la cadena delimitada por comas de los identificadores de fase de proceso que representan las fases visitadas de la instancia de flujo de proceso de negocio. La solicitud siguiente crea una instancia de un registro de cuenta (ID=679b2464-71b5-e711-80f5-00155d513100) y establece la fase activa como la segunda fase, S2 (ID=19a11fc0-3398-4214-8522-cb2a97f66e4b).

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

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>Actualización de un registro de entidad de flujo de proceso de negocio (instancia de proceso)

Puede actualizar una instancia de proceso para pasar a la fase siguiente o la anterior, abandonar una instancia de proceso, volver a activarla o finalizarla. 

#### <a name="stage-navigation"></a>Navegación entre fases

Para navegar a otra fase, tendrá que actualizar un registro de instancia de proceso para cambiar su identificador de fase activa y actualizar la ruta recorrida en consecuencia. Tenga en cuenta que solo se debe pasar a la fase siguiente o la anterior mientras se actualiza una instancia de flujo de proceso de negocio.

Para realizar la navegación entre fases, necesitará el identificador de la instancia de flujo de proceso de negocio que quiera actualizar. Para recuperar todas las instancias del flujo de proceso de negocio, vea [Recuperación de todos los registros (instancias) de una entidad de flujo de proceso de negocio](#retrieve-all-the-records-instances-for-a-business-process-flow-entity) anteriormente.

Suponiendo que el identificador de la instancia de proceso que quiere actualizar sea dc2ab599-306d-e811-80ff-00155d513100, use la solicitud siguiente para actualizar la fase activa de S1 a S2:

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

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>Cambio del estado de una instancia de proceso: Anular, Reactivar o Finalizar 

Una instancia de proceso puede tener uno de los estados siguientes: **Activo**, **Finalizada** o **Anulada**. El estado se determina por los atributos siguientes en el registro de la instancia de proceso:

- **statecode**: muestra el estado de la instancia del proceso.

    |Valor|Etiqueta|
    |-----|-----|
    |0    |Activo|
    |1    |Inactivo|

- **statuscode**: muestra información sobre el estado de la instancia del proceso.

    |Valor|Etiqueta|
    |-----|-----|
    |1    |Activo|
    |2    |Finalizado|
    |3    |Anulado|

Por tanto, para **Anular** una instancia de proceso, use la solicitud siguiente para establecer los valores `statecode` y `statuscode` correctamente:

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
> Puede anular una instancia de proceso en cualquier etapa.

De forma similar, para volver a activar una instancia de proceso, reemplace los valores `statecode` y `statuscode` del código anterior con **0** y **1** respectivamente.

Por último, para establecer el estado una la instancia de proceso en **Finalizado**, que solo es posible en la última etapa de una instancia de proceso, reemplace los valores `statecode` y `statuscode` del código anterior con **0** y **2** respectivamente.

#### <a name="cross-entity-navigation"></a>Navegación entre entidades

Para la navegación entre entidades en este ejemplo, tendrá que establecer la etapa activa de la instancia de proceso en la última fase, S3 (ID=a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a), actualizar la ruta de recorrido en consecuencia, y establecer un registro de contacto como el registro de entidad principal en función de la definición de flujo de proceso de negocio.

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

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>Eliminación de un registro de entidad de flujo de proceso de negocio (instancia de proceso)

Use la siguiente solicitud de API web:

**Solicitud**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Respuesta**

Si el registro existe, obtendrá una respuesta normal con el estado 204 para indicar que la eliminación se realizó correctamente. Si no se encuentra la entidad, obtendrá una respuesta con el estado 404.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>Uso de los mensajes RetrieveProcessInstances y RetrieveActivePath

Use el mensaje `RetrieveProcessInstances` (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> o <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) para recuperar todas las instancias de flujo de proceso de negocio para un registro de entidad en todas las definiciones de proceso de negocio. Las instancias de flujo de proceso de negocio devueltas para una entidad se ordenan en función del atributo `modifiedon` de la instancia. Por ejemplo, la instancia de flujo de proceso de negocio que se haya modificado más recientemente será el *primer* registro de la colección devuelta. La instancia de flujo de proceso de negocio que se hay modificado más recientemente es la que está activa en la interfaz de usuario para un registro de entidad.  
  
Cada registro de instancia de flujo de proceso de negocio devuelto para un registro de entidad como resultado de usar el mensaje `RetrieveProcessInstances` almacena el identificador de la fase activa en el atributo `processstageid`, que se puede usar para buscar la fase activa y, después, ir a la anterior o la siguiente. Para ello, primero deberá encontrar la ruta de acceso activa de una instancia de flujo de proceso de negocio y las fases disponibles en la instancia de flujo de proceso mediante el mensaje `RetrieveActivePath` (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> o <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>).   
  
 Una vez que haya obtenido la fase activa y la información de ruta de acceso activa para una instancia de flujo de proceso de negocio, puede usar la información para pasar a una fase anterior o siguiente en la ruta de acceso activa. La navegación hacia delante entre fases se debe realizar de forma secuencial, es decir, solo debe avanzar a la siguiente fase en la ruta de acceso activa.   
  
 Para obtener el código de ejemplo completo en el que se muestra el uso de estos dos métodos y la navegación entre fases con el [Servicio de organización](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata), vea [Sample: Work with business process flows](sample-work-business-process-flows.md) (Ejemplo: Trabajar con flujos de proceso de negocio). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Aplicación del flujo de proceso de negocio al crear un registro de entidad

En esta sección se proporciona información sobre el comportamiento predeterminado para aplicar automáticamente flujos de proceso de negocio a nuevos registros de entidad creados en Common Data Service, y cómo se puede invalidar para aplicar un flujo de proceso de negocio de su elección a los nuevos registros de entidad.

De forma predeterminada, para una entidad que tiene varios flujos de proceso de negocio definidos, el sistema aplica un flujo de proceso de negocio al registro de entidad nuevo mediante la lógica de varios pasos siguiente:
1. Se identifican todos los flujos de proceso de negocio aplicables para el registro de entidad nuevo en función del atributo **Workflow.PrimaryEntity** de los registros de definición de flujo de proceso de negocio.
2. Se identifican las definiciones de flujo de proceso de negocio a las que el usuario actual tiene acceso. Para obtener información sobre cómo se determina y administra el acceso a un flujo de proceso de negocio, vea [Administración de la seguridad para los flujos de proceso de negocio](#BPFSecurity) anteriormente en este tema.<br/>  
3. Todas las definiciones de flujo de proceso de negocio del sistema están sujetas a un orden global por entidad. El orden del flujo de proceso de negocio se almacena en el atributo **Workflow.ProcessOrder**. Las definiciones de flujo de proceso de negocio de una entidad se ordenan en función de este orden, y se elige la que tenga el valor de orden menor.
4. Por último, si el registro de entidad se crea a partir de una aplicación empresarial (módulo de aplicación), se aplica un nivel más de filtrado para seleccionar el flujo de proceso de negocio que se va a aplicar de forma automática al nuevo registro de entidad. Cuando se trabaja en una aplicación, los usuarios solo pueden acceder a las entidades relevantes, flujos de proceso de negocio, vistas y formularios a los que tienen acceso en virtud de los roles de seguridad asignados a la aplicación empresarial. 
    - Si la aplicación empresarial no contiene ningún flujo de proceso de negocio, el flujo de proceso de negocio se aplica como se ha explicado hasta el paso 3.
    - Si la aplicación empresarial tiene uno o más flujos de proceso de negocio, solo serían aplicables los que estén presentes en la aplicación. En este caso, cuando el usuario está trabajando dentro de un contexto de aplicación empresarial, la lista de flujos de proceso de negocio del paso 3 se filtra hasta los que forman parte de la aplicación empresarial que están presentes dentro del módulo de aplicación, y se ordenan en función del orden de los procesos. 
    - Si no hay ningún flujo de proceso de negocio disponible en una aplicación empresarial para la entidad, o bien uno al que el usuario tenga acceso, no se aplica ningún flujo de proceso de negocio al nuevo registro de entidad.

Puede invalidar la lógica predeterminada de aplicación automática de los flujos de proceso de negocio a los registros de entidad nuevos. Para ello, establezca el atributo **ProcessId** de la entidad en uno de los valores siguientes al crear un registro de entidad:
- Establézcalo en **Guid.Empty** para omitir el establecimiento de un flujo de proceso de negocio para los registros de entidad nuevos. Es posible que quiera hacerlo si crea registros de entidad en masa, pero no quiere que se les aplique el flujo de proceso de negocio.
- Establézcalo en una entidad de flujo de proceso de negocio específica (como una referencia de entidad). En este caso, el sistema aplicará el flujo de proceso de negocio especificado en lugar de la lógica predeterminada.

Si no establece un valor para el atributo **ProcessId** durante la creación del registro de entidad, el sistema aplicará la lógica predeterminada como se explicó anteriormente.

> [!NOTE]
> La invalidación de la lógica predeterminada de aplicación automática de los flujos de proceso de negocio a los registros de entidad nuevos solo se admite mediante programación. No se puede hacer mediante la interfaz de usuario.

## <a name="legacy-process-related-attributes-in-entities"></a>Atributos heredados relacionados con los procesos en las entidades

Los atributos heredados relacionados con los procesos (como **ProcessId**, **StageId** y **TraversedPath**) en las entidades habilitadas para los flujos de proceso de negocio ya están en desuso. La manipulación de estos atributos heredados relacionados con los procesos para seleccionar como destino registros de entidad no garantiza la coherencia del estado de flujo de proceso de negocio y ***no*** es un escenario admitido. La manera recomendada es usar los atributos de la entidad de flujo de proceso de negocio como se explicó anteriormente en la sección [Creación recuperación, actualización y eliminación de registros de entidad de flujo de proceso de negocio (instancias de proceso)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances).

La única excepción es modificar mediante programación el atributo **ProcessId** durante la creación de un registro de entidad para invalidar la aplicación predeterminada del flujo de proceso de negocio para el nuevo registro, como se explicó en la sección anterior: [Aplicación del flujo de proceso de negocio al crear un registro de entidad](#ApplyBPF).

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>Compatibilidad con la programación del lado cliente para los flujos de proceso de negocio  
 Existe un objeto del lado cliente que puede usar para interactuar con los flujos de proceso de negocio en los scripts de formulario. Los flujos de proceso de negocio desencadenan eventos del lado cliente cada vez que un proceso se aplica a un registro, se cambia la fase o se cambia su estado a `Active`, `Finished` o `Aborted`. Más información: [formContext.data.process (referencia de la API de cliente)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md)  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>Número máximo de procesos, fases y pasos  
 Por cada entidad, el valor predeterminado para el número máximo de flujos de proceso de negocio activos es 10. Puede especificar otro valor mediante el atributo `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity`. Pero si el valor es mayor que 10, es posible que vea una disminución en el rendimiento del sistema al cambiar de procesos o al abrir un registro que tenga asignado un flujo de proceso de negocio. Esto puede ser especialmente importante si los procesos abarcan varias entidades.  
  
 Las opciones siguientes no son personalizables:  
  
-   El número máximo de fases por cada entidad del proceso es 30.  
  
-   El número máximo de pasos de cada fase es 30.  
  
-   El número máximo de entidades que pueden participar en el flujo de proceso es 5.  

