---
title: Administración de puertas de enlace de datos locales | Microsoft Docs
description: Ver e instalar una puerta de enlace de datos local en Power Automate.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/13/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 33c2e0e6a3a35e23d0889cd19908a055cc7f5f5e
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297679"
---
# <a name="manage-an-on-premises-data-gateway-in-power-automate"></a>Administrar una puerta de enlace de datos local en Power Automate


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

* El nombre de usuario y la contraseña que usó para [registrarse](sign-up-sign-in.md) en Power Automate.
* Los permisos administrativos de una puerta de enlace.

  Tiene estos permisos de manera predeterminada para cada puerta de enlace que instale. Además, un administrador de otra puerta de enlace puede conceder estos permisos para esa puerta de enlace.
* Una licencia que admita puertas de enlace Para más información, consulte la sección "Conectividad" de la [página de precios](https://flow.microsoft.com/pricing/).

> [!TIP]
> Las puertas de enlace y las conexiones locales se pueden crear para [cualquier entorno](environments-overview-maker.md).

## <a name="install-a-gateway"></a>Instalación de una puerta de enlace

Para instalar una puerta de enlace, siga los pasos descritos en [Instalación de una puerta de enlace de datos local](/data-integration/gateway/service-gateway-install). Instale la puerta de enlace en modo estándar, ya que la _puerta de enlace de datos local (modo personal)_ solo está disponible para Power BI.

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
1. Seleccione **Distribuya las solicitudes por todas las puertas de enlace activas de este clúster.**.
1. Seleccione **Aplicar** para guardar los cambios.

Para más información, consulte [Información acerca de las puertas de enlace de datos locales de Microsoft Flow](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
