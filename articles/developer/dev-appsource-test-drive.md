---
title: Permitir a los clientes la realización de pruebas de los flujos en AppSource | Microsoft Docs
description: Utilice AppSource para compartir aplicaciones con los clientes y genere clientes potenciales para su empresa.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2017
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 67e38b8c3b2a7f32c88ecc31c88cfdb654d23310
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74362933"
---
# <a name="let-customers-test-drive-your-flows-on-appsource"></a>Permitir a los clientes la realización de pruebas de los flujos en AppSource
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]
¿Quiere mostrar cómo se integra la aplicación con Power Automate? Ya están disponibles las soluciones Test Drive en [AppSource.com](https://appsource.microsoft.com) como una manera de compartir la integración de Power Automate con los clientes y generar clientes potenciales para su empresa.

## <a name="what-is-a-test-drive-solution"></a>¿Qué es una solución de versión de prueba?
Una solución Test Drive permite a sus clientes probar una aplicación real sin necesidad de instalar ninguna aplicación. Los clientes solo tienen que iniciar sesión en AppSource.com con su cuenta de Azure Active Directory (AAD) y ejecutar la aplicación en un explorador web. Sin la versión de prueba, los clientes solo pueden leer acerca de la aplicación o ver un vídeo que la describe. Con la versión de prueba, los clientes se hacen una idea mejor acerca de la solución y de la funcionalidad de la aplicación. Y tienen una experiencia de uso real de la aplicación. Pero los clientes no podrán ver los entresijos para saber cómo se ha compilado la aplicación, por lo que su propiedad intelectual estará protegida. Se recopila y comparte información de clientes potenciales con usted para ayudarle a desarrollar su negocio.

## <a name="how-do-i-build-a-test-drive-solution"></a>¿Cómo se puede crear una solución Test Drive?
La compilación de una solución Test Drive es igual a la compilación de cualquier otra aplicación, pero necesita usar un origen de datos al que se pueda otorgar acceso de solo lectura al usuario. El uso de un origen de datos que ya está configurado implica que no se producirá ningún error a la hora de probarlo. La solución completa que se distribuye en última instancia a los clientes incluye datos editables, pero los datos de solo lectura también funcionan bien para una solución Test Drive.

### <a name="embed-flow-into-your-product"></a>Inserción de un flujo en el producto
Una vez que tiene un origen de datos al que puede conceder acceso de solo lectura al usuario, puede insertar Power Automate en la aplicación. [Obtenga más información acerca de la inserción aquí](embed-flow-dev.md). Es posible que desee usar la funcionalidad de búsqueda para resaltar las plantillas que son exclusivas de la aplicación. Por ejemplo, si la aplicación crea datos en Dynamics 365, puede resaltar una plantilla de Dynamics 365 que extrae los datos y, a continuación, envía un correo electrónico al usuario. 

## <a name="how-do-i-list-my-test-drive-solution-on-appsourcecom"></a>¿Cómo muestro mi solución Test Drive en AppSource.com?
Ahora que la aplicación ya está lista, es el momento de publicarla en AppSource.com. Para iniciar este proceso, complete el [formulario de la aplicación](https://flow.microsoft.com/partners/get-listed/) en flow.microsoft.com. Una vez que lo haga recibirá un correo electrónico con instrucciones sobre cómo enviar la aplicación para su publicación en AppSource.com.

