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
ms.date: 03/24/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 97456d637dd272a465559d4cee8fb1d17fe3de8d
ms.sourcegitcommit: bba5bd4ae3879b6bf1521d8ed636374fe09709e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "3298779"
---
# <a name="set-up-ui-flows"></a>Configuración de los flujos de la interfaz de usuario

Antes de poder usar el dispositivo para crear flujos de interfaz de usuario, debe asegurarse de que cumple los requisitos que se describen aquí.

> [!TIP]
> Antes de crear un flujo de interfaz de usuario, consulte la [lista de conectores](https://flow.microsoft.com/connectors/) para ver si la aplicación que quiere automatizar ya tiene un conector. Si es así, considere la posibilidad de crear un flujo en lugar de un flujo de interfaz de usuario. También puede crear su [propio conector](https://docs.microsoft.com/connectors/custom-connectors/).

## <a name="prerequisites"></a>Requisitos previos

- Un plan de Power Automate [pagado](https://flow.microsoft.com/pricing/) o de [prueba](https://flow.microsoft.com/manage/).

- Una cuenta profesional o educativa para iniciar sesión en el dispositivo Windows con privilegios de administrador y Power Automate.

- Un dispositivo que ejecuta Windows 10 Pro, Windows Server 2016 o Windows Server 2019.

- El explorador [Microsoft Edge](https://www.microsoft.com/edge/) (versión 80 o posterior) o Google Chrome.

- Un [entorno](https://docs.microsoft.com/power-platform/admin/environments-overview) con una [base de datos Common Data Service](https://docs.microsoft.com/power-platform/admin/create-database).

- Un teclado compatible conectado.

## <a name="limitations"></a>Limitaciones

Para grabar, probar o ejecutar flujos de interfaz de usuario, debe tener la versión más reciente de cada componente.

Lo siguiente no es compatible:
- No se admiten instalaciones de Windows 10 Home.

-   Flujos de la interfaz de usuario de escritorio

    -   Varios monitores
    -   Doble clic, mantener el mouse sobre un elemento, entrada táctil o de lápiz
    -   Interacciones en Windows (Explorador de archivos, menú de inicio, barra de tareas, etc.)

-   Flujos de interfaz de usuario web

    -   Haga clic con el botón derecho.
    -   La información de sesión del usuario (por ejemplo, las cookies) no se reutilizará durante la reproducción. Tendrá que editar el script para insertar la información de inicio de sesión cuando sea necesario en los sitios web.

Encontrará limitaciones específicas de características incluidas en la documentación de cada característica.

## <a name="install-ui-flows-on-your-device"></a>Instalación de flujos de interfaz de usuario en el dispositivo

El instalador de flujos de interfaz de usuario contiene todos los componentes necesarios para grabar, editar y probar flujos de interfaz de usuario para el escritorio. 

>[!IMPORTANT]
>El instalador de flujos de interfaz de usuario instala el componente WebDriver y la extensión del explorador de flujos de interfaz de usuario. Ambos son necesarios para grabar, probar y ejecutar flujos de interfaz de usuario para el escritorio.

Para instalar la aplicación de flujos de interfaz de usuario, siga estos pasos:

1. [Descargue el instalador de flujos de interfaz de usuario](https://go.microsoft.com/fwlink/?linkid=2102613).
1. Abra el archivo **Setup.Microsoft.PowerAutomate.UIflow.exe**. Es probable que este archivo esté en la carpeta **Descargas** después de que lo descargó en el paso anterior.
1. Siga las instrucciones del instalador de **configuración de flujos de interfaz de usuario** para completar la instalación.

### <a name="set-data-collection-options"></a>Establecimiento de opciones de recopilación de datos

Durante la instalación, si no quiere enviar datos de uso a Microsoft, puede cambiar la configuración predeterminada. Para ello, desactive **Permitir que Microsoft recopile datos de uso para mejorar los flujos de interfaz de usuario**.

![Imagen que muestra las opciones de recopilación de datos](../media/ui-flows-setup/data-collection-settings.png)

## <a name="activate-the-ui-flows-browser-extension"></a>Activación de la extensión del explorador de flujos de interfaz de usuario 

Una vez que se complete el instalador de flujos de interfaz de usuario, el explorador le pedirá activar la extensión.

- En [Microsoft Edge](https://www.microsoft.com/edge/) (versión 80 o posterior), seleccione cada icono de advertencia en la parte superior derecha del explorador y, después, **Habilitar extensión**.
-   En Google Chrome, seleccione **Enable extension** (Habilitar extensión) cuando se le solicite.  

> [!TIP]
> Si no ve la solicitud en el explorador, revise lo siguiente:
> - Debe usar [Microsoft Edge](https://www.microsoft.com/edge/) (versión 80 o posterior) o Google Chrome.
> - Es posible que tenga que habilitar manualmente la extensión. Para Microsoft Edge, vaya a **edge://extensions** o, en el caso de Google Chrome, a **chrome://extensions**.
> - Si la extensión de los flujos de interfaz de usuario de Power Automate no aparece, puede volver a instalarla con el [instalador de flujos de interfaz de usuario](https://go.microsoft.com/fwlink/?linkid=2102613).


## <a name="install-selenium-ide-to-automate-web-applications"></a>Instalación de Selenium IDE para automatizar las aplicaciones web

El IDE de Selenium es una herramienta de código abierto que le permite grabar y reproducir interacciones humanas en sitios web.

Con flujos de interfaz de usuario, puede ejecutar scripts del IDE de Selenium desde Power Automate y almacenados de manera segura (con gobernanza de TI adecuada) en Common Data Service.

Siga estos pasos para instalar el IDE de Selenium:

1. [Descargue e instale](https://go.microsoft.com/fwlink/?linkid=2107665) Selenium IDE para [Microsoft Edge](https://www.microsoft.com/edge/) (versión 80 o posterior) o Google Chrome.

1. En Microsoft Edge (versión 80 o posterior), seleccione **Permitir extensiones de otras tiendas** y, después, **Agregar a Chrome**.

## <a name="install-the-on-premises-data-gateway"></a>Instalación de la puerta de enlace de datos local

Necesitará la puerta de enlace para desencadenar el flujo de interfaz de usuario desde un [flujo de evento, programación o botón](../getting-started.md#types-of-flows) en un dispositivo remoto.

>[!TIP]
>La puerta de enlace no es necesaria si solo quiere crear, editar y probar los flujos de interfaz de usuario en el dispositivo.

[Instale la puerta de enlace de datos local](https://docs.microsoft.com/data-integration/gateway/service-gateway-install), si la necesita.


>[!IMPORTANT]
>Cuando se instale la puerta de enlace, el valor predeterminado pasará a ser la región que usa Power Automate.


## <a name="setup-ui-flows-connections-and-machine-credentials"></a>Configuración de las conexiones de flujos de interfaz de usuario y las credenciales del equipo

1. Inicie sesión en [Power Automate](https://powerautomate.microsoft.com).
1. Expanda **Datos** en el lado izquierdo de la pantalla.
1. Seleccione **Conexiones**.

   ![Captura de pantalla de la pestaña conexiones](../media/ui-flows-setup/connections-tab.png)

1. Seleccione Nueva conexión.

   ![Captura de pantalla de una conexión](../media/ui-flows-setup/new-connection.png)

1. Busque *Flujo de interfaz de usuario* y seleccione **Flujos de interfaz de usuario**.

   ![Captura de pantalla del cuadro de búsqueda](../media/ui-flows-setup/search-ui-flow.png)

1. Proporcione la información de puerta de enlace y las credenciales del dispositivo: 

    - **Dominio y nombre de usuario**: proporcione su cuenta de dispositivo. Puede usar una cuenta local con el nombre del usuario (por ejemplo, “MACHINENAME\\usuario” o “local\\usuario”) o una cuenta de Active Directory como “DOMAIN\\usuario”.
    - **Contraseña**: la contraseña de su cuenta.
    - **Elegir una puerta de enlace**: seleccione la puerta de enlace que quiera usar.

      ![Captura de pantalla que muestra dónde especificar las credenciales para la conexión](../media/ui-flows-setup/credentials-screen.png)

1. Seleccione **Crear**.

## <a name="troubleshoot-missing-gateway"></a>Solucionar problemas de una puerta de enlace que falta

Es posible que no encuentre la puerta de enlace en la lista mientras crea la conexión por las siguientes razones:

- La puerta de enlace se puede instalar en una región distinta a la de Power Automate. Para resolver este problema, desinstale la puerta de enlace del dispositivo y vuelva a instalarla; para ello, seleccione la [región de Power Automate correcta](../regions-overview.md#region-mappings-for-power-automate-and-gateways).
- El propietario de la puerta de enlace la ha eliminado.

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

## <a name="supported-languages"></a>Idiomas compatibles

A continuación se indican los idiomas compatibles con los flujos de interfaz de usuario, además del inglés:

|||||
----|-----|-----|--------
Euskera  | Francés    | Letón   | Eslovaco
Búlgaro   |   Gallego    |   Lituano  |   Esloveno
Catalán |   Alemán      |Malayo  |   Español
Chino (simplificado)    |   Griego   |   Noruego   |   Sueco
Chino (tradicional)   |   Hindi   |   Polaco  |   Tailandés
Croata    |   Húngaro   |   Portugués (Brasil) |   Turco
Checo   |   Indonesio  |   Portugués (Portugal)       |Ucraniano
Danés  |   Italiano |   Rumano    |   Vietnamita
Neerlandés       |Japonés   |   Ruso 
Estonio    |Kazajo |   Serbio cirílico (Serbia)  
Finés     |Coreano     |Serbio latino (Serbia)

## <a name="uninstall-ui-flows"></a>Desinstalación de los flujos de interfaz de usuario

1. Abra el menú **Inicio** > **Configuración** > **Aplicaciones**.
1. Busque la opción **Flujos de interfaz de usuario** y selecciónela.
1. Seleccione **Desinstalar**.

## <a name="learn-more"></a>Más información

- [Actualización de flujos de interfaz de usuario](upgrade.md) a partir de versiones anteriores
- Aprenda a [crear flujos de interfaz de usuario de escritorio](create-desktop.md).
- Aprenda a [crear flujos de interfaz de usuario web](create-web.md).
- Aprenda a ejecutar [flujos de interfaz de usuario](run-ui-flow.md).
- Aprenda a [administrar flujos de interfaz de usuario](manage.md).
- Más información sobre la [puerta de enlace local](../gateway-reference.md#use-a-gateway)
