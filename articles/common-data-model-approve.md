---
title: Compilación de un bucle de aprobación con Common Data Service| Microsoft Docs
description: Cree una entidad, un flujo y una aplicación que funcionen conjuntamente para que los revisores pueden aprobar o rechazar archivos agregados a Dropbox.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: eab01a20f44f68a85601ff824175f1a506ebec87
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74361323"
---
# <a name="build-an-approval-loop-by-using-power-automate-and-the-microsoft-common-data-service"></a>Compilación de un bucle de aprobación mediante Power Automate y Microsoft Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Common Data Service puede proporcionar una forma de compilar flujos que tengan la información almacenada en una base de datos independiente de un flujo. El mejor ejemplo son las aprobaciones. Si almacena el estado de la aprobación en una entidad, el flujo puede funcionar encima.

En este ejemplo, se creará un proceso de aprobación que comienza cuando un usuario agrega un archivo a Dropbox. En ese momento, aparece la información del archivo en una aplicación, donde un revisor puede aprobar o rechazar el cambio. Cuando el revisor aprueba o rechaza el cambio, se envía un correo de notificación y los archivos rechazados se eliminan de Dropbox.

Si sigue los pasos que se describen en esta sección, compilará:

* un **entidad personalizada** que contendrá información acerca cada uno de los archivos agregado a Dropbox y si el estado del archivo es aprobado, rechazado o pendiente.
* un **flujo** que agrega información a la entidad personalizada cuando se agrega un archivo a Dropbox, envía un correo cuando el archivo se aprueba o se rechaza, y elimina los archivos rechazados. Estos pasos muestran cómo compilar un flujo desde cero, pero se puede crear un flujo similar desde una plantilla.
* una **aplicación** en la que un revisor puede aprobar o rechazar archivos agregados a Dropbox. Usará Power Apps para generar esta aplicación automáticamente según los campos de la entidad personalizada.

**Requisitos previos**

* Regístrese en [Power Automate](sign-up-sign-in.md) y [Power Apps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/).
* Cree conexiones a Dropbox y Office 365 Outlook, como se describe en [Manage your connections](https://powerapps.microsoft.com/tutorials/add-manage-connections/) (Administración de conexiones).

## <a name="build-the-entity"></a>Compilación de la entidad
1. Inicie sesión en [powerapps.com](https://make.powerapps.com).
2. Si no aparece la barra de navegación izquierda de forma predeterminada, haga clic en el icono con tres líneas horizontales en la esquina superior izquierda o púlselo.
   
    ![Abrir barra de navegación izquierda](./media/common-data-model-approve/hamburger-icon.png)
3. En la barra de navegación izquierdo, haga clic o pulse **Administrar** y, luego, haga clic o pulse **Entidades**.
   
    ![Administrar entidades](./media/common-data-model-approve/manage-entities.png)
4. Si se le pide, haga clic o pulse **Crear mi base de datos**.
   
    ![Crear base de datos](./media/common-data-model-approve/create-database.png)
5. Cerca de la esquina superior derecha, haga clic o pulse **Nueva entidad**.
   
    ![Crear entidad](./media/common-data-model-approve/new-entity.png)
   
    Si la ventana del explorador no está maximizada, este botón puede aparecer en otro lugar.
6. En **Nombre de entidad**, especifique un nombre que no contenga espacios y no tenga ninguna otra entidad de la base de datos.
   
    Para seguir este ejemplo exactamente, especifique **ReviewDropboxFiles**.
   
    ![Especificar nombre de entidad](./media/common-data-model-approve/entity-name.png)
7. En **Nombre para mostrar**, especifique un nombre descriptivo.
   
    ![Especificar nombre para mostrar](./media/common-data-model-approve/display-name.png)
8. Haga clic o pulse **Siguiente**.
   
    ![Botón Siguiente](./media/common-data-model-approve/next-button.png)

## <a name="add-fields-to-the-entity"></a>Adición de campos a la entidad
1. Cerca de la esquina superior derecha, haga clic o pulse **Agregar campo**.
   
    ![Agregar campo](./media/common-data-model-approve/add-field.png)
2. En la fila en blanco que aparece en la parte inferior de la lista de campos, establezca las propiedades de un campo de **Approver**. (Al establecer estas propiedades, para pasar a la siguiente columna presione la tecla TAB.)
   
   * En la columna **Nombre para mostrar**, escriba **Approver**.
   * En la columna **Nombre**, escriba **ApproverEmail**.
   * En la columna **Tipo**, haga clic en la opción **Email** (Correo electrónico).
   * En la columna **Requerido**, active la casilla.
     
     ![Campo Approver](./media/common-data-model-approve/approver-field.png)
3. En la siguiente fila, establezca las propiedades de un campo **Status**:
   
   * En la columna **Nombre para mostrar**, escriba **Status**.
   * En la columna **Nombre**, escriba **Status**.
   * En la columna **Tipo**, haga clic en la opción **Text** (Texto).
   * En la columna **Propiedades**, deje el valor predeterminado.
   * En la columna **Requerido**, active la casilla.
     
     ![Campo Status](./media/common-data-model-approve/status-field.png)
4. En la siguiente fila, establezca las propiedades de un campo **FileID**:
   
   * En la columna **Nombre para mostrar**, escriba **File identifier**.
   * En la columna **Nombre**, escriba **FileID**.
   * En la columna **Tipo**, haga clic en la opción **Text** (Texto).
   * En la columna **Propiedades**, deje el valor predeterminado.
   * En la columna **Unique** (Único), seleccione la casilla.
   * En la columna **Requerido**, active la casilla.
     
     ![Campo FileID](./media/common-data-model-approve/fileid-field.png)
5. Cerca del borde derecho, haga clic o pulse los puntos suspensivos (...) del campo **FileID** y, después, haga clic en **Establecer como campo de título** o púlselo.
   
    ![Establecer campo de título](./media/common-data-model-approve/set-title-field.png)
6. Cerca de la esquina inferior izquierda, haga clic en el botón **Crear** o púlselo.
   
    ![Crear una entidad](./media/common-data-model-approve/create-button.png)
7. (opcional) Cuando la lista de entidades vuelva a aparecer, maximice la ventana del explorador, en caso de que no lo esté, y haga clic o pulse el encabezado de columna **Tipo** . La lista está ordenada y las entidades personalizadas, como la que acaba de crear, aparecen al principio.

## <a name="sign-in-and-create-a-flow"></a>Inicio de sesión y creación un flujo
1. Abra el [portal de Power Automate](https://flow.microsoft.com).
2. Maximice la ventana del explorador, si ya no está maximizada y haga clic o pulse la opción **Iniciar sesión**, que está cerca de la esquina superior derecha.
   
    ![Botón de inicio de sesión de Power Automate](./media/common-data-model-approve/signin-flow.png)
3. En el menú de la parte superior derecha seleccione el entorno en que creó la base de datos en powerapps.com.
   
    **Nota**: si no selecciona el mismo entorno, no verá la entidad.
4. Cerca de la esquina superior izquierda, haga clic en la opción **Mis flujos** o púlsela.
   
    ![Opción Mis flujos](./media/common-data-model-approve/myflows-button.png)
5. Cerca de la esquina superior derecha, haga clic o pulse **Create new flow** (Crear nuevo flujo).
   
    ![Botón Create new flow (Crear nuevo flujo)](./media/common-data-model-approve/create-flow.png)

## <a name="start-when-a-file-is-added"></a>Inicio cuando se agrega un archivo
1. En el cuadro que contiene **Buscar más desencadenadores**, escriba o pegue **Dropbox** y pulse o haga clic en **Dropbox - Cuando se crea un archivo**.
   
    ![Crear desencadenador](./media/common-data-model-approve/create-trigger.png)
2. En **Carpeta**, haga clic o pulse el icono de la carpeta y navegue a la carpeta a la que se van a agregar los archivos.
   
    ![Elegir carpeta](./media/common-data-model-approve/folder-icon.png)

## <a name="add-data-to-the-entity"></a>Adición de datos a la entidad
1. Haga clic o pulse **Nuevo paso** y, después, **Agregar una acción**.
   
    ![Agregar una acción](./media/common-data-model-approve/add-action.png)
2. En el cuadro que contiene **Buscar más acciones**, escriba o pegue **Common Data Service** y, después, haga clic o pulse **Common Data Service - Create object**.
   
    ![Crear un objeto en Common Data Service](./media/common-data-model-approve/cdm-create-object.png)
3. En **The entity** (La entidad), escriba o pegue **Review**, y haga clic en **Review Dropbox files** (Revisar archivos de Dropbox).
   
    ![Elegir la entidad](./media/common-data-model-approve/choose-entity-flow.png)
4. En **Título**, haga clic o pulse el cuadro y, después, **Nombre de archivo** en la lista de tokens de parámetro para agregar ese token al campo.
   
    ![Agregar token de nombre de archivo](./media/common-data-model-approve/add-filename-token.png)
5. En **Approver**, escriba o pegue la dirección de correo electrónico de la persona que va a revisar los archivos.
   
    **Nota:** para facilitar la prueba del flujo, especifique su propia dirección. Puede cambiarla más adelante, cuando el flujo esté listo para su uso real.
   
    ![Agregar el aprobador](./media/common-data-model-approve/add-approver.png)
6. En **Status**, escriba o pegue **Pending**.
   
    ![Agregar estado predeterminado](./media/common-data-model-approve/add-default-status.png)
7. En **File Identifier**, haga clic o pulse el cuadro y, después, **File identifier** en la lista de tokens de parámetro para agregar ese token al campo.
   
    ![Agregar el token File identifier](./media/common-data-model-approve/add-file-identifier.png)

## <a name="check-whether-the-file-has-been-reviewed"></a>Comprobación de si el archivo se ha revisado
1. En la acción **Create object**, haga clic o pulse **Nuevo paso**, **Más**, **Agregar una instrucción Do Until**.
   
    ![Agregar una instrucción Do Until](./media/common-data-model-approve/add-do-until.png)
2. En la esquina superior izquierda de la acción **Do until**, haga clic o pulse el cuadro que contiene **Elegir un valor**.
   
    ![Elegir un valor](./media/common-data-model-approve/choose-value.png)
   
    **Nota:** si la ventana del explorador no está maximizada, haga clic o pulse el cuadro superior que contiene **Elegir un valor**.
3. En **Salidas desde Cuando se crea un archivo**, haga clic o pulse **Status** para agregar ese token de parámetro al campo.
   
    ![Agregar token Status](./media/common-data-model-approve/add-status.png)
4. Abra la lista que está cerca del centro de la acción **Do until** y haga clic en **no es igual a**, o púlselo.
   
    ![Especificar no es igual a](./media/common-data-model-approve/is-not-equal.png)
5. En la esquina superior derecha de la acción **Do until**, escriba o pegue **Pending** en el cuadro que contiene **Elegir un valor**.
   
    ![Especificar el estado que se inspecciona](./media/common-data-model-approve/do-until-not-pending.png)
   
    **Nota:** si la ventana del explorador no está maximizada, haga clic o pulse el cuadro inferior que contiene **Elegir un valor**.
6. Cerca de la parte inferior de la acción **Do until**, haga clic en **Agregar una acción**.
   
    ![Agregar acción dentro de Do until](./media/common-data-model-approve/add-action-in-dountil.png)
7. En el cuadro que contiene **Buscar más acciones**, escriba **Common** y, después, haga clic o pulse **Common Data Service - Get object**.
   
    ![Obtener un objeto](./media/common-data-model-approve/get-object.png)
8. En **The namespace** (El espacio de nombres), haga clic o pulse su base de datos.
9. En **The entity** (La entidad), escriba o pegue **Review**, y haga clic en **Review Dropbox files** (Revisar archivos de Dropbox).
   
    ![Elegir entidad](./media/common-data-model-approve/choose-entity-flow.png)
10. En **Object id** (Id. de objeto), haga clic o pulse el cuadro y, luego, haga clic o pulse el token de parámetro **File identifier** para agregarlo al campo.
    
     ![Agregar identificador de objeto](./media/common-data-model-approve/add-object-id.png)

## <a name="check-whether-the-item-has-been-approved"></a>Compruebe si el elemento se ha aprobado
1. En la acción **Do Until**, haga clic o pulse **Nuevo paso** y, luego, **Agregar una condición**.
   
    ![Agregar condición](./media/common-data-model-approve/add-condition.png)
2. En la esquina superior izquierda de la condición, haga clic o pulse el cuadro que contiene **Elegir un valor**.
   
    ![Esquina superior izquierda de la condición](./media/common-data-model-approve/condition-upper-left.png)
   
    **Nota:** si la ventana del explorador no está maximizada, haga clic o pulse el cuadro superior que contiene **Elegir un valor**.
3. En **Outputs from Get object**, haga clic o pulse el token de parámetro **Status** para agregarlo al campo.
   
    ![Agregar estado a condición](./media/common-data-model-approve/add-status-to-condition.png)
4. En la esquina superior derecha de la condición, escriba o pegue **Aprobado** en el cuadro que contiene **Elegir un valor**.
   
    ![Compruebe si el estado se establece en aprobado](./media/common-data-model-approve/status-equals-approved.png)
   
    **Nota:** si la ventana del explorador no está maximizada, escriba o pegue **Aprobado** en el cuadro inferior que contiene **Elegir un valor**.

## <a name="send-notification-mail"></a>Enviar correo de notificación
1. En **En caso positivo, no hacer nada**, haga clic o pulse **Agregar una acción**.
   
    ![En caso positivo, agregar una acción](./media/common-data-model-approve/if-yes-action.png)
2. En el cuadro que contiene **Buscar más acciones**, escriba o pegue **enviar correo** y, luego, pulse o haga clic en **Office 365 Outlook - Enviar un correo electrónico**.
   
    ![En caso afirmativo, enviar correo](./media/common-data-model-approve/if-yes-send-mail.png)
3. En **A**, escriba o pegue la dirección de la persona a la que desee enviar una notificación cuando se acepta un elemento.
   
    **Nota:** para facilitar la prueba del flujo, especifique su propia dirección. Puede cambiarla cuando el flujo esté listo para su uso real.
   
    ![Destinatario de aprobación](./media/common-data-model-approve/approval-recipient.png)
4. En **Asunto**, haga clic o pulse el cuadro y, luego, haga clic o pulse el token de parámetro **File name** para agregarlo al campo.
   
    ![Especificar el nombre de archivo como asunto del correo electrónico](./media/common-data-model-approve/subject-is-file-name.png)
5. En **Cuerpo**, escriba o pegue **El elemento se ha aprobado.**
   
    ![Cuerpo de correo electrónico de aprobación](./media/common-data-model-approve/approval-body.png)
6. En **En caso negativo, no haga nada**, repita los pasos 1 a 5 de este procedimiento, salvo que en el cuerpo del mensaje de correo electrónico debe especificar **El elemento se ha rechazado.**
   
    ![Cuerpo del correo de rechazo](./media/common-data-model-approve/rejection-body.png)

## <a name="delete-rejected-files"></a>Eliminación de archivos rechazados
1. En los campos del correo de rechazo, haga clic en **Agregar una acción** o púlselo.
   
    ![Agregar acción de eliminación](./media/common-data-model-approve/add-delete-action.png)
2. En el cuadro que contiene **Buscar más acciones**, escriba o pegue **Dropbox** y pulse o haga clic en **Dropbox - Eliminar archivo**.
   
    ![Eliminar archivo de Dropbox](./media/common-data-model-approve/dropbox-delete-file.png)
3. En **Archivo**, haga clic o pulse el cuadro y, luego, haga clic o pulse el parámetro de token **File identifier** para agregarlo al campo.
   
    ![Identificar archivo que se elimina](./media/common-data-model-approve/identify-file-delete.png)

## <a name="save-the-flow"></a>Guardado del flujo
1. En la parte superior de la pantalla, escriba o pegue el nombre del flujo que va a crear y haga clic o pulse **Crear flujo**.
   
    ![Guardar flujo](./media/common-data-model-approve/save-flow.png)
2. Haga clic o pulse **Cerrar** y, después, **Listo**.
3. En Dropbox, agregue al menos dos archivos a la carpeta que especificó: uno para probar la aprobación y otra para probar el rechazo.

## <a name="build-the-app"></a>Compilación de la aplicación
1. Inicie sesión en [powerapps.com](https://make.powerapps.com) y, a continuación, haga clic o pulse **Nueva aplicación** cerca de la parte inferior de la barra de navegación izquierda.
   
    ![Crear una aplicación en un explorador](./media/common-data-model-approve/new-app-button.png)
2. En el cuadro de diálogo que aparece, haga clic o pulse en la opción para abrir Power Apps Studio para Windows o Power Apps Studio para web.
3. Si ha abierto Power Apps Studio para Windows, haga clic o pulse en **Nuevo** en la barra de navegación izquierda.
4. En **Create an app from your data** (Crear una aplicación a partir de sus datos), haga clic o pulse **Phone layout** (Diseño de teléfono) en el icono **Common Data Service**.
   
    ![Crear aplicación](./media/common-data-model-approve/afd-cdm.png)
5. En el cuadro **Search** (Buscar) escriba o pegue **Review**.
   
    ![Búsqueda de una entidad](./media/common-data-model-approve/search-entities.png)
6. En **Choose an entity** (Elegir una entidad), haga clic o pulse **Review Dropbox Files** (Revisar archivos de Dropbox).
   
    ![Elegir una entidad](./media/common-data-model-approve/choose-entity.png)
7. Cerca de la esquina inferior izquierda, haga clic en **Connect** (Conectar) o púlselo.
   
    ![Botón Conectar](./media/common-data-model-approve/connect-button.png)
8. Si aparece la pantalla inicial del paseo introductorio, realice este recorrido para familiarizarse con Power Apps (o bien haga clic o pulse en **Omitir**).
   
    ![Paseo introductorio](./media/common-data-model-approve/quick-tour.png)
   
    El paseo se puede realizar más adelante. Para ello, solo es preciso hacer clic o pulsar el icono del signo de interrogación que está cerca de la esquina superior izquierda y, después, **Take the intro tour** (Dar paseo introductorio) .
9. (opcional) Cerca la parte inferior de la pantalla, arrastre el control deslizante para aumentar el zoom, con el fin de que sea más fácil ver la aplicación.
   
    ![Control de zoom](./media/common-data-model-approve/zoom-control.png)

## <a name="customize-the-app"></a>Personalización de la aplicación
1. En la barra de navegación derecha, haga clic o pulse el diseño que incluya un encabezado y una descripción.
   
    ![Botón Conectar](./media/common-data-model-approve/choose-layout.png)
2. En la **pantalla de exploración**, haga clic o pulse inmediatamente debajo de la barra de búsqueda para seleccionar el control de cuadro de texto mayor.
   
    ![Seleccionar encabezado](./media/common-data-model-approve/select-header.png)
3. En el panel derecho, abra la lista inferior haciendo clic o pulsando su flecha abajo.
   
    ![Abrir lista desplegable](./media/common-data-model-approve/open-dropdown.png)
4. En la lista inferior, haga clic en **Title** (Título), o púlselo, para mostrar el nombre de los archivos agregados.
   
    ![Establecer datos de encabezado](./media/common-data-model-approve/set-heading.png)
5. En el panel derecho, abra la lista superior y haga clic o pulse **Status** (Estado) para mostrar el estado de cada archivo.
   
    ![Establecer datos del cuerpo](./media/common-data-model-approve/set-body.png)

## <a name="test-the-overall-solution"></a>Prueba de la solución global
1. En Power Apps, abra el modo Vista previa, para lo que debe hacer clic o pulsar en el botón de reproducir que hay cerca de la esquina superior izquierda.
   
    ![Abrir el modo de vista previa](./media/common-data-model-approve/open-preview.png)
2. En el primer archivo de la lista, haga clic o pulse la flecha para mostrar los detalles del mismo.
   
    ![Abrir pantalla de detalles](./media/common-data-model-approve/open-details.png)
3. En la esquina superior derecha, haga clic en el icono del lápiz, o púlselo, para cambiar los detalles del archivo.
   
    ![Abrir pantalla de edición](./media/common-data-model-approve/edit-record.png)
4. En el cuadro **Estado** escriba o pegue **Aprobado**.
   
    ![Aprobar un archivo](./media/common-data-model-approve/change-status.png)
5. En la esquina superior derecha, haga clic o pulse el icono de marca de verificación para guardar los cambios y volver a la pantalla de detalles.
   
    ![Guardar cambios](./media/common-data-model-approve/save-record.png)
   
    En unos minutos, recibirá un correo electrónico que le indicará que el archivo ha sido aprobado.
6. En la esquina superior derecha, haga clic o pulse el botón Atrás para volver a la pantalla de exploración.
   
    ![Volver a la pantalla de exploración](./media/common-data-model-approve/back-arrow.png)
7. En el otro archivo de la lista, haga clic o pulse la flecha para mostrar los detalles del mismo.
   
    ![Abrir pantalla de detalles](./media/common-data-model-approve/open-details.png)
8. En la esquina superior derecha, haga clic en el icono del lápiz, o púlselo, para cambiar los detalles del archivo.
   
    ![Abrir pantalla de edición](./media/common-data-model-approve/edit-record.png)
9. En el cuadro **Estado**, escriba o pegue **Rechazado** (o cualquier otra cosa, salvo **Aprobado**, como**Aprovado** o **Approobado**).
   
    ![Rechazar archivo](./media/common-data-model-approve/reject-file.png)
10. En la esquina superior derecha, haga clic o pulse el icono de marca de verificación para guardar los cambios y volver a la pantalla de detalles.
    
     ![Guardar cambios](./media/common-data-model-approve/save-record.png)
    
     En unos minutos, recibirá un correo electrónico que indica que se ha rechazado el archivo y este se eliminará de Dropbox.

