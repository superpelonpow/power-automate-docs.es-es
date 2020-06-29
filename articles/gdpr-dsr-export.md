---
title: Solicitudes de exportación del titular de los datos de acuerdo con el RGPD en Power Automate | Microsoft Docs
description: Obtenga información sobre cómo usar Power Automate para responder a solicitudes de exportación del titular de los datos de acuerdo con el RGPD.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: f9fee8a217cdec28f6a3b49dee6335c4f13a3d45
ms.sourcegitcommit: 2284143cf147beb7d6071fd8005a41298e51e493
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "3384948"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-power-automate"></a>Responder a las solicitudes de exportación del titular de los datos de acuerdo con el RGPD para Power Automate


Como parte de nuestro compromiso de colaborar con usted en su viaje hacia el Reglamento General de Protección de Datos (RGPD), hemos desarrollado documentación para ayudarle a prepararse. En esta documentación no solo se describe lo que estamos haciendo para prepararnos para el RGPD, sino que también se comparten ejemplos de pasos que se pueden adoptar actualmente para el cumplimiento de este reglamento al usar Power Automate.

## <a name="manage-export-requests"></a>Administración de la exportación de solicitudes

El *derecho de portabilidad de datos* permite a un titular de dato solicitar una copia de sus datos personales en un formato electrónico (es decir, en un "formato estructurado, de uso frecuente, legible por máquinas e interoperable") que se pueda transmitir a otro controlador de datos.

Power Automate ofrece las siguientes experiencias para buscar o exportar los datos personales para un determinado usuario:

* **Acceso a sitio web:** inicie sesión en el [Centro de administración de Power Apps](https://admin.powerapps.com/) o el [Centro de administración de Power Automate](https://admin.flow.microsoft.com/).

* **Acceso a PowerShell:** [cmdlets de PowerShell de administración de Power Apps](https://go.microsoft.com/fwlink/?linkid=871804).

|**Datos de clientes**|**Acceso al sitio web**|**Acceso a PowerShell**|
|-----------------|------------------|-------------------|
|Registros generados por el sistema|[Portal de confianza de servicios de Office 365](https://servicetrust.microsoft.com/)|
|Historial de ejecución|Creador de portal de Power Automate||
|Flows|Creador de portal de Power Automate||
|Permisos de flujo| Portal de creado e Power Automate y Centro de administración de Power Automate||
|Detalles de usuario||Cmdlets Power Apps|
|Conexiones|Creador de portal de Power Automate|Cmdlets Power Apps |
|Permisos de conexión|Creador de portal de Power Automate|Cmdlets Power Apps |
|Conectores personalizados|Creador de portal de Power Automate|Cmdlets Power Apps |
|Permisos de conector personalizado|Creador de portal de Power Automate|Cmdlets Power Apps |
|Puerta de enlace|Creador de portal de Power Automate|Cmdlets de PowerShell de puerta de enlace de datos local|
|Permisos de puerta de enlace|Creador de portal de Power Automate|Cmdlets de PowerShell de puerta de enlace de datos local|

## <a name="export-a-flow"></a>Exportación de un flujo

Un usuario final o un administrador al que se haya concedido acceso al flujo puede exportarlo siguiendo estos pasos:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com/).

1. Seleccione el vínculo **Mis flujos** y, a continuación, seleccione el flujo para exportar.

1. Seleccione **... Más** y, a continuación, seleccione **Exportar**.

    ![Exportación de flujo](./media/gdpr-dsr-export/export-flow.png)

1. Seleccione **Paquete (.zip)**.

El flujo estará ahora disponible como un paquete comprimido. Para obtener más información, consulte la entrada de blog sobre [cómo exportar e importar un flujo](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exportación de historial de ejecuciones

El historial de ejecuciones incluye una lista de todas las ejecuciones que se han producido para un flujo. Estos datos incluyen el estado del flujo, la hora de inicio, la duración y los datos de entrada/salida para los desencadenadores y las acciones.

Un usuario final o un administrador al que se haya concedido acceso al flujo a través del centro de administración de Power Automate puede exportar los datos siguiendo estos pasos:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com/).
1. Seleccione el vínculo **Mis flujos** y, a continuación, seleccione el flujo cuyo historial de ejecución desea exportar.
1. En el panel **HISTORIAL DE EJECUCIÓN**, seleccione **Ver todo**.

    ![Historial de ejecución](./media/gdpr-dsr-export/run-history.png)

1. Seleccione **Descargar CSV**.

    ![Descargar CSV](./media/gdpr-dsr-export/download-csv.png)

El historial de ejecuciones se descarga como un archivo .csv para que pueda abrirlo en Microsoft Excel o un editor de texto y analizar mejor los resultados.

## <a name="export-a-users-activity-feed"></a>Exportación de la fuente de actividad de un usuario

En [Power Automate](https://flow.microsoft.com/), la fuente de actividad muestra el historial de actividades, errores y notificaciones de un usuario. Cualquier usuario puede ver su fuente de actividad siguiendo estos pasos:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com/), seleccione el icono de campana cerca de la esquina superior derecha y, a continuación, seleccione **Mostrar todas las actividades**.

    ![Muestra de la fuente de actividades](./media/gdpr-dsr-export/show-activity-feed.png)

1. En la pantalla **Actividad**, copie los resultados y, después, péguelos en un editor de documentos como Microsoft Word.

    ![Muestra de la fuente de actividades](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exportación de las conexiones de un usuario

Las conexiones permiten a los flujos conectarse a las API, las aplicaciones de SaaS y otros sistemas de terceros. Siga estos pasos para ver las conexiones:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com/), seleccione el icono de engranaje cerca de la esquina superior derecha y después seleccione **Conexiones**.

    ![Mostrar Contactos](./media/gdpr-dsr-export/show-connections.png)
1. Copie los resultados y, después, péguelos en un editor de documentos como Microsoft Word.

Cmdlets de PowerShell del administrador de Power Apps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>Exportación de una lista de permisos de conexión de un usuario

Un usuario puede exportar las asignaciones de roles de conexión para todas las conexiones a las que tiene acceso a través de la función Get-ConnectionRoleAssignment en los [cmdlets de PowerShell de Power Apps](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
Cmdlets de PowerShell del administrador de Power Apps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>Exportación de los conectores personalizados de un usuario

Los conectores personalizados complementan los conectores incluidos y permiten la conectividad con otras API y sistemas SaaS y de desarrollo personalizado. Puede transferir la propiedad de un conector personalizado o eliminarlo.

Siga estos pasos para exportar una lista de conectores de cliente:

1. Navegue hasta [Power Automate](https://flow.microsoft.com).
1. Seleccione el icono de **engranaje** de la configuración.
1. Seleccione **Conectores personalizados**.
1. Copie y pegue la lista de conectores personalizados en un editor de texto, como Microsoft Word.

    ![Exportación de conectores personalizados](./media/gdpr-dsr-export/export-custom-connectors.png)

Además de la experiencia proporcionada en Power Automate, puede usar la función Get-Connector de los [cmdlets de PowerShell de Power Apps](https://go.microsoft.com/fwlink/?linkid=871804) para exportar todos los conectores personalizados.

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

Cmdlets de PowerShell del administrador de Power Apps

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>Exportación de los permisos de conector personalizado de un usuario

Un usuario puede exportar todos los permisos de conector personalizado que haya creado a través de la función Get-ConnectorRoleAssignment en los [cmdlets de PowerShell de Power Apps](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

Cmdlets de PowerShell del administrador de Power Apps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>Exportación del historial de aprobaciones

El historial de aprobaciones de Power Automate captura un registro histórico de las aprobaciones que se han recibido o enviado para un usuario. Cualquier usuario puede ver su historial de aprobación siguiendo estos pasos:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com/), seleccione **Aprobaciones** y, a continuación, seleccione **Historial**.

    ![Visualización del historial de aprobaciones](./media/gdpr-dsr-export/view-approval-history.png)

1. Una lista muestra las aprobaciones que el usuario ha recibido. Los usuarios pueden mostrar las aprobaciones que enviaron seleccionando la flecha abajo junto a **Recibidas** y, a continuación, seleccionando **Enviadas**.

    ![Visualización de aprobaciones recibidas](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>Exportar los detalles del usuario
Los detalles del usuario ofrecen una vinculación entre un usuario y un inquilino específico. Un administrador puede exportar esta información si llama al cmdlet **Get-AdminFlowUserDetails** y pasa el identificador de objeto para el usuario.

Cmdlets de PowerShell del administrador de Power Apps

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>Exportar la configuración de puerta de enlace
Las respuestas a las solicitudes de exportación del interesado para puertas de enlace de datos locales se pueden encontrar [aquí](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

