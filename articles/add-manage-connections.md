---
title: Información acerca de la conexión a datos mediante conexiones y puertas de enlace de datos locales | Microsoft Docs
description: Agregue o administre conexiones a SharePoint, SQL Server, OneDrive para la Empresa, Salesforce, Office 365, OneDrive, Dropbox, Twitter, Google Drive, etc.
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
ms.date: 02/15/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b4e087855890d7ca94a8288793494ce1e81826b2
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193298"
---
# <a name="manage-connections-in-power-automate"></a>Administración de conexiones en Power Automate

Si crea una conexión en Power Automate, podrá acceder fácilmente a los datos durante la compilación de un flujo. Power Automate incluye conexiones que se utilizan habitualmente, por ejemplo, SharePoint, SQL Server, Office 365, OneDrive para la Empresa, Salesforce, Excel, Dropbox, Twitter, etc. Las conexiones se comparten con Power Apps, por lo que cuando se crea una conexión en un producto, se muestra en el otro.

Por ejemplo, puede usar una conexión para realizar estas tareas:

* Actualizar una lista de SharePoint.
* Obtener datos de un archivo de Excel de una cuenta de OneDrive para la Empresa o Dropbox.
* Enviar correo electrónico en Office 365.
* Enviar un tweet.

Puede crear una conexión en varios escenarios, como estos:

* Creación de un [flujo desde una plantilla](get-started-logic-template.md)
* Creación de un [flujo desde cero](get-started-logic-flow.md) o actualización de un flujo existente
* Creación de una conexión en el [sitio web de Power Automate][1] directamente

En este tema se muestra cómo administrar conexiones en el [sitio web de Power Automate][1].

## <a name="add-a-connection"></a>Agregar una conexión
1. En el [sitio web de Power Automate][1], inicie sesión con su cuenta profesional o de organización.
2. Cerca de la esquina superior derecha, seleccione el icono del engranaje y, después, seleccione **Conexiones**.
   
    ![Seleccionar conexiones](./media/add-manage-connections/connections-menu.png)
3. Seleccione **Crear conexión**.
4. En la lista de **Conexiones disponibles**, seleccione la que desea configurar, como SharePoint.
5. Seleccione el botón **Crear conexión** y, escriba sus credenciales para configurar la conexión.

Cuando la conexión esté configurada, aparecerá en **Mis conexiones**.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>Conexión de los datos a través de una puerta de enlace de datos local
Actualmente, SQL Server y SharePoint Server admiten la puerta de enlace de datos local. Para crear una conexión que utilice una puerta de enlace:

1. Siga los pasos anteriores de este mismo tema para agregar una conexión.
2. En la lista de **conexiones disponibles**, seleccione **SQL Server** y, luego, active la casilla **Conectarse mediante una puerta de enlace de datos local**.
   
    ![Seleccionar puerta de enlace](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Las puertas de enlace de datos de Microsoft SharePoint admiten tráfico HTTP, pero no tráfico HTTPS.
   > 
   > 
3. Especifique las credenciales de la conexión y seleccione la puerta de enlace que desea utilizar.
   
    Para más información, consulte [Manage an on-premises data gateway](gateway-manage.md) (Administración de una puerta de enlace de datos local) y [Understand on-premises data gateways for Microsoft Flow](gateway-reference.md) (Información sobre las puertas de enlace de datos locales en Microsoft Flow).
   
    Cuando la conexión esté configurada, aparecerá en **Mis conexiones**.

## <a name="delete-a-connection"></a>Eliminación de una conexión
1. Vaya a la página **Mis conexiones** y seleccione el icono de la papelera de la conexión que desea eliminar.
   
    ![Eliminar conexión](./media/add-manage-connections/delete-connection.png)
2. Seleccione **Aceptar** para confirmar que desea eliminar la conexión.
   
    ![Confirmar eliminación](./media/add-manage-connections/delete-confirmation.png)

Cuando se elimina una conexión, se quita tanto de Power Apps como de Power Automate.

## <a name="update-a-connection"></a>Actualización de una conexión
Si una conexión no funciona porque los datos de la cuenta o la contraseña han cambiado, se puede actualizar.

1. En la página **Mis conexiones**, seleccione el vínculo **Comprobar contraseña** de la conexión que desea actualizar.
   
    ![Comprobar contraseña](./media/add-manage-connections/verify-password.png)
2. Cuando se le pida, actualice la conexión con las nuevas credenciales.

Cuando se actualiza una conexión, se hace tanto en Power Apps como en Power Automate.

## <a name="troubleshoot-a-connection"></a>Solución de problemas de una conexión
En función de las directivas de la organización, puede que tenga que usar la misma cuenta para iniciar sesión en Power Automate y para crear una conexión a SharePoint, Office 365 o OneDrive para la Empresa.

Por ejemplo, puede iniciar sesión en Power Automate con *yourname@outlook.com* , pero se le bloqueará al intentar conectarse SharePoint con *yourname@contoso.com* . En su lugar, puede iniciar sesión en Power Automate con *yourname@contoso.com* y podrá conectarse a SharePoint.

<!--Reference links in article-->
[1]: https://flow.microsoft.com
