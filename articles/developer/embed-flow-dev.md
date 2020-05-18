---
title: Integre Power Automate con sitios web y aplicaciones | Microsoft Docs
description: Insertar de las experiencia de Power Automate en un sitio web o una aplicación.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 6ca077b6a7b0d04f184ddf8a716dd677713e0667
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297701"
---
# <a name="integrate-power-automate-with-websites-and-apps"></a>Integrar Power Automate con sitios web y aplicaciones
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Inserte Power Automate en la aplicación o sitio web mediante *widgets de flujo* para proporcionar a los usuarios una manera sencilla de automatizar sus tareas profesionales o personales.

Los widgets de flujo son iframes ubicados en un documento de host. Este documento señala a una página del diseñador de Power Automate. Estos widgets integran la funcionalidad específica de Power Automate en la aplicación de terceros.

Los widgets pueden ser sencillos. Por ejemplo, un widget que representa una lista de plantillas sin comunicación alguna entre el host y el iframe. Los widgets también pueden ser complejos. Por ejemplo, un widget que aprovisiona un flujo a partir de una plantilla y, después, lo desencadena a través de una comunicación bidireccional entre el host y el widget.

## <a name="prerequisites"></a>Requisitos previos

- Una **cuenta de Microsoft** o bien
- Una cuenta profesional o educativa

## <a name="use-the-unauthenticated-widget"></a>Uso del widget sin autenticar
Para usar el widget de plantillas no autenticadas, insértelo directamente en la aplicación host mediante un iframe. No se necesita el SDK de JS ni un token de acceso. 

### <a name="show-templates-for-your-scenarios"></a>Presentación de plantillas para sus escenarios
Para empezar, agregue este código para mostrar las plantillas de Power Automate en el sitio web:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}&category={category}"></iframe>
```

| Parámetro | Descripción |
| --- | --- |
| configuración regional |El código de región e idioma de cuatro letras para la vista de la plantilla. Por ejemplo, `en-us` representa el inglés de Estados Unidos, mientras que `de-de` representa el alemán. |
| search term |El término de búsqueda para las plantillas que desea mostrar en la vista. Por ejemplo, busque `wunderlist` para mostrar las plantillas de Wunderlist. |
| number of templates |El número de plantillas que desea mostrar en la vista. |
| destination |La página que se abre cuando los usuarios seleccionan la plantilla. Escriba `details` para mostrar los detalles de la plantilla, o bien `new` para abrir el diseñador de Power Automate. |
| categoría |Filtra por la categoría de plantilla determinada. | 
| parameters.{name} |Contexto adicional que se pasa en el flujo. |


Si el parámetro de destino es `new`, se abre el diseñador de Power Automate cuando los usuarios seleccionan una plantilla. Después, los usuarios pueden crear un flujo en el diseñador. Si quiere tener la experiencia completa desde el widget, vea la sección siguiente.

### <a name="passing-additional-parameters-to-the-flow-template"></a>Paso de parámetros adicionales a la plantilla de flujo

Si el usuario está en un contexto determinado en el sitio web o la aplicación, es posible que quiera pasar ese contexto al flujo. Por ejemplo, un usuario puede abrir una plantilla para *Notify me when an item is added to a list* (Notificarme cuando se agrega un elemento a una lista) mientras ve una lista concreta en Wunderlist. Siga estos pasos para pasar el identificador de la lista como *parámetro* al flujo:

1. Defina el parámetro de la plantilla de flujo antes de publicarlo. Así es un parámetro, `@{parameters('parameter_name')}`.
1. Pase el parámetro en la cadena de consulta del iframe src. Por ejemplo, agregue `&parameters.listName={the name of the list}` si tiene un parámetro denominado **listName**.

### <a name="full-sample"></a>Ejemplo completo

Para mostrar las cuatro plantillas principales de Wunderlist en alemán e iniciar el usuario con **myCoolList**, use este código:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>Uso de widgets de flujo autenticados

En la tabla siguiente se muestra la lista de widgets de Power Automate que admiten la experiencia completa desde el widget mediante el token de acceso de autenticación de usuario. Tendrá que usar el kit de desarrollo de software de Javascript (SDK de JS) de Power Automate para insertar los widgets y proporcionar el token de acceso de usuario requerido.

| Tipo de widget    | Característica admitida                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| flows          | Muestra una lista de flujos en una pestaña para los flujos personales y compartidos. Permite editar un flujo existente o crear uno a partir de una plantilla o en blanco. | 
| flowCreation   | Crea un flujo a partir de un identificador de plantilla proporcionado por la aplicación host.                                                                | 
| runtime        | Desencadena un flujo manual o de desencadenador híbrido que proporciona la aplicación host.                                                        | 
| approvalCenter | Inserta las solicitudes de aprobación y las aprobaciones enviadas.                                                                                        | 
| plantillas      | Muestra una lista de plantillas. El usuario elige una para crear un flujo.                                                                         | 

Use el SDK de Flow autenticado para permitir a los usuarios crear y administrar flujos directamente desde el sitio web o la aplicación (en lugar de navegar hasta Power Automate). Para usar el SDK autenticado, es preciso que el usuario inicie sesión con su cuenta de Microsoft o Azure Active Directory.

> [!NOTE]
> No hay forma alguna de ocultar la personalización de marca de Power Automate al usar los widgets.

## <a name="widget-architecture"></a>Arquitectura de widget

Los widgets de Power Automate funcionan mediante la inserción de un iframe que hace referencia a Power Automate en una aplicación host. El host proporciona el token de acceso que requiere el widget de Power Automate. El SDK de JS de Power Automate permite a la aplicación host inicializar y administrar el ciclo de vida del widget.

![Arquitectura de widget](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>Detalles del SDK de JS

El equipo de Power Automate proporciona el SDK de JS para facilitar la integración de widgets de Flow en aplicaciones de terceros. El SDK de JS de Flow está disponible como un vínculo público en el servicio Flow y permite que la aplicación host administre eventos del widget e interactúe con la aplicación Flow mediante el envío de acciones al widget. Las acciones y los eventos de widget son específicos del tipo de widget.

### <a name="widget-initialization"></a>Inicialización del widget

Es necesario agregar la referencia del SDK de JS de Flow a la aplicación host antes de inicializar el widget.

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

Para crear una instancia del SDK de JS, pase los valores opcionales de hostName y locale en un objeto JSON.

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US'
}); 
```

| Nombre     | Requerido/Opcional | Descripción                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | Opcionales          | Nombre de host de Power Automate, por ejemplo https://flow.microsoft.com        | 
| `locale`   | Opcionales          | Configuración regional del cliente para el widget (si no se especifica, el valor predeterminado es `en-Us`). | 


Una vez creada la instancia del SDK de JS, se puede inicializar e insertar un widget de Power Automate en un elemento primario de la aplicación host. Para ello, agregue una etiqueta div de HTML:

```html
<div id="flowDiv" class="flowContainer"></div>
```

A continuación, inicialice el widget de Power Automate con el método `renderWidget()` del SDK de JS. Asegúrese de proporcionar el tipo de widget y los valores correspondientes.

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flowDiv',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {}
});
```

Este es un estilo de ejemplo para el contenedor que se puede modificar para hacerlo coincidir con las dimensiones de la aplicación host.

```html
<head>
    <style>
        .flowContainer iframe {
            width: 400px;
            height: 1000px;
            border: none;
            overflow: hidden;
    }
    </style>
</head>
```

Estos son los parámetros para `renderWidget()`: 

| Parámetro        | Requerido/Opcional | Descripción                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | Obligatorios          | Identificador de un elemento DIV en la página de host donde se insertará el widget.                   | 
| `environmentId`    | Opcionales          | Los widgets necesitan un identificador de entorno. Si no proporciona una identificación, se utiliza un entorno predeterminado. | 
| `flowsSettings`    | Opcionales          | Objeto de configuración de Power Automate                                                                        | 
| `templateSettings` | Opcionales          | Objeto de configuración de plantilla                                                                    | 
| `approvalSettings` | Opcionales          | Objeto de configuración de aprobación                                                                    | 

### <a name="access-tokens"></a>Tokens de acceso

Después de que se ejecute el método `renderWidget()` del SDK de JS, el SDK de JS inicializa un iframe que apunta a la dirección URL del widget de Power Automate. Esta dirección URL contiene toda la configuración en los parámetros de cadena de consulta. La aplicación host tiene que obtener un token de acceso de Power Automate para el usuario (token JWT de Azure Active Directory con audiencia https://service.flow.microsoft.com) antes de inicializar el widget. El widget genera un evento `GET_ACCESS_TOKEN` para solicitar un token de acceso al host. El host debe controlar el evento y pasar el token al widget:

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

La aplicación host es responsable de mantener el token y de pasarlo con una fecha de caducidad válida al widget cuando se solicite. Si el widget está abierto durante períodos más largos, el host debe comprobar si el token ha caducado y actualizarlo si es necesario antes de pasarlo al widget.

### <a name="detecting-if-the-widget-is-ready"></a>Detección de si el widget está listo

Después de una inicialización correcta, el widget genera un evento para notificar que está listo. El host puede escuchar al evento `WIDGET_READY` y ejecutar cualquier código de host adicional.

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>Configuración del widget

### <a name="flowssettings"></a>FlowsSettings 

FlowsSettings se puede usar para personalizar la funcionalidad del widget de Power Automate.

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| Parámetro | Requerido/Opcional | Descripción | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | Obligatorios | Se usa el GUID de la plantilla cuando el usuario hace clic en el botón **Crear desde cero** en el widget de Flow. | 
| `flowsFilter` | Opcionales | El widget de Power Automate aplica el filtro proporcionado al enumerar los flujos. Por ejemplo, se muestran los flujos que hacen referencia a un sitio de SharePoint concreto. <br /> ```flowFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | Opcionales | Aparece de forma predeterminada la pestaña activa predeterminada que se va a mostrar en el widget de Power Automate. <br /> Por ejemplo, <br /> ```tab:'sharedFlows' ``` muestra la pestaña Equipo<br /> y ``` tab:'myFlows' ``` muestra la pestaña Mis flujos. |   

### <a name="templatessettings"></a>TemplatesSettings 

Se aplica a todos los widgets que permiten crear flujos a partir de una plantilla, incluidos Flows, FlowCreation y Templates.

```javascript
templatesSettings?: {
    defaultParams?: any;
    destination?: string;
    pageSize?: number;
    searchTerm?: string;
    templateCategory?: string;
    useServerSideProvisioning?: boolean;
    enableDietDesigner?: boolean;
};
 ```

| Parámetro |Requerido/Opcional | Descripción                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | Opcionales          | Parámetros de tiempo de diseño que se usan al crear un flujo a partir de una plantilla, por ejemplo: <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | Opcionales          | Los valores válidos son "new" o "details". Cuando se establece en "details", se muestra una página de detalles al crear un flujo a partir de una plantilla.     |
| `pageSize` | Opcionales          | El número de plantillas que se van a mostrar. El tamaño predeterminado es 6. | 
| `searchTerm` | Opcionales          | Se muestran plantillas que coinciden con el término de búsqueda proporcionado.| 
| `templateCategory` | Opcionales          | Se muestran las plantillas de una categoría específica.| 
 
### <a name="approvalcentersettings"></a>ApprovalCenterSettings

Se aplica a widgets ApprovalCenter.

 ```javascript
 approvalCenterSettings?: {
    approvalsFilter?: string;
    tab?: string;but
    autoNavigateToDetails?: boolean;
    showSimpleEmptyPage? boolean;
    hideLink?: boolean
};
 ```
| Parámetro | Requerido/Opcional | Descripción | 
|------------|-------------------|--------------| 
| `hideLink`| Opcionales | Cuando se establece en `true`, el widget oculta los vínculos de las aprobaciones recibidas y enviadas. | 
| `autoNavigateToDetails`| Opcionales | Cuando se establece en `true`, el widget abre de forma automática los detalles de aprobación cuando solo existe una aprobación. | 
| `approvalsFilter`| Opcionales | El widget de aprobación aplicará el filtro de aprobación especificado al enumerar las aprobaciones, por ejemplo: <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| Opcionales | La pestaña activa predeterminada que se va a mostrar en el widget de Flow. <br/> Valores válidos: "receivedApprovals", "sentApprovals". | 
| `showSimpleEmptyPage`| Opcionales | Muestra una página vacía cuando no hay ninguna aprobación. | 
| `hideInfoPaneCloseButton` | Opcionales | Oculta el botón Cerrar del panel de información (o el host ya tiene un botón Cerrar). | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>Eventos de widget

El widget de Power Automate admite eventos que permiten al host escuchar los eventos de ciclo de vida del widget. El widget de Power Automate admite dos tipos de eventos: eventos de notificación unidireccionales (por ejemplo, Widget\_Ready) y eventos generados desde el widget para capturar datos del host (Get\_Access\_Token). El host debe usar el método widget.listen() para escuchar eventos específicos generados desde el widget.

### <a name="usage"></a>Uso

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>Eventos admitidos por el tipo de widget

| Evento de widget      | Detalles                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | El widget se ha cargado correctamente.                                      | 
| `WIDGET_RENDERED`   | El widget se ha cargado y se ha completado la representación de la interfaz de usuario.                      | 
| `GET_ACCESS_TOKEN`  | Solicitud del widget para insertar el token de acceso de usuario.                      | 
| `GET_STRINGS`       | Permite al host reemplazar un conjunto de cadenas de interfaz de usuario que se muestran en el widget. | 

### <a name="runtime-widget"></a>Widget de tiempo de ejecución

| Evento de widget                    | Detalles                                     | Datos                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | Se ha desencadenado y se ha iniciado la ejecución del flujo.      |           | 
| `RUN_FLOW_COMPLETED`              | La ejecución del flujo se ha desencadenado correctamente.             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | El usuario ha hecho clic en el botón Listo durante la ejecución del flujo.       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | El usuario ha hecho clic en el botón Cancelar durante la ejecución del flujo.     |           | 
| `FLOW_CREATION_SUCCEEDED`         | El flujo se ha creado correctamente.           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | Se ha desencadenado cuando el host debía cerrar el widget. |       | 

### <a name="flow-creation-widget"></a>Widget de creación de flujos

| Evento de widget             | Detalles                                  | Datos  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | No se pudo crear el flujo.                     |       | 
| `WIDGET_CLOSE`             | Se ha desencadenado cuando el host debía cerrar el widget.  |       | 
| `TEMPLATE_LOAD_FAILED`     | No se pudo cargar la plantilla.              |       | 
| `FLOW_CREATION_SUCCEEDED`  | El flujo se ha creado correctamente.        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>Widget de aprobación

| Evento de widget                      | Detalles                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | El estado de la aprobación recibida ha cambiado.  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | El estado de la aprobación enviada ha cambiado.      | 

El evento **GET\_STRINGS** permite personalizar el texto de algunos de los elementos de interfaz de usuario que aparecen en el widget. Se pueden personalizar las cadenas siguientes:

| Clave de cadena                     | Uso en el widget                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | Texto que se muestra en el botón Crear flujo del widget de creación de flujos y tiempo de ejecución.                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | El valor inicial que se va a usar para el nombre del flujo en el widget de creación de flujos. Solo se usa cuando se habilita la opción allowCustomFlowName. | 
| `FLOW_CREATION_HEADER`           | El encabezado que se va a usar al crear un flujo en los widgets de tiempo de ejecución y creación de flujos.                                                    | 
| `INVOKE_FLOW_HEADER`             | El encabezado que se va a usar al invocar un flujo en el widget de tiempo de ejecución.                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | Texto que se muestra en el botón que se usa para invocar o ejecutar un flujo en el widget de tiempo de ejecución.                                                       | 

### <a name="example"></a>Ejemplo

Llamada a `widgetDoneCallback` pasando un objeto JSON con pares de clave y valor de clave de cadena y texto para reemplazar el valor predeterminado.

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>Acciones de widget

El host usa las acciones de widget para enviar un mensaje o una acción específica al widget. El SDK de JS del widget proporciona el método `notify()` para enviar un mensaje o una carga JSON al widget. Cada acción de widget admite una firma de carga específica.

### <a name="usage"></a>Uso

```javascript
widget.notify('<WIDGET_ACTION>', parameterMatchingParameterInterface)
    .then(result => console.log(result))
    .catch(error => console.log(error))
 ```

### <a name="example"></a>Ejemplo 

Invocación de un flujo mediante el envío del comando siguiente a un widget de tiempo de ejecución. 

```javascript
widget.notify('triggerFlow', { flowName: flowName, implicitData:implicitData });  
 ```

### <a name="runtime-widget"></a>Widget de tiempo de ejecución

| Acción de widget                               | Detalles                                                      | Interfaz de parámetros  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | Desencadena la ejecución de un flujo.                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | Desencadena la ejecución de un flujo mediante una plantilla.                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | Obtiene el esquema del desencadenador de un flujo.                               | `{   flowName: string, }` | 
| `closeWidget`                                 | Cancela cualquier actividad pendiente y genera un evento WIDGET_CLOSE. |                      | 

### <a name="flow-creation-widget"></a>Widget de creación de flujos

| Acción de widget                               | Detalles                                                      | Interfaz de parámetros  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | Crea un flujo para la plantilla seleccionada.                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | Crea un flujo para la definición de la plantilla seleccionada.          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | Cancela cualquier actividad pendiente y genera un evento WIDGET_CLOSE. |                      | 

### <a name="approval-widget"></a>Widget de aprobación

| Acción de widget  | Detalles                                           | Interfaz de parámetros  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | Cierra el panel de información en el que se muestran los detalles de la aprobación.  | N/D                  | 

## <a name="configuring-your-client-application"></a>Configuración de la aplicación cliente

Tendrá que configurar la aplicación cliente con ámbitos del servicio Flow (permisos delegados). Si en la aplicación de Azure Active Directory (AAD) que se utiliza para la integración de widgets se usa un flujo de autorización de "concesión de código", será necesario configurar la aplicación de AAD con permisos delegados que sean compatibles con Power Automate. Esto proporciona permisos delegados que permiten a la aplicación:

-   Administrar aprobaciones
-   Leer aprobaciones
-   Leer actividades
-   Administrar flujos
-   Leer flujos

Siga estos pasos para seleccionar uno o varios permisos delegados:

1.  Ir a https://portal.azure.com 
2.  Seleccione **Azure Active Directory**.
3.  En **Administrar**, haga clic en **Registros de aplicaciones**.
4.  Escriba la aplicación de terceros que se va a configurar para los ámbitos de servicio de Flow.
5.  Seleccione **Configuración**.
      ![Arquitectura de widget](../media/embed-flow-dev/AAD-App-Settings.png)
6. Haga clic en **Permisos necesarios** en **Acceso de API**/.
7. Seleccione **Agregar**.
8. Elija **Seleccionar una API**.
      ![Arquitectura de widget](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. Busque el **servicio de Power Automate** y selecciónelo. Nota: Para poder ver el servicio de Power Automate, el inquilino debe tener al menos un usuario de AAD que haya iniciado sesión en el portal de Flow (<https://flow.microsoft.com>)
10. Elija los ámbitos de Flow necesarios para la aplicación y después haga clic en **Guardar**.
      ![Arquitectura de widget](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

Ahora la aplicación obtendrá un token del servicio Flow que contiene los permisos delegados en la notificación \'scp' en el token de JWT.

## <a name="sample-application-embedding-flow-widgets"></a>Aplicación de ejemplo en la que se insertan widgets de Flow 

Se proporciona un ejemplo de aplicación de página única (SPA) de JavaScript en la sección de recursos para que pueda experimentar con la inserción de widgets de Flow en una página de host. Para usar la aplicación de ejemplo es necesario registrar una aplicación de AAD con el flujo de concesión implícita habilitado.

### <a name="registering-an-aad-app"></a>Registro de una aplicación de AAD

1.  Inicie sesión en el [portal Azure](https://portal.azure.com/).
2.  En el panel de navegación de la izquierda, haga clic en **Azure Active Directory** y, después, seleccione **Registros de la aplicación** (versión preliminar) \> Nuevo registro.
3.  Cuando aparezca la página **Registrar una aplicación**, escriba un nombre para la aplicación.
4.  En **Tipos de cuenta compatibles**, haga clic en **Cuentas en cualquier directorio organizativo**.
5.  En la sección **URL de redireccionamiento**, seleccione la plataforma web y establezca el valor en la dirección URL de la aplicación\' en función del servidor web.  Establezca este valor en http://localhost:30662/ para ejecutar la aplicación de ejemplo.
6.  Seleccione **Registrar**.
7.  En la página **Información general** de la aplicación, anote el valor de identificador (cliente) de la aplicación.
8.  En el ejemplo es necesario habilitar el [flujo de concesión implícito](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow). En el panel de navegación de la izquierda de la aplicación registrada, haga clic en **Autenticación**.
9.  En **Configuración avanzada**, en **Concesión implícita**, active las casillas **Tokens de id.** y **Tokens de acceso**. Los tokens de id. y los de acceso son necesarios, ya que en esta aplicación se debe iniciar la sesión de los usuarios y llamar a la API de Flow.
10. Seleccione **Guardar**.

### <a name="running-the-sample"></a>Ejecución del ejemplo
<!-- todo where should I download from? -->
1.  Descargue el ejemplo y cópielo en una carpeta local del dispositivo.
2.  Abra el archivo index.html de la carpeta FlowSDKSample y modifique `applicationConfig` para actualizar el valor `clientID` con el identificador de aplicación que ha registrado antes.
    ![Arquitectura de widget](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  La aplicación de ejemplo está configurada para usar los ámbitos de Flow **Flows.Read.All** y **Flow.Manage.All**. Puede configurar ámbitos adicionales si actualiza la propiedad **flowScopes** del objeto **applicationConfig**.
4.  Ejecute estos comandos para instalar la dependencia y ejecutar la aplicación de ejemplo:
    > \> npm install \> node server.js
5. Abra el explorador y, después, escriba http://localhost:30662.
6. Haga clic en el botón **Iniciar sesión** para autenticarse en AAD y adquirir un token de acceso de flujo.
7. El cuadro de texto **Token de acceso** contiene el token de acceso.
    ![Arquitectura de widget](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. Haga clic en **Load Flows widget** (Cargar widget de flujos) o **Load Templates widget** (Cargar widget de plantillas) para insertar los widgets correspondientes.
    ![Arquitectura de widget](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

[Vínculo de descarga](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip) de la aplicación de ejemplo.

## <a name="resources"></a>Recursos

### <a name="widget-test-pages"></a>Páginas de prueba de widgets

Obtenga más información sobre la configuración y la integración de widgets:

- Widget de plantillas: <[https://flow.microsoft.com/test/templateswidget/](https://flow.microsoft.com/test/templateswidget/)>
- Widget FlowCreation: <[https://flow.microsoft.com/test/flowcreationwidget/](https://flow.microsoft.com/test/flowcreationwidget/)>
- Widget de tiempo de ejecución: <[https://flow.microsoft.com/test/runtimewidget/](https://flow.microsoft.com/test/runtimewidget/)>
- Widget de centro de aprobaciones: <[https://flow.microsoft.com/test/approvalcenterwidget/](https://flow.microsoft.com/test/approvalcenterwidget/)>
- Widget de flujos: <[https://flow.microsoft.com/test/managewidget/](https://flow.microsoft.com/test/managewidget/)>

### <a name="supported-widget-locales"></a>Configuraciones regionales de widget admitidas

Si no se muestra la configuración regional inicializada, Flow usará de forma predeterminada la configuración regional admitida más cercana.

| Configuración regional     | Idioma                   | 
|------------|----------------------------| 
| bg-bg      | Búlgaro (Bulgaria)       | 
| ca-es      | Catalán (catalán)            | 
| cs-cz      | Checo (República Checa)     | 
| da-dk      | Danés (Dinamarca)           | 
| de-de      | Alemán (Alemania)           | 
| el-gr      | Griego (Grecia)             | 
| en-Us      | Inglés (Estados Unidos)    | 
| es-es      | Español (España)        | 
| et-ee      | Estonio (Estonia)         | 
| eu-es      | Euskera (euskera)             | 
| fi-fi      | Finés (Finlandia)          | 
| fr-fr      | Francés (Francia)            | 
| gl-es      | Gallego (España)           | 
| hi-HU      | Húngaro (Hungría)        | 
| hi-in      | Hindi (India)              | 
| hr-hr      | Croata (Croacia)         | 
| id-Id      | Indonesio (Indonesia)     | 
| it-It      | Italiano (Italia)            | 
| jp-Jp      | Japonés (Japón)           | 
| kk-kz      | Kazajo (Kazajistán)        | 
| ko-kr      | Coreano (Corea del Sur)             | 
| lt-LT      | Lituano (Lituania)     | 
| lv-lv      | Letón (Letonia)           | 
| ms-my      | Malayo (Malasia)           | 
| nb-no      | Noruego (bokmål)         | 
| nl-nl      | Neerlandés (Países Bajos)        | 
| pl-pl      | Polaco (Polonia)            | 
| pt-br      | Portugués (Brasil)        | 
| pt-pt      | Portugués (Portugal)      | 
| ro-ro      | Rumano (Rumanía)         | 
| ru-ru      | Ruso (Rusia)           | 
| sk-sk      | Eslovaco (Eslovaquia)          | 
| sl-si      | Esloveno (Eslovenia)       | 
| sr-cyrl-rs | Serbio cirílico (Serbia) | 
| sr-latn-rs | Serbio latino (Serbia)    | 
| sv-se      | Sueco (Suecia)           | 
| th-th      | Tailandés (Tailandia)            | 
| tr-tr      | Turco (Turquía)           | 
| uk-ua      | Ucraniano (Ucrania)        | 
| vi-vn      | Vietnamita (Vietnam)      |
