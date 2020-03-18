---
title: Más información sobre los entornos de Power Automate | Microsoft Docs
description: Aprenda a usar entornos para aislar los flujos
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/27/2017
ms.author: sunayv
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7d62aa0870af1be0e05e0a3799d02cfdfe705e3c
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195437"
---
# <a name="choosing-an-environment"></a>Elección de un entorno


En este artículo se describen los **entornos** de Power Automate en los que puede crear y aislar de forma segura flujos, puertas de enlace, conexiones y otros recursos.

Obtendrá información sobre:

* Las características que proporcionan los entornos.
* Cómo cambiar entre entornos.
* Cómo crear un flujo en el entorno adecuado.

## <a name="environments-overview"></a>Información general sobre los entornos

Cuando se crea un flujo, se puede elegir en qué entorno se va a hospedar y los recursos que va a usar. Se pueden usar entornos distintos para diferentes escenarios.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Estos son algunos escenarios para usar entornos

Escenario|Recomendación
-----|-----
Quiere crear un flujo que use una conexión a Microsoft Common Data Service.|Coloque el flujo y Common Data Service en el mismo entorno. Esto garantiza que todos los datos se aíslan en dicho entorno (límite de aislamiento).
Va a crear un flujo para el departamento de recursos humanos. Desea asegurarse de que los usuarios del departamento de recursos humanos son los únicos que tienen acceso al flujo.|Cree un entorno y agregue solo a los usuarios de recursos humanos a él. Coloque el flujo y los demás recursos que el flujo utilice en este entorno.
Hay usuarios en Europa que utilizan un flujo para mostrar datos de SharePoint.|Cree un entorno en Europa y, a continuación, cree el flujo y la conexión de SharePoint a este. Este entorno de Europa ofrece a los usuarios europeos el mejor rendimiento, ya que todos los recursos son locales en Europa (localidad de los datos).

Para crear entornos, debe ser administrador de Power Automate. Los administradores controlan quién tiene acceso a los entornos. Para más información acerca de cómo crearlos y administrarlos, consulte el tema sobre [administración de entornos](environments-overview-admin.md).

## <a name="switching-environments"></a>Cambio de entornos

Power Automate facilita el cambio entre entornos. Al cambiar de entorno, solo verá los elementos que se han creado en ese entorno específico; no podrá ver ni acceder a los elementos de ningún otro entorno.

Aquí se muestra un ejemplo.

Cree un flujo denominado *NewEmployee* en el entorno de *recursos humanos*. En [Power Automate](https://flow.microsoft.com), se abre el entorno *Sales*. El flujo *NewEmployee* no aparece en la lista. Para ver el flujo *NewEmployee*, abra el entorno de *recursos humanos*. Recuerde que las mismas reglas se pueden aplicar a todos los elementos que creó en ese entorno, incluidas las conexiones, las puertas de enlace y los flujos, entre otras cosas.

Siga estos pasos para cambiar de entorno:

1. Inicie sesión en [Power Automate](https://flow.microsoft.com).
1. En la esquina superior derecha, verá una imagen que representa su perfil.

   ![imagen de perfil](./media/environments-overview-maker/default-environment.png)

1. Seleccione la imagen. Aparece una lista desplegable que muestra todos los entornos disponibles. El entorno en el que ha iniciado sesión aparece seleccionado:

   ![lista de imágenes de entornos](./media/environments-overview-maker/all-environments.png)
1. Para cambiar a otro entorno, seleccione ese entorno en la lista:

   ![seleccionar un entorno al que cambiar](./media/environments-overview-maker/select-europe.png)
1. Power Automate cambia al nuevo entorno.

## <a name="create-flows-in-the-right-environment"></a>Creación de flujos en el entorno adecuado

Antes de crear un flujo, seleccione el entorno en el que se agregará el flujo y sus recursos.

> [!NOTE]
> Si crea un flujo en el entorno incorrecto, tendrá que eliminarlo y, posteriormente, volver a crearlo en el entorno correcto.

Considere los siguientes factores al elegir en qué entorno quiere hospedar los flujos:

* Solo puede crear puertas de enlace en el entorno predeterminado. Por tanto, si desea usar una puerta de enlace para conectar el flujo a datos locales, tendrá que usar el entorno predeterminado.
* Las bases de datos de Microsoft Common Data Service están asociadas a un entorno específico. Por lo tanto, si desea crear un flujo que use Common Data Service, debe crear el flujo en el entorno que hospeda la base de datos.
* Verá todos los entornos en los que se pueden editar recursos. Sin embargo, tendrá que pedir a un administrador que lo agregue como creador a todos los entornos en los que desee crear flujos.

> [!NOTE]
> Siempre podrá crear flujos en el entorno predeterminado.

## <a name="next-steps"></a>Pasos siguientes

* [Creación de un flujo desde una plantilla](get-started-logic-template.md)
* [Crear un flujo](get-started-logic-flow.md)
* [Introducción acerca de los entornos para administradores](environments-overview-admin.md)
