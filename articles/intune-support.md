---
title: La aplicación móvil Power Automate ahora admite la administración de aplicaciones móviles de Microsoft Intune. | Microsoft Docs
description: La aplicación móvil Power Automate ahora admite la administración de aplicaciones móviles de Microsoft Intune.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 521876e669e87c40f6108c46d7e4e0aee962ca34
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297547"
---
# <a name="power-automate-mobile-app-supports-microsoft-intune"></a>La aplicación móvil Power Automate es compatible con Microsoft Intune


La aplicación móvil Power Automate para iOS y Android admite la administración de aplicaciones móviles (MAM) de Intune sin inscripción de dispositivos. El uso de MAM permite a los administradores de TI crear y aplicar directivas de datos móviles para proteger los datos de la organización.

## <a name="why-intune-support-is-important"></a>¿Por qué es importante la compatibilidad con Intune?

Las organizaciones desean un mayor control sobre los datos que residen en los dispositivos móviles de los empleados. Puede que les interese restringir el modo en que se mueven los datos al dispositivo y asegurarse de que los datos se quitan una vez que un empleado abandona la organización.

## <a name="what-is-microsoft-application-management-mam"></a>¿Qué es Microsoft Application Management (MAM)?

MAM permite a las organizaciones crear directivas que rigen cómo se usan las aplicaciones en un inquilino. Esto incluye exigir el cifrado de datos de la aplicación, lo que limita la capacidad de copiar o extraer datos solo a aplicaciones aprobadas o exigir un PIN en un dispositivo.

### <a name="prerequisites"></a>Requisitos previos

- Una [directiva de protección de aplicaciones](https://docs.microsoft.com/intune/app-protection-policies) de Intune.
- Un grupo de Azure Active Directory (Azure AD).
- Portal de empresa. Una de las principales ventajas del uso de MAM es que no es necesario estar inscrito en MAM de Intune. Lo único necesario es el Portal de empresa, que está disponible en App Store y en la tienda de Google Play.
- Versión 2.31.0 de la aplicación móvil Power Automate para iOS, Android o Windows Phone.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Creación de una directiva de protección de aplicaciones, asignación de aplicaciones a la directiva, definición de la configuración y adición de usuarios a un grupo de Azure AD

Para que se administre la aplicación móvil de Power Automate, debe hacer lo siguiente:

1. Crear una directiva de protección de aplicaciones.
1. Asignar la aplicación móvil Power Automate a la directiva de protección de aplicaciones.
1. Asignar la configuración de directiva. Por ejemplo, puede asignar la directiva para exigir un PIN de acceso al dispositivo móvil que ejecuta la aplicación móvil Power Automate.
1. Aplique la directiva de protección de aplicaciones a un grupo de Azure AD específico.
1. Agregue todos los usuarios a los que se aplica la directiva de protección de aplicaciones al grupo de Azure AD.

Siga estos pasos para crear una [directiva de protección de aplicaciones](https://docs.microsoft.com/intune/app-protection-policies) que exija que los usuarios de la aplicación móvil Power Automate escriban un PIN para poder acceder a la aplicación. 


## <a name="test-the-app-protection-policy"></a>Prueba de la directiva de protección de aplicaciones

Después de haber creado la directiva de protección de aplicaciones y de asignar usuarios al grupo de Azure AD, es hora de usar la aplicación móvil Power Automate y confirmar que la directiva funciona.

Para confirmar que la directiva funciona, siga estos pasos:

1. Instale la aplicación móvil Power Automate en un dispositivo cuya plataforma coincida con una de las plataformas que haya definido en la directiva de protección de aplicaciones.
1. Inicie sesión en la aplicación móvil con una cuenta que se encuentre en el grupo de Azure AD que restringe el uso de la aplicación móvil a los usuarios que tienen un PIN.

A continuación, se le pedirá que:
1. Instale el Portal de empresa.
1. Establezca el PIN, si aún no tiene uno que cumpla los criterios de la directiva de protección de aplicaciones.


## <a name="learn-more"></a>Más información

Aprenda a crear una [directiva de protección de aplicaciones](https://docs.microsoft.com/intune/app-protection-policies).

