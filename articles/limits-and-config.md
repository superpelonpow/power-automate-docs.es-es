---
title: Límites y configuración | Microsoft Docs
description: Límites y configuración
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
ms.date: 05/30/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4361705779ab31b73206835380a648557f581e66
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74354676"
---
# <a name="limits-and-configuration-in-power-automate"></a>Límites y configuración de Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Este tema contiene información sobre los límites actuales y detalles de la configuración de flujos.

## <a name="request-limits"></a>Límites de solicitudes
Límites para una única solicitud saliente.

### <a name="timeout"></a>Tiempo de espera

| Nombre | Límite |
| --- | --- |
| Tiempo de espera de solicitud para las llamadas sincrónicas |120 segundos |
| Tiempo de espera de solicitud para las llamadas asincrónicas|Configurable. El máximo es 30 días. |

### <a name="message-size"></a>Tamaño del mensaje

| Nombre | Límite | Notas |
| --- | --- | --- |
| Tamaño del mensaje |100 MB |No todas las API admiten los 100 MB por completo. |
| Límite de la evaluación de expresión |131 072 caracteres |`@concat()`, `@base64()`, `string` no pueden superar este límite. |

### <a name="retry-policy"></a>Directiva de reintentos

| Nombre | Límite |
| --- | --- |
| Número de reintentos |90 | El valor predeterminado es 4. Para cambiar el valor predeterminado, use la configuración de la acción | 
| Reintentar retraso máximo |1 día | |
| Reintentar retraso mínimo |5 segundos | |

## <a name="run-duration-and-retention"></a>Duración y retención de la ejecución
Estos son los límites de una sola ejecución de flujo.

| Nombre | Límite | Notas |
| --- | --- | --- |
| Duración de la ejecución |30 días |Incluye flujos de trabajo con pasos pendientes, como aprobaciones. Después de 30 días, cualquier paso pendiente agotará el tiempo de espera. Las aprobaciones que agoten el tiempo de espera se quitarán del centro de aprobaciones. Si algún usuario intenta aprobar una solicitud que haya agotado el tiempo de espera, recibirá un mensaje de error. |
| Retención de almacenamiento |30 días |Contados desde la hora de inicio de la ejecución. |
| Intervalo de periodicidad mínimo |1 minuto | |
| Intervalo de periodicidad máximo |500 días | |
| Retención máxima del historial de ejecución |28 días, según las reglas del RGPD. | |
|Intervalo de aplazamiento mínimo: licencia Gratis y Plan 1|5 segundos||
|Intervalo de aplazamiento mínimo: licencia Plan 2|1 segundo||

## <a name="looping-and-debatching-limits"></a>Repetición en bucle y fragmentación de límites
Estos son los límites de una sola ejecución de flujo. En el caso de los límites diarios, consulte los [límites y las asignaciones de solicitudes](https://aka.ms/platformlimits).

| Nombre | Límite | Notas |
| --- | --- | --- |
| Elementos de Aplicar a cada: licencia gratuita|5000 |Puede usar la acción de filtrado para filtrar matrices de mayor tamaño según sea necesario. |
| Elementos de Aplicar a cada: licencias de Office 365, Plan 1, Plan 2, Por usuario y Por flujo|100 000 |Puede usar la acción de filtrado para filtrar matrices de mayor tamaño según sea necesario. |
| Iteraciones Until |5000 | |
| Elementos de SplitOn: licencia gratuita |5000 ||
| Elementos de SplitOn: licencias de Office 365, Plan 1, Plan 2, Por usuario y Por flujo |100 000 ||
| Aplicar a cada paralelismo |50 |De forma predeterminada, los bucles se ejecutan en secuencia (básicamente, el paralelismo es 1). Puede configurar hasta 50 en paralelo. |
| Ejecuciones de acciones por 5 minutos: licencias gratuita, de Office 365, Plan 1 y versiones de prueba | 2 000 | Además, puede distribuir una carga de trabajo por más de un flujo según sea necesario. |
|Ejecuciones de acciones por 5 minutos: licencias Plan de pago 2, Por usuario y Por flujo|100 000|Además, puede distribuir una carga de trabajo por más de un flujo según sea necesario.|
| Llamadas salientes a acciones simultáneas: licencias gratuita, de Office 365, Plan 1 y versiones de prueba | Más de 500 | Reduzca la cantidad de solicitudes simultáneas o la duración según sea necesario. |
| Ejecuciones de acciones por 24 horas: licencias gratuita, de Office365, Plan 1 y versiones de prueba | ~2500 | Reduzca la cantidad de solicitudes simultáneas o la duración según sea necesario. | 

## <a name="throughput-limits"></a>Límites de rendimiento

|Nombre|Límite|Notas|
|---|---|---|
|Punto de conexión en tiempo de ejecución - Número de llamadas de lectura permitidas por 5 minutos: licencias gratuita, de Office 365, Plan 1 y versiones de prueba|6 000||
|Punto de conexión en tiempo de ejecución - Número de llamadas de lectura permitidas por 5 minutos: licencias Plan de pago 2, Por usuario y Por flujo|60 000||
|Punto de conexión en tiempo de ejecución - Llamadas de invocación por 5 minutos: licencias gratuita, de Office 365, Plan 1 y versiones de prueba|4 500||
|Punto de conexión en tiempo de ejecución - Número de llamadas de invocación por 5 minutos: licencias de Plan de pago 2, Por usuario y Por flujo|45 000||
|Cantidad de rendimiento permitido por 5 minutos: licencias gratuita, de Office 365, Plan 1 y versiones de prueba|600 MB||
|Cantidad de rendimiento permitido por 5 minutos: licencias Plan de pago 2, Por usuario y Por flujo|6 GB||
|Cantidad de flujos de contenido que se pueden generar (entradas/salidas de acciones) por hora: licencias gratuita, de Office 365, Plan 1, Plan 2, Por usuario y Por flujo|200 GB||


## <a name="definition-limits"></a>Límites de definición
Estos son los límites de un solo flujo.

| Nombre | Límite | Notas |
| --- | --- | --- |
| Acciones por flujo de trabajo |500|Puede agregar flujos de trabajo anidados para ampliar este límite según sea necesario. |
| Profundidad permitida de anidamiento de acciones |8 |Puede agregar flujos de trabajo anidados para ampliar este límite según sea necesario. |
| Número máximo de caracteres por cada expresión |8192 | |
| `action`/`trigger` límite de nombre |80 | |
| `description` límite de longitud |256 | |

## <a name="sharepoint-limits"></a>Límites de SharePoint
Hay [limitaciones](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/) sobre cómo se puede usar Microsoft SharePoint con Power Automate y Power Apps.

## <a name="ip-address-configuration"></a>Configuración de la dirección IP
La dirección IP desde la que se envían solicitudes de Power Automate depende de la [región](regions-overview.md) donde está ubicado el [entorno](environments-overview-admin.md) que contiene el flujo. Actualmente no se publican FQDN disponibles para escenarios de flujo.

>[!IMPORTANT]
> Algunas llamadas que realiza un flujo pueden provenir de las direcciones IP que se enumeran en la documentación de [Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses). Algunos ejemplos de estas llamadas incluyen HTTP o HTTP + OpenAPI.

### <a name="logic-apps"></a>Logic Apps
Las llamadas realizadas desde un flujo van directamente a través del servicio Azure Logic Apps. Algunos ejemplos de estas llamadas incluyen HTTP o HTTP + OpenAPI. Consulte [la documentación de Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) adecuada según las direcciones IP que usa el servicio.

### <a name="connectors"></a>Conectores
Las llamadas realizadas desde un conector (por ejemplo, la API de SQL o la de SharePoint) procederán de las direcciones IP especificadas a continuación:

| Región | IP de salida |
| --- | --- |
| Asia Pacífico | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19 |
| Australia  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174 |
| Canadá | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152|
| Europa | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 137.117.161.181 |
| India  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218 |
| Japón | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248 |
| Sudamérica | 191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Reino Unido | 51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| Estados Unidos | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49|
| Versión preliminar (Estados Unidos)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157 |

Por ejemplo, use las direcciones IP que deba autorizar para Azure SQL Database.

### <a name="required-services"></a>Servicios necesarios
En la tabla siguiente se enumeran los servicios a los que se conecta Power Automate. Asegúrese de que ninguno de estos servicios están bloqueado en la red.

Dominios | Protocolos | Usos
--------|  ---------| -----
management.azure.com|HTTPS|Acceso a Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|HTTPS|Acceso a la biblioteca de autenticación de Active Directory (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|HTTPS|Acceso a la Graph API de Azure AD: para obtener información del usuario, como una foto del perfil.
*.azure-apim.net|HTTPS|Acceso al runtime para los conectores.
*.flow.microsoft.com|HTTPS|Acceso al sitio de Power Automate.
*.powerapps.com|HTTPS|Acceso al sitio de Power Apps.
*.azureedge.net|HTTPS|Acceso a la red CDN de Power Automate.
nps.onyx.azure.net|HTTPS|Acceso a NPS (Net Promoter Score).
webshell.suite.office.com|HTTPS|Acceso a Office para encabezados y búsqueda. Para más información, consulte [los intervalos y las direcciones URL de Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online).
