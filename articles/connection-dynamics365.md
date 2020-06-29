---
title: Crear un flujo con Dynamics 365 (online) | Microsoft Docs
description: El Dynamics 365 Connector está en desuso. Use en su lugar el conector de Common Data Service (Entorno actual) o el conector de Common Data Service.
services: ''
suite: flow
documentationcenter: na
author: JimDaly
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/31/2020
ms.author: matp
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 59eb50914015ffa76607b377963b616cbcc00ded
ms.sourcegitcommit: b77b16f15bceedc9caa948676bcd641bf0bcaf2c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "3413434"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Crear un flujo mediante Dynamics 365 (online)

> [!IMPORTANT]
> Las aplicaciones de Dynamics 365 (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing y Dynamics 365 Project Service Automation) usan [Common Data Service](/powerapps/maker/common-data-service/data-platform-intro) como origen de datos.
>
> El [Dynamics 365 Connector](/connectors/dynamicscrmonline/) está en desuso, pero seguirá funcionando hasta que se retire.
> Para obtener más información, consulte [Dynamics 365 Connector está en desuso](/power-platform/important-changes-coming#dynamics-365-connector-is-deprecated).
> 
> No use Dynamics 365 Connector para flujos nuevos. Use el [Conector de Common Data Service (entorno actual) ](/connectors/commondataserviceforapps/) siempre que pueda.
> Si el conector de Common Data Service (entorno actual) no se adapta a sus necesidades, use el [Conector de Common Data Service](/connectors/commondataservice/).
>
> El [Conector de Common Data Service (entorno actual)](/connectors/commondataserviceforapps/) debería ser su primera opción, puesto que proporciona más capacidad y mejor rendimiento. Sin embargo, actualmente no proporciona algunas de las capacidades que proporcionan los conectores de Dynamics 365 y de Common Data Service, como poder conectarse a múltiples entornos. El [Conector de Common Data Service](/connectors/commondataservice/) proporciona las mismas capacidades que Dynamics 365 Connector, pero además ofrece una mejora considerable de la fiabilidad.


Al usar Dynamics 365 Connector, puede crear flujos que se inician cuando se produce un evento en Dynamics 365, o en algún otro servicio, que a su vez realiza una acción en Dynamics 365 o en algún otro servicio. 

En Power Automate, puede configurar flujos de trabajo automatizados entre sus aplicaciones y servicios favoritos para sincronizar archivos, recibir notificaciones, recopilar datos y más. Para obtener más información, vea [Empezar a usar Power Automate](getting-started.md).

> [!IMPORTANT] 
> Para invocar un desencadenador de Power Automate, la entidad de Common Data Service utilizada con el flujo debe tener activada la opción **Seguimiento de cambios**. Más información: [Habilitar seguimiento de cambios para controlar la sincronización de datos](/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization). 

## <a name="create-a-flow-from-a-template"></a>Crear un flujo a partir de una plantilla.

Para crear un flujo a partir de una de las muchas plantillas disponibles, como en estos ejemplos:

* Cuando se crea un objeto en Dynamics 365, cree un elemento de lista en SharePoint.
* Crear registros de clientes potenciales de Dynamics 365 desde una tabla de Excel.
* Copiar cuentas de Dynamics 365 para clientes de Dynamics 365 for Operations.

Para crear un flujo desde una plantilla, siga estos pasos.

1. Inicie sesión en el [sitio web de Power Automate](https://flow.microsoft.com/).
2. Haga clic en (o pulse) **Servicios** y después haga clic en (o pulse) **Dynamics 365**.
3. Hay varias plantillas disponibles. Para empezar, seleccione la plantilla que desee.

## <a name="create-a-task-from-a-lead"></a>Creación de una tarea desde un cliente potencial

Si no hay una plantilla disponible para lo que necesita, cree un flujo desde el principio. En este tutorial se muestra cómo crear una tarea en Dynamics 365 siempre que se crea un cliente potencial en Dynamics 365.

1. Inicie sesión en el [sitio web de Power Automate](https://flow.microsoft.com/).
2. Haga clic en (o pulse) **Mis flujos** y después haga clic en (o pulse) **Crear desde cero**.
3. En la lista de desencadenadores de flujo, haga clic en (o pulse) **Dynamics 365 - Al crear un registro**.
4. Si se le solicita, inicie sesión en Dynamics 365.
5. En **Nombre de la organización**, seleccione la instancia de Dynamics 365 en que desea que el flujo escuche.
6. En **Nombre de entidad**, seleccione la entidad que desea escuchar, que actuará como el desencadenador que inicia el flujo.
   
     Para este tutorial, seleccione **Clientes potenciales**.
   
    ![Detalles de flujo](./media/connection-dynamics365/flow-details.png)
    > [IMPORTANTE] Para que el flujo se pueda desencadenar en la entidad de Dynamics 365, la definición de esta debe tener habilitado **Seguimiento de cambios**. Consulte [Habilitar seguimiento de cambios para controlar la sincronización de datos](/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)
    
7. Haga clic en (o pulse) **Nuevo paso** y después haga clic en (o pulse) **Agregar una acción**.
8. Haga clic en (o pulse) **Dynamics 365 – Al crear un registro**.
9. En **Nombre de la organización**, seleccione la instancia de Dynamics 365 en la que desea que el flujo cree el registro. Tenga en cuenta que no es preciso que sea la instancia desde la que se desencadena el evento.
10. En **Nombre de entidad**, seleccione la entidad que creará un registro cuando se produzca el evento.
    
     Para este tutorial, seleccione **Tareas**.
11. Aparece el cuadro **Asunto**. Al hacer clic en él o pulsarlo, aparece un panel de contenido dinámico en el que puede seleccionar cualquiera de estos campos.
    
    * **Apellidos**. Si selecciona este campo, el apellido del cliente potencial se insertará en el campo **Asunto** de la tarea cuando se crea.
    * **Tema**. Si selecciona este campo, el campo **Tema** del cliente potencial se insertará en el campo **Asunto** de la tarea cuando se crea.
    
    Para este tutorial, seleccione **Tema**.
    
    ![Flujo agregar tema](./media/connection-dynamics365/flow-addtopic.png)
    
    > **Sugerencia:** en el panel de contenido dinámico, haga clic en (o pulse) **Ver más** para mostrar más campos asociados a la entidad. Por ejemplo, también puede rellenar el campo **Asunto** de la tarea con los campos **Nombre de la compañía**, **Cliente**, **Descripción**, o **Correo electrónico** del cliente potencial.
    > 
    > 
12. Haga clic en (o pulse) **Crear flujo**.

## <a name="trigger-based-logic"></a>Lógica basada en desencadenadores

Los desencadenadores como **Al crear un registro**, **Al actualizar un registro** y **Al eliminar un registro** inician el flujo a los pocos minutos de que se produzca el evento.  En casos aislados, el flujo puede tardar hasta dos horas en desencadenarse.

Cuando se produce el desencadenador, el flujo recibe una notificación, pero se ejecuta en los datos que existen en el momento de ejecución de la acción.  Por ejemplo, si el flujo se desencadena cuando se crea un registro, y actualiza el registro dos veces antes de la ejecución de flujo, el flujo se ejecuta una sola vez con los datos más recientes.

## <a name="specify-advanced-options"></a>Especificación de opciones avanzadas

Cuando se agrega un paso a un flujo, se puede hacer clic o pulsar **Mostrar opciones avanzadas** para agregar un filtro o un pedido por la consulta que controla cómo se filtran los datos en el flujo.

Por ejemplo, puede usar una consulta de filtro para recuperar únicamente los contactos activos y puede ordenarlos por apellido. Para ello, escriba la consulta de filtro OData **statuscode eq 1** y seleccione **Apellidos** en el panel de contenido dinámico. Para obtener más información sobre el filtro y el orden por consultas, vea [Consultar datos> Filtrar resultados](/powerapps/developer/common-data-service/webapi/query-data-web-api#filter-results) y [Datos de consulta> Resultados del pedido](/powerapps/developer/common-data-service/webapi/query-data-web-api#order-results).

  ![Consulta de orderby de flujo](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Procedimientos recomendados cuando se usan las opciones avanzadas

Cuando se agrega un valor a un campo, debe coincidir con el tipo de campo independientemente de que escriba un valor o lo seleccione en el panel de contenido dinámico.

| Tipo de campo | Cómo se usa | Dónde se encuentra | Nombre | Tipo de datos |
| --- | --- | --- | --- | --- |
| Campos de texto |Los campos de texto requieren una sola línea de texto o contenido dinámico que es un campo de tipo texto. Entre los ejemplos se incluyen los campos **Categoría** y **Subcategoría**. |**Configuración** > **Personalizaciones** > **Personalizar el sistema** > **Entidades** > **Tarea** > **Campos** |**categoría** |**Línea de texto única** |
| Campos numéricos de tipo entero |Algunos campos requieren un entero o contenido dinámico que sea un campo de tipo entero. Algunos ejemplos son **Porcentaje completado** y **Duración**. |**Configuración** > **Personalizaciones** > **Personalizar el sistema** > **Entidades** > **Tarea** > **Campos** |**percentcomplete** |**Número entero** |
| Campos de fecha |Algunos campos requieren una fecha escrita en formato dd/mm/aaaa o contenido dinámico que sea un campo de tipo de fecha. Algunos ejemplos son: **Fecha de creación**, **Fecha de inicio**, **Inicio real**, **Último período de retención**, **Finalización real** y **Fecha de vencimiento**. |**Configuración** > **Personalizaciones** > **Personalizar el sistema** > **Entidades** > **Tarea** > **Campos** |**createdon** |**Fecha y hora** |
| Campos que requieren un identificador de registro y un tipo de búsqueda |Algunos campos que hacen referencia a otro registro de entidad requieren tanto el identificador de registro como el tipo de búsqueda. |**Configuración** > **Personalizaciones** > **Personalizar el sistema** > **Entidades** > **Cuenta** > **Campos** |**accountid** |**Clave principal** |
|Conjunto de opciones|Los campos de Conjunto de opciones requieren pasar un valor entero conocido a este tipo de campo.  En el área de personalización de Dynamics 365, puede ver los conjuntos de opciones que respaldan el campo de entero junto con su etiqueta respectiva.|Configuración > Personalización > Personalizar el sistema > Entidades > Cuenta > Campos | Método de contacto preferido| Número entero|

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Más ejemplos de campos que requieren un identificador de registro y un tipo de búsqueda

Ampliemos la información de la tabla anterior; aquí hay más ejemplos de campos que no funcionan con los valores seleccionados de la lista de contenido dinámico. En su lugar, estos campos requieren que se especifiquen tanto un identificador de registro como un tipo de búsqueda en los campos de Power Apps.

* **Propietario** y **Tipo de propietario**.
  
  * El campo **Propietario** debe ser un identificador de registro de usuario o equipo válido.
  * **Tipo de propietario** debe ser **systemusers** o **teams**.
* **Cliente** y **Tipo de cliente**.
  
  * El campo **Cliente** debe ser una cuenta o un identificador de registro de contacto válidos.
  * **Tipo de cliente** debe ser **accounts** o **contacts**.
* **Referente a** y **Tipo referente a**.
  
  * El campo **Referente a** debe ser un identificador de registro válido, como una cuenta o un identificador de registro de contacto.
  * **Tipo referente a** debe ser el tipo de búsqueda para el registro, como **accounts** o **contacts**.

Este ejemplo agrega al campo **Referente a** de la tarea un registro de cuenta que corresponde al identificador de registro.

  ![recordId y tipo de cuenta de flujo](./media/connection-dynamics365/flow-recordid-account.png)

En este ejemplo también se asigna la tarea a un usuario concreto en función del identificador de registro del usuario.

  ![recordId y tipo de usuario de flujo](./media/connection-dynamics365/flow-recordid-user.png)

Para buscar el identificador de un registro, consulte [Búsqueda del identificador de registro](#find-the-records-id) en este mismo tema.

> **Importante:** los campos cuya descripción sea "Para uso interno" no deben contener ningún valor. Entre estos campos se incluyen **Ruta recorrida**, **Parámetros adicionales** y **Número de versión de regla de zona horaria.**
> 
> 

## <a name="find-the-records-id"></a>Búsqueda del identificador del registro

1. En la aplicación web Dynamics 365, abra un registro, como un registro de cuenta.
2. En la barra de herramientas de acciones, haga clic en (o pulse) **Emergente**
   ![registro emergente](./media/connection-dynamics365/popout.png) (o bien, haga clic en [o pulse] **ENVIAR UN VÍNCULO POR CORREO ELECTRÓNICO** para copiar la dirección URL completa en el programa de correo electrónico predeterminado).
   
    En la barra de direcciones del explorador web, la dirección URL contiene el identificador de registro entre los caracteres de codificación %7b y %7d.
   
   ![RecordId](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>Temas relacionados

[Solución de problemas en un flujo](fix-flow-failures.md)

[Preguntas y respuestas sobre Flow en su organización](organization-q-and-a.md)

[Preguntas más frecuentes](frequently-asked-questions.md)

