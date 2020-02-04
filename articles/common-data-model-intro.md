---
title: Common Data Service | Microsoft Docs
description: Cree un flujo para importar datos, exportar datos o crear aprobaciones con Common Data Service.
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
ms.openlocfilehash: 2b536263d90af7b0bbdcdec30d1b00bc7bae2a9e
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74361208"
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>Cree de un flujo que use Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Mejore la eficacia operativa con una vista unificada de los datos empresariales mediante la creación de un flujo que use [Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/). Implemente esta base de datos profesional segura que incluye las entidades empresariales estándar con formato correcto (como Ventas, Compras, Atención al cliente y Productividad) de su organización. Almacene los datos de la organización en una o varias [entidades personalizadas](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/), que ofrecen varias ventajas sobre los orígenes de datos externos, como Microsoft Excel y Salesforce.

Por ejemplo, aproveche Common Data Service en Power Automate de las siguientes formas:

* Cree un flujo para importar datos, exportar datos o realizar acciones sobre los datos (como enviar una notificación). Tenga en cuenta que este enfoque no es un servicio de sincronización completa; simplemente permite introducir o sacar datos de cada entidad.
  
    Para obtener pasos detallados, consulte los procedimientos que se explicarán en este mismo tema.
* En lugar de [crear un bucle de aprobación a través de correo electrónico](wait-for-approvals.md), cree un flujo que almacene el estado de aprobación en una entidad y compile una aplicación personalizada en la que los usuarios puedan aprobar o rechazar los elementos.
  
    Para conocer los pasos detallados, consulte [Build an approval loop with the Common Data Service](common-data-model-approve.md) (Compilación de un bucle de aprobación con Common Data Service).

**Requisitos previos**

* Regístrese en [Power Automate](https://flow.microsoft.com) y [PowerApps](https://make.powerapps.com).
  
    Si tiene problemas, compruebe si [Power Automate](sign-up-sign-in.md) y [Power Apps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) admiten el tipo de cuenta que tiene y si su organización no ha bloqueado la suscripción.
* Si es la primera vez que utiliza Common Data Service, abra la pestaña **Entidades** de [powerapps.com](https://web.powerapps.com/#/entities) y haga clic o pulse **Create my database** (Crear mi base de datos).

## <a name="sign-in-to-your-environment"></a>Inicie sesión en su entorno
1. Abra el [portal de Power Automate](https://flow.microsoft.com) y haga clic o pulse en **Iniciar sesión** en la esquina superior derecha.
   
    **Nota**: para mostrar el botón **Iniciar sesión** es posible que tenga que abrir el menú de la parte superior izquierda.
   
    ![Iniciar sesión](./media/common-data-model-intro/signin-flow.png)
2. En el menú de la parte superior derecha seleccione el entorno en que creó la base de datos en powerapps.com.
   
    **Nota**: si no selecciona el mismo entorno, no verá las entidades.
   
    ![Seleccionar entorno](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>Apertura de una plantilla
1. En el cuadro **Buscar plantillas** de la parte superior de la pantalla, escriba o pegue **common** y presione Entrar.
   
    ![Búsqueda de plantillas](./media/common-data-model-intro/template-search.png)
2. En la lista de plantillas, haga clic o pulse la plantilla que importa datos del origen que desee en la entidad (o *objeto*) que desee.
   
    Por ejemplo, haga clic o pulse la plantilla que copia la información de contacto de Dynamics 365 en Common Data Service.
   
    ![Elegir una plantilla](./media/common-data-model-intro/choose-template.png)
3. Haga clic en el botón **Usar esta plantilla** o púlselo.
   
    ![Utilizar plantilla](./media/common-data-model-intro/use-template.png)
4. Si aún no ha creado una conexión de Power Automate con Dynamics 365, haga clic o pulse en **Iniciar sesión** y, luego, especifique sus credenciales, en caso de que se le pidan.
   
    ![Inicio de sesión en Dynamics 365](./media/common-data-model-intro/dynamics-signin.png)
5. Haga clic en **Continuar** o púlselo.
   
    ![Confirmar cuentas](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>Compilación de un flujo
1. En la primera tarjeta, especifique el evento que desencadenará el flujo.
   
    Por ejemplo, va a crear un flujo que copiará contactos nuevos de una instancia de Dynamics 365 a Common Data Service. En **When a record is created** (Cuando se cree un registro), especifique la instancia, para lo que debe hacer clic o pulsar la flecha abajo y, luego, hacer clic o pulsar una de las opciones de la lista que aparece.
   
    ![Especificar instancia de Dynamics 365](./media/common-data-model-intro/specify-instance.png)
2. (opcional) Cerca de la parte superior de la pantalla, especifique otro nombre para el flujo que va a crear.
   
    **Nota:** si la ventana del explorador no está maximizada, es posible que la interfaz de usuario sea un poco diferente.
   
    ![Flujo de nombre](./media/common-data-model-intro/name-flow.png)
3. Haga clic o pulse **Crear flujo**.
   
    **Nota:** si la ventana del explorador no está maximizada, es posible que solo aparezca la marca de verificación.
   
    ![Crear flujo](./media/common-data-model-intro/create-flow.png)

Ahora, siempre que dicho objeto se cree en el sistema de origen, se importarán en Common Data Service. Si no encuentra una plantilla que haga lo que necesita, puede [generar un flujo desde cero](get-started-logic-flow.md) que opere sobre Common Data Service.

Puede realizar acciones en los cambios de la base de datos. Por ejemplo, puede enviar un correo de notificación cada vez que cambian los datos.

