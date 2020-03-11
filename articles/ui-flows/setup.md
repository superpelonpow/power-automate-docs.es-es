---
title: Configuración de flujos de trabajo de interfaz de usuario en el dispositivo | Microsoft Docs
description: Configuración de flujos de trabajo de interfaz de usuario en el dispositivo
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
ms.date: 02/27/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1cf0dee7576111a696f8486f36aa5a2cdd2eeebf
ms.sourcegitcommit: 26cda5060446812f3725ccd4fe435839088f50fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "78244245"
---
# <a name="set-up-ui-flows"></a>Configuración de los flujos de la interfaz de usuario

[Este tema es documentación preliminar y está sujeto a cambios].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

> [!IMPORTANT]
> La característica de flujos de la interfaz de usuario se está implementando actualmente en las regiones. Si no ve la característica en el entorno, no puede crear flujos de interfaz de usuario o recibe un error al tratar de ejecutarla en un flujo, vuelva a intentarlo más tarde.

Antes de poder usar el dispositivo para crear flujos de interfaz de usuario, debe asegurarse de que cumple los requisitos que se describen aquí.

> [!TIP]
> Antes de crear un flujo de interfaz de usuario, consulte la [lista de conectores](https://flow.microsoft.com/connectors/) para ver si la aplicación que quiere automatizar ya tiene un conector. Si es así, considere la posibilidad de crear un flujo en lugar de un flujo de interfaz de usuario. También puede crear su [propio conector](https://docs.microsoft.com/connectors/custom-connectors/).

## <a name="prerequisites"></a>Requisitos previos

- Un plan de Power Automate [pagado](https://flow.microsoft.com/pricing/) o [de prueba](https://flow.microsoft.com/manage/).

- Una cuenta profesional o educativa para iniciar sesión en el dispositivo Windows con privilegios de administrador y Power Automate.

- Un dispositivo que ejecute Windows 10, Windows Server 2016 o Windows Server 2019.

- Explorador [Microsoft Edge](https://www.microsoftedgeinsider.com) o Google Chrome.

- Un [entorno](https://docs.microsoft.com/power-platform/admin/environments-overview) con una [base de datos de Common Data Service](https://docs.microsoft.com/power-platform/admin/create-database).

- Un teclado compatible conectado.

## <a name="limitations"></a>Limitaciones

Flujos de interfaz de usuario (versión preliminar) está disponible en inglés.

Lo siguiente no es compatible:

-   Flujos de la interfaz de usuario de escritorio

    -   Varios monitores
    -   Máquinas virtuales
    -   Doble clic, mantener el mouse sobre un elemento, entrada táctil o de lápiz
    -   Interacciones en Windows (Explorador de archivos, menú de inicio, barra de tareas, etc.)

-   Flujos de interfaz de usuario web

    -   Clic con el botón derecho
    -   La información de sesión del usuario (por ejemplo, las cookies) no se reutilizará durante la reproducción. Tendrá que editar el script para insertar la información de inicio de sesión cuando sea necesario en los sitios web.

Encontrará limitaciones específicas de características incluidas en la documentación de cada característica.

## <a name="install-ui-flows-on-your-device"></a>Instalación de flujos de interfaz de usuario en el dispositivo

El instalador de flujos de interfaz de usuario contiene todos los componentes necesarios para grabar, editar y probar flujos de interfaz de usuario para el escritorio. 

>[!IMPORTANT]
>El instalador de flujos de interfaz de usuario instala el componente WebDriver y la extensión del explorador de flujos de interfaz de usuario. Ambos son necesarios para grabar, probar y ejecutar flujos de interfaz de usuario para el escritorio.

Para instalar la aplicación de flujos de interfaz de usuario, siga estos pasos:

1. [Descargue el instalador de flujos de interfaz de usuario](https://go.microsoft.com/fwlink/?linkid=2102613).
1. Abra el archivo **Setup.Microsoft.Flow.UIflow.exe**. Es probable que este archivo esté en la carpeta **Descargas** después de que lo descargó en el paso anterior.
1. Siga las instrucciones del instalador de **configuración de flujos de interfaz de usuario (versión preliminar)** para completar la instalación.

> [!TIP]
> Si quiere cambiar la configuración de la colección de datos, vuelva a instalar los flujos de interfaz de usuario y cambie la configuración.

## <a name="activate-the-ui-flows-browser-extension"></a>Activación de la extensión del explorador de flujos de interfaz de usuario 

Una vez que se complete el instalador de flujos de interfaz de usuario, el explorador le pedirá activar la extensión.

- En Microsoft Edge, seleccione cada icono de advertencia en la esquina superior derecha del explorador y, después, **Habilitar extensión**.
-   En Google Chrome, seleccione **Enable extension** (Habilitar extensión) cuando se le solicite.  

> [!TIP]
> Si no ve la solicitud en el explorador, revise lo siguiente:
> - Debe usar Microsoft Edge o Google Chrome.
> - Es posible que tenga que habilitar manualmente la extensión. Para Microsoft Edge, vaya a **edge://extensions** o, en el caso de Google Chrome, a **chrome://extensions**.
> - Si la extensión de los flujos de interfaz de usuario de Power Automate no aparece, puede volver a instalarla con el [instalador de flujos de interfaz de usuario](https://go.microsoft.com/fwlink/?linkid=2102613).

## <a name="install-selenium-ide-to-automate-web-applications"></a>Instalación de Selenium IDE para automatizar las aplicaciones web

El IDE de Selenium es una herramienta de código abierto que le permite grabar y reproducir interacciones humanas en sitios web.

Con flujos de interfaz de usuario, puede ejecutar scripts del IDE de Selenium desde Power Automate y almacenados de manera segura (con gobernanza de TI adecuada) en Common Data Service.

Siga estos pasos para instalar el IDE de Selenium:

1. [Descargue e instale](https://go.microsoft.com/fwlink/?linkid=2107665) el IDE de Selenium para la versión siguiente de Microsoft Edge o Google Chrome.

1. En Microsoft Edge, seleccione **Permitir extensiones de otras tiendas** y, después, **Agregar a Chrome**.

## <a name="install-the-on-premises-data-gateway"></a>Instalación de la puerta de enlace de datos local

Necesitará la puerta de enlace para desencadenar el flujo de interfaz de usuario desde un [flujo de evento, programación o botón](../getting-started.md#types-of-flows).

>[!TIP]
>La puerta de enlace no es necesaria si solo quiere crear, editar y probar los flujos de interfaz de usuario en el dispositivo.

[Instale la puerta de enlace de datos local](https://docs.microsoft.com/data-integration/gateway/service-gateway-install), si la necesita.

## <a name="uninstall-ui-flows"></a>Desinstalación de los flujos de interfaz de usuario

1. Abra el menú **Inicio** > **Configuración** > **Aplicaciones**.
1. Busque **Flujos de interfaz de usuario (versión preliminar)** y selecciónelo.
1. Seleccione **Desinstalar**.

## <a name="supported-keyboard-layouts"></a>Distribuciones de teclado admitidas

- Teclado EE. UU.: inglés (Estados Unidos)
- Teclado EE. UU.: inglés (Australia)
- Teclado EE. UU.: inglés (Canadá)
- Microsoft Pinyin: chino (han simplificado, China)
- Teclado alemán: alemán (Alemania)
- Microsoft IME: japonés (Japón)
- Teclado de Reino Unido: inglés (Reino Unido)
- Teclado francés: francés (Francia)
- Teclado ruso: ruso (Rusia)
- Teclado portugués (brasileño ABNT): portugués (Brasil)
- Teclado portugués (brasileño ABNT2): portugués (Brasil)
- Microsoft IME: coreano (Corea del Sur)
- Teclado español: español (España)
- Teclado italiano: italiano (Italia)
- Teclado latinoamericano: español (México)
- Teclado polaco (programadores): polaco (Polonia)
- Teclado internacional de Estados Unidos: neerlandés (Países Bajos)
- Teclado Q turco: turco (Turquía)
- Teclado de India: inglés (India)

## <a name="supported-languages"></a>Idiomas admitidos

A continuación se indican los idiomas compatibles con los flujos de interfaz de usuario, además del inglés:

|||||
----|-----|-----|-----
Vasco  | Francés    | Letón   | Eslovaco
Búlgaro   |   Gallego    |   Lituano  |   Esloveno
Catalán |   Alemán      |Malayo  |   Español
Chino (simplificado)    |   Griego   |   Noruego   |   Sueco
Chino (tradicional)   |   Hindi   |   Polaco  |   Tailandés
Croata    |   Húngaro   |   Portugués (Brasil) |   Turco
Checo   |   Indonesio  |   Portugués (Portugal)       |Ucraniano
Danés  |   Italiano |   Rumano    |   Vietnamita
Neerlandés       |Japonés   |   Ruso 
Estonio    |Kazajo |   Serbio (cirílico, Serbia)  
Finés     |Coreano     |Serbio (latino, Serbia)

## <a name="limitations"></a>Limitaciones
- Las versiones más recientes de cada componente son necesarias para grabar, probar o ejecutar flujos de interfaz de usuario.


## <a name="next-steps"></a>Pasos siguientes

- Aprenda a [crear flujos de interfaz de usuario de escritorio](create-desktop.md).
- Aprenda a [crear flujos de interfaz de usuario web](create-web.md).
- Aprenda a ejecutar [flujos de interfaz de usuario](run-ui-flow.md).
- Aprenda a [administrar flujos de interfaz de usuario](manage.md).
- Más información sobre la [puerta de enlace local](../gateway-reference.md#use-a-gateway)
