---
title: Resumen de las solicitudes del titular de los datos de acuerdo con el RGPD | Microsoft Docs
description: Obtenga información acerca de cómo responder a solicitudes del interesado de acuerdo con el RGPD para Power Automate.
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
ms.openlocfilehash: e9f4418ae532c3c6e2f3511ee7ee873695bc8f9f
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79191964"
---
# <a name="responding-to-gdpr-data-subject-requests-for-power-automate"></a>Respuesta a solicitudes del interesado de acuerdo con el RGPD para Power Automate


Este articulo le prepara tanto a usted como a su organización para cumplir con el Reglamento general de protección de datos (RGPD). En este artículo no solo se describe lo que Microsoft está haciendo para prepararse para el RGPD, sino que también se incluyen ejemplos de medidas que puede adoptar ya para cumplir con el RGPD al usar Power Apps, Power Automate y Common Data Service.

## <a name="prerequisites"></a>Requisitos previos

Los usuarios y administradores pueden realizar las acciones descritas en este artículo.

### <a name="users"></a>Usuarios

Un usuario debe tener una cuenta activa de Azure Active Directory con una [licencia de Power Automate](https://preview.flow.microsoft.com/pricing/). Los usuarios que no cumplan este requisito deben pedir a un administrador que realice estas acciones.

### <a name="administrators"></a>Administradores

Puede realizar las operaciones que requieren privilegios de administrador, que se describen en este artículo, si inicia sesión en el [centro de administración de Power Automate](https://admin.flow.microsoft.com/) o [PowerShell de administración de Power Apps](https://go.microsoft.com/fwlink/?linkid=871804) con una cuenta que tenga estos permisos:

- Una licencia de prueba o de pago para Power Apps Plan 2.

    [Una licencia de prueba](http://make.powerapps.com/trial) expira en 30 días.

- [Administrador global de Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) o [administrador global de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

### <a name="unmanaged-tenants"></a>Inquilinos no administrados
Si es miembro de un [inquilino no administrado](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover), lo que significa que el inquilino de Azure AD no tiene un administrador global, todavía podrá seguir los pasos descritos en este artículo para exportar y quitar sus propios datos personales. 

## <a name="responding-to-dsrs-for-power-automate-customer-data"></a>Respuesta a los derechos de titulares de datos para los datos de cliente de Power Automate

El RGPD otorga a los usuarios (denominados en el RGPD "titulares de datos") el derecho de administrar los datos personales que se han recopilado por un empleador u otro tipo de agencia u organización (denominado "controlador de datos" o simplemente "controlador"). Los datos personales se definen muy ampliamente en el RGPD como cualquier dato que guarde relación con una persona física identificada o identificable. El RGPD ofrece a los titulares de datos derechos específicos sobre sus datos personales, como la obtención de copias de los datos personales, la solicitud de correcciones, la restricción de procesamiento, la eliminación o la recepción en un formato electrónico que permita su transferencia a otro controlador. Una solicitud formal emitida por un titular de datos a un controlador para que adopte medidas sobre sus datos personales se denomina "solicitud de derechos de titulares de datos".

En este artículo se describe cómo utilizar los productos, servicios y herramientas administrativas de Microsoft para ayudar a los controladores a buscar y actuar en datos personales en respuesta a los derechos de titulares de datos. En concreto, este artículo incluye cómo buscar, acceder y actuar en los datos personales que residen en la nube de Microsoft. Este es un breve resumen de los procesos descritos en esta guía:

1. Detectar: use herramientas de búsqueda y detección para encontrar más fácilmente los datos de los clientes que pueden estar sometidos a derechos de titulares de datos. Una vez que se recopilen documentos potencialmente de respuesta, puede realizar una o varias de las acciones de derechos de titulares de datos descritas en los pasos siguientes para responder a la solicitud. También puede determinar que la solicitud no cumple las directrices de su organización para responder a los derechos de los titulares de datos. [Documentación de detección de derechos de titulares de datos de Power Automate](gdpr-dsr-discovery.md)

1. Acceder: recupere datos personales que residen en la nube de Microsoft y, si se solicita, haga una copia de estos que pueda estar a disposición del titular de los datos.

1. Rectificar: haga cambios o implemente otras acciones solicitadas en los datos personales, si procede.

    Si un titular de datos le pide que corrija sus datos personales que residen en su organización, usted y su organización deben determinar si es adecuado atender la solicitud.  La rectificación de los datos puede incluir acciones como editar, ocultar o quitar datos personales.

    Puede usar Azure Active Directory para administrar las identidades de los usuarios de Power Automate. Los clientes empresariales pueden administrar las solicitudes de rectificación de derechos de titulares de datos, incluidas las características de edición limitadas, por la naturaleza de un determinado servicio de Microsoft.  Como procesador de datos, Microsoft no ofrece la posibilidad de corregir los registros generados por el sistema, porque estos registros reflejan actividades objetivas y constituyen un registro histórico de eventos dentro de los servicios de Microsoft.  [Obtenga más información sobre los derechos de titulares de datos.](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure)

1. Restringir: limite el tratamiento de los datos personales, ya sea quitando licencias para varios servicios en línea o desactivando los servicios deseados siempre que sea posible. También puede quitar datos de la nube de Microsoft y conservarlos de manera local o en otra ubicación.

    Los titulares de datos pueden solicitar que se restrinja el procesamiento de sus datos personales.  Microsoft proporciona interfaces de programación de aplicaciones (API) e interfaces de usuario (IU) para este propósito.  Estas interfaces permiten al administrador de inquilinos del cliente de empresa administrar estos derechos de titulares de datos a través de una combinación de exportación y eliminación de los datos. Un cliente puede 1) exportar una copia electrónica de los datos personales del usuario, incluidas las cuentas, los registros generados por el sistema y los registros asociados, seguido de 2) la eliminación de la cuenta y los datos asociados que se encuentran dentro de sistemas de Microsoft.

1. Eliminar: quite de forma permanente los datos personales que se encuentran en la nube de Microsoft. [Obtenga más información acerca de cómo eliminar datos personales](gdpr-dsr-delete.md).

1. Exportar: proporcione una copia electrónica (en un formato legible) de los datos personales al titular de los datos. Cada sección de este artículo describe los procedimientos técnicos que puede llevar a cabo la organización de un controlador de datos para responder a una solicitud de derechos de titulares de datos en relación con datos personales en la nube de Microsoft. [Obtenga más información acerca de cómo exportar datos personales](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>Registros generados por el sistema

Consulte esta [guía](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs) para obtener más información sobre los registros generados por el sistema para Power Automate.
