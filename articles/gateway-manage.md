---
title: Administración de puertas de enlace de datos locales | Microsoft Docs
description: Vea e instale una puerta de enlace de datos local en Power Automate.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 019d711771c10f360b1f5c7dab61aa432c827311
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74367119"
---
# <a name="manage-an-on-premises-data-gateway-in-power-automate"></a>Administración de una puerta de enlace de datos local en Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Instale y administre una puerta de enlace de datos local para integrar de forma segura varias aplicaciones que están en la nube con sus datos y aplicaciones locales a través de Power Automate.

Con una puerta de enlace, puede conectarse a datos locales a través de estas conexiones:

* Apache Impala
* Conectores personalizados creados por el usuario
* DB2
* Sistema de archivos
* Http con Azure AD
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* SharePoint
* SQL Server
* Teradata (versión preliminar)

> [!IMPORTANT]
> Las puertas de enlace de datos de Microsoft SharePoint admiten tráfico HTTP y HTTPS.

## <a name="prerequisites"></a>Requisitos previos

* El nombre de usuario y la contraseña que se usaron para [registrarse](sign-up-sign-in.md) en Power Automate.
* Permisos administrativos en una puerta de enlace.

  Tiene estos permisos de manera predeterminada para cada puerta de enlace que instale. Además, un administrador de otra puerta de enlace puede conceder estos permisos para esa puerta de enlace.
* Una licencia que admita puertas de enlace Para más información, consulte la sección "Conectividad" de la [página de precios](https://flow.microsoft.com/pricing/).

> [!NOTE]
> Las puertas de enlace y las conexiones locales solo puede crearlas en su [entorno predeterminado](environments-overview-maker.md).

## <a name="install-a-gateway"></a>Instalación de una puerta de enlace

Para instalar una puerta de enlace, siga los pasos descritos en [Instalación de una puerta de enlace de datos local](/data-integration/gateway/service-gateway-install). Instale la puerta de enlace en modo estándar, ya que la _puerta de enlace de datos local (modo personal)_ solo está disponible para Power BI.

## <a name="view-your-gateways"></a>Visualización de las puertas de enlace

En la esquina superior derecha del [sitio web de Power Automate](https://flow.microsoft.com), seleccione el icono del engranaje y, después, seleccione **Puertas de enlace**.

![Puerta de enlace bajo administración][1]

> [!NOTE]
> Si ha creado o se le ha concedido acceso a una puerta de enlace en Power Apps, aparecerá en la lista **Mis puertas de enlace** de Power Automate.

## <a name="cluster-your-gateways"></a>Agrupación de las puertas de enlace

Puede crear [clústeres de alta disponibilidad de instalaciones de puerta de enlace de datos local](/data-integration/gateway/service-gateway-high-availability-clusters) para evitar los puntos de error únicos en el acceso a los recursos de datos locales.

De forma predeterminada, Power Automate usa la puerta de enlace principal en el clúster. Si la puerta de enlace principal no está disponible, el servicio cambia a la siguiente puerta de enlace del clúster, y así sucesivamente.

Una vez que haya configurado un clúster de puerta de enlace, puede permitir que el tráfico se distribuya en todas las puertas de enlace del clúster.

Siga estos pasos para distribuir el tráfico a través de las puertas de enlace:

1. Seleccione **Datos** en la barra de navegación del lado izquierdo.
1. Seleccione **Puertas de enlace**.
1. Seleccione cualquiera de las puertas de enlace.
1. Seleccione **Distribuya las solicitudes por todas las puertas de enlace activas de este clúster.** .
1. Seleccione **Aplicar** para guardar los cambios.

Para más información, consulte [Información acerca de las puertas de enlace de datos locales de Microsoft Flow](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
