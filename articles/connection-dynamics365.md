---
title: Creación de un flujo con Dynamics 365 (en línea) | Microsoft Docs
description: Creación de flujos de trabajo útiles mediante una conexión de Dynamics 365 y Power Automate
services: ''
suite: flow
documentationcenter: na
author: Mattp123
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/06/2017
ms.author: matp
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f341adb319c20a201525bb6b7a8a0c54e2da5ea3
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195046"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Creación de un flujo mediante Dynamics 365 (con conexión)

Mediante un conector de Dynamics 365 se pueden crear flujos que se inician cuando se produce un evento en 365 Dynamics, o algún otro servicio, que realiza una acción en Dynamics 365, o en algún otro servicio. 

En Power Automate puede configurar flujos de trabajo automatizados entre sus aplicaciones y servicios preferidos para sincronizar archivos, obtener notificaciones, recopilar datos, etc. Para más información, consulte [Introducción a Power Automate](getting-started.md).

> [!IMPORTANT] 
> Para invocar un desencadenador de flujos, la entidad de Common Data Service utilizada con el flujo debe tener activada la opción **Change Tracking**. Más información: [Habilitar seguimiento de cambios para controlar la sincronización de datos](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization). 

## <a name="create-a-flow-from-a-template"></a>Creación de un flujo desde una plantilla
Para crear un flujo se puede utilizar una de las muchas plantillas disponibles, como en estos ejemplos:

* Cuando se crea un objeto en Dynamics 365, cree un elemento de lista en SharePoint.
* Cree registros de clientes potenciales de Dynamics 365 desde una tabla de Excel.
* Copie cuentas de Dynamics 365 a los clientes de Dynamics 365 for Operations.

Para crear un flujo desde una plantilla, siga estos pasos.

1. Inicie sesión en el [sitio web de Power Automate](https://flow.microsoft.com/).
2. Haga clic o pulse **Servicios** y, después, haga clic o pulse **Dynamics 365**.
3. Hay varias plantillas disponibles. Para empezar, seleccione la plantilla que desee.

## <a name="create-a-task-from-a-lead"></a>Creación de una tarea desde un cliente potencial
Si no hay una plantilla disponible para lo que necesita, cree un flujo desde el principio. En este tutorial, se muestra cómo crear una tarea en Dynamics 365 siempre que se crea un cliente potencial en Dynamics 365.

1. Inicie sesión en el [sitio web de Power Automate](https://flow.microsoft.com/).
2. Haga clic o pulse **Mis flujos** y, después, haga clic o pulse **Crear desde cero**.
3. En la lista de desencadenadores de flujo, haga clic o pulse **Dynamics 365 - Al crear un registro**.
4. Si se le solicita, inicie sesión en Dynamics 365.
5. En **Nombre de la organización**, seleccione la instancia de Dynamics 365 en que desea que el flujo escuche.
6. En **Nombre de entidad**, seleccione la entidad que desea escuchar, que actuará como desencadenador que inicia el flujo.
   
     Para este tutorial, seleccione **Leads**.
   
    ![Detalles del flujo](./media/connection-dynamics365/flow-details.png)
    > [IMPORTANTE] Para que el flujo se pueda desencadenar en la entidad de Dynamics 365, la definición de esta debe tener habilitado **Seguimiento de cambios**. Consulte [Habilitación del seguimiento de cambios para controlar la sincronización de datos](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization).
    
7. Haga clic o pulse **Nuevo paso** y, después, **Agregar una acción**.
8. Haga clic o pulse **Dynamics 365 – Al crear un registro**.
9. En **Nombre de la organización**, seleccione la instancia de Dynamics 365 en que desea que el flujo cree el registro. Tenga en cuenta que no es preciso que sea la instancia desde la que se desencadena el evento.
10. En **Nombre de entidad**, seleccione la entidad que creará un registro cuando se produzca el evento.
    
     Para este tutorial, seleccione **Tasks**.
11. Aparece el cuadro **Asunto**. Al hacer clic en él o pulsarlo, aparece un panel de contenido dinámico en el que puede seleccionar cualquiera de estos campos.
    
    * **Apellido**. Si selecciona este campo, el apellido del cliente potencial se insertará en el campo **Asunto** de la tarea cuando se crea.
    * **Tema**. Si selecciona este campo, el campo **Tema** del cliente potencial se insertará en el campo **Asunto** de la tarea cuando se crea.
    
    Para este tutorial, seleccione **Topic**.
    
    ![Flujo agregar tema](./media/connection-dynamics365/flow-addtopic.png)
    
    > **Sugerencia:** En el panel de contenido dinámico, haga clic en **Ver más** o pulse dicho vínculo para mostrar más campos asociados a la entidad. Por ejemplo, también puede rellenar el campo **Asunto** de la tarea con los campos **Nombre de la compañía**, **Cliente**, **Descripción**, o **Correo electrónico** del cliente potencial.
    > 
    > 
12. Haga clic o pulse **Crear flujo**.

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>Creación de una tarea de Wunderlist desde una tarea de Dynamics 365
En este tutorial, se muestra cómo crear una tarea en [Wunderlist](https://www.wunderlist.com) siempre que se crea una tarea en Dynamics 365. Wunderlist es un servicio basado en Internet que se puede usar para crear listas de tareas pendientes, agregar avisos o realizar un seguimiento de los recados.

1. Inicie sesión en el [sitio web de Power Automate](https://flow.microsoft.com/).
2. Haga clic o pulse **Mis flujos** y, después, haga clic o pulse **Crear desde cero**.
3. En la lista de desencadenadores de flujo, haga clic o pulse **Dynamics 365 - Al crear un registro**.
4. En **Nombre de la organización**, seleccione la instancia de Dynamics 365 en que desea que el flujo escuche.
5. En **Nombre de entidad**, seleccione la entidad que desea escuchar, que actuará como desencadenador para iniciar el flujo.
   
    Para este tutorial, seleccione **Tasks**.
6. Haga clic o pulse **Nuevo paso** y, después, **Agregar una acción**.
7. Escriba de *crear una tarea* y, después, haga clic o pulse **Wunderlist - Crear una tarea**.
8. En **Id. de la lista**, seleccione **Bandeja de entrada**.
9. En **Título**, seleccione **Asunto** en el panel de contenido dinámico.
10. Haga clic o pulse **Crear flujo**.  

## <a name="trigger-based-logic"></a>Lógica basada en desencadenadores
Los desencadenadores como **Al crear un registro**, **Al actualizar un registro** y **Al eliminar un registro** inician el flujo a los pocos minutos de que se produzca el evento.  En casos aislados, el flujo puede tardar hasta dos horas en desencadenarse.

Cuando se produce el desencadenador, el flujo recibe una notificación, pero se ejecuta en los datos que existen en el momento de ejecución de la acción.  Por ejemplo, si el flujo se desencadena cuando se crea un registro, y actualiza el registro dos veces antes de la ejecución de flujo, el flujo se ejecuta una sola vez con los datos más recientes.

## <a name="specify-advanced-options"></a>Especificación de opciones avanzadas
Cuando se agrega un paso a un flujo, se puede hacer clic o pulsar **Mostrar opciones avanzadas** para agregar un filtro o un pedido por la consulta que controla cómo se filtran los datos en el flujo.

Por ejemplo, puede usar una consulta de filtro para recuperar únicamente los contactos activos y puede ordenarlos por apellido. Para ello, escriba la consulta de filtro OData **statuscode eq 1** y seleccione **Apellidos** en el panel de contenido dinámico. Para más información acerca de las consultas de filtro y ordenar por, vea [MSDN: $filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) y [MSDN: $orderby](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2).

  ![Consulta de orderby de flujo](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Procedimientos recomendados cuando se usan las opciones avanzadas
Cuando se agrega un valor a un campo, debe coincidir con el tipo de campo independientemente de que escriba un valor o lo seleccione en el panel de contenido dinámico.

| Tipo de campo | Cómo se usa | Dónde se encuentra | Nombre | Tipo de datos |
| --- | --- | --- | --- | --- |
| Campos de texto |Los campos de texto requieren una sola línea de texto o contenido dinámico que es un campo de tipo texto. Entre los ejemplos se incluyen los campos **Categoría** y **Subcategoría**. |**Configuración** > **Personalizaciones** > **Personalizar el sistema** > **Entidades** > **Tarea** > **Campos** |**category** |**Una línea de texto** |
| Campos numéricos de tipo entero |Algunos campos requieren un entero o contenido dinámico que sea un campo de tipo entero. Algunos ejemplos son: **Porcentaje completado** y **Duración**. |**Configuración** > **Personalizaciones** > **Personalizar el sistema** > **Entidades** > **Tarea** > **Campos** |**percentcomplete** |**Número entero** |
| Campos de fecha |Algunos campos requieren que una fecha escrita en formato dd/mm/aaaa o contenido dinámico que sea un campo de tipo de fecha. Algunos ejemplos son: **Fecha de creación**, **Fecha de inicio**, **Inicio real**, **Último período de retención**, **Finalización real**, y **Fecha de vencimiento**. |**Configuración** > **Personalizaciones** > **Personalizar el sistema** > **Entidades** > **Tarea** > **Campos** |**createdon** |**Fecha y hora** |
| Campos que requieren un identificador de registro y un tipo de búsqueda |Algunos campos que hacen referencia a otro registro de entidad requieren tanto el identificador de registro como el tipo de búsqueda. |**Configuración** > **Personalizaciones** > **Personalizar el sistema** > **Entidades** > **Cuenta** > **Campos** |**accountid** |**Clave principal** |
|Conjunto de opciones|Los campos de Conjunto de opciones requieren pasar un valor entero conocido a este tipo de campo.  En el área de personalización de Dynamics 365, puede ver los conjuntos de opciones que respaldan el campo de entero junto con su etiqueta respectiva.|Configuración > Personalización > Personalizar el sistema > Entidades > Cuenta > Campos | Método de contacto preferido| Número entero|

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Más ejemplos de campos que requieren un identificador de registro y un tipo de búsqueda
Ampliemos la información de la tabla anterior, aquí hay más ejemplos de campos que no funcionan con los valores seleccionados de la lista de contenido dinámico. En su lugar, estos campos requieren que se especifiquen tanto un identificador de registro como un tipo de búsqueda en los campos de Power Apps.

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
2. En la barra de herramientas de acciones, haga clic o pulse **Emergente**
   ![registro emergente](./media/connection-dynamics365/popout.png) (o bien haga clic o pulse **ENVIAR UN VÍNCULO POR CORREO ELECTRÓNICO** para copiar la dirección URL completa en el programa de correo electrónico predeterminado).
   
    En la barra de direcciones del explorador web, la dirección URL contiene el identificador de registro entre los caracteres de codificación %7b y %7d.
   
   ![RecordId](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>Temas relacionados
[Solución de problemas en un flujo](fix-flow-failures.md)

[Preguntas y respuestas sobre Flow en su organización](organization-q-and-a.md)

[Preguntas más frecuentes](frequently-asked-questions.md)

