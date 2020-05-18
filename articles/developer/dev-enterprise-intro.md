---
title: Power Automate para desarrolladores empresariales, fabricantes de software independientes y partners | Microsoft Docs
description: Introducción al desarrollo de soluciones para Power Automate.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: ca815ad5949da494c1a50c193c040acdd948d3a2
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297613"
---
# <a name="power-automate-for-enterprise-developers-isvs-and-partners"></a>Power Automate para desarrolladores empresariales, fabricantes de software independientes y partners
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Los desarrolladores tienen la posibilidad de ampliar Power Automate y crear soluciones aún más potentes para las organizaciones y clientes.

## <a name="power-automate-for-enterprise-developers"></a>Power Automate para desarrolladores empresariales

Como desarrollador empresarial, cree soluciones sólidas y personalizadas en Power Automate para su organización:

- **Creación de conectores personalizados**: desarrolle conectores personalizados para conectarse a los servicios web y de datos de la organización a través de Power Automate. [Más información](https://docs.microsoft.com/connectors/custom-connectors/)

- **Creación de instancias de Azure Functions**: diseñe instancias de Azure Functions para ampliar aplicaciones con lógica personalizada del lado del servidor. [Más información](/azure/azure-functions/app-service-export-api-to-powerapps-and-flow)

- **Insertar Power Automate**: inserte Power Automate directamente en sus experiencias de sitio web para crear soluciones integradas, flujos de trabajo de superficie o procesos en los que otros usuarios de su organización ya hacen su trabajo. [Más información](embed-flow-dev.md)

## <a name="power-automate-for-isvs-and-microsoft-partners"></a>Power Automate para fabricantes de software independientes y asociados de Microsoft

Como asociado de Microsoft o fabricante de software independiente (ISV por sus siglas en inglés), podrá acelerar la adopción tecnológica de los clientes mediante la extensión de sus productos con el fin de que se integren con los datos y los procesos empresariales de los clientes, así como agregar y personalizar flujos de trabajo para automatizar procesos empresariales dentro de su aplicación. Tras completar los pasos siguientes, su aplicación podrá aprovechar la potencia de un motor de flujos de trabajo que trabaja en la nube para conectar con más de 200 servicios distintos.

| Fase | Paso | ¿Cuándo lo necesita? |
| --- | --- | --- |
| Desarrollo | 1. Crear un conector personalizado según sus datos | En caso de que quiera exponer sus propios datos de fabricante de software independientes a Power Apps o Power Automate |
| Desarrollo | 2. Agregar soporte para que su aplicación autentique usuarios con Azure Active Directory (Azure AD) | Si quiere insertar la interfaz de usuario o lista de Power Automate en Microsoft AppSource | 
| Desarrollo | 3. Insertar la interfaz de usuario de Power Automate en su aplicación usando el iframe basado en la web | En caso de que quiera incluir la creación o administración de flujos en su aplicación. | 
| Desarrollo | 4. Crear y publicar plantillas de flujo | En caso de que quiera tener flujos ya creados para sus clientes. | 
| Desarrollo | 5. Agregar la lógica de aplicación a flujos de implementación programáticos | En caso de que quiera implementar automáticamente sus flujos de trabajo ya creados para sus clientes. | 
| Distribución | 6. Otorgar licencias de Microsoft Flow a los clientes mediante el programa Microsoft Cloud Solution Provider | En caso de que los clientes no tengan ninguna licencia de Office 365 o Dynamics 365. |
| Distribución | 7. Enumerar la solución en Microsoft AppSource | Se recomienda para aumentar la visibilidad de su solución de ISV. |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. Conectar a sus API O permitir que los clientes se conecte a sus API

Como ISV, es posible que tenga datos privados a los que los clientes deberían acceder mediante sus flujos. Puede exponer el acceso a cualquiera de los datos a través de un conector personalizado. [Más información](https://docs.microsoft.com/connectors/custom-connectors/)

Una vez creado, hay dos maneras para que los clientes puedan usar el conector:
- El conector se puede implementar en el inquilino del cliente a través de las API de REST o PowerShell.
- Para que el conector personalizado esté disponible públicamente para todos los usuarios, puede enviarlo para su certificación. [Más información](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. Autenticación 

Para llamar a las API de REST e insertar la interfaz de usuario autenticado, la aplicación deberá usar el inicio de sesión único federado de Azure AD para autenticar a los usuarios finales y clientes. [Vaya aquí](https://identity.microsoft.com/) para obtener información sobre cómo habilitar el inicio de sesión único federado de Azure AD. No se admite el acceso no autenticado ni mediante proveedores de identidades que no sean Azure AD. 

### <a name="3-embedding-ui-components"></a>3. Insertar componentes de interfaz de usuario

Inserte Power Automate en su aplicación para habilitar la integración profunda en contexto entre la aplicación y el resto de servicios que admite Power Automate. [Más información](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. Crear y publicar plantillas de flujo

Una vez que tenga un conector, debe publicar plantillas que muestren cómo usar el servicio. Estas plantillas servirán como ejemplos que los usuarios pueden aprender y posteriormente extender a sus propios flujos de trabajo exclusivos. [Más información](../publish-a-template.md)

### <a name="5-deployment"></a>5. Implementación

Para permitir que los usuarios finales accedan a flujos que puedan usar automáticamente, implemente los flujos en el inquilino de Azure AD del usuario. Use un paquete que implemente mediante nuestras API de REST o PowerShell. [Más información](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6. Licencias

Si los clientes ya tienen Office 365 o Dynamics 365 y las licencias están asociadas a las identidades con las que los usuarios inician sesión en Azure AD, no tendrán ningún otro requisito de licencia adicional. Si los clientes no usan Office 365 o Dynamics 365, deberá comprar derechos de uso para Power Automate en su nombre, de modo que tengan licencia para usar los componentes insertados en su aplicación.

Le ofrecemos el programa [Microsoft Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) para que compre licencias en nombre de sus clientes. Hay dos [planes de tarifa](https://flow.microsoft.com/pricing/) distintos para Power Automate. Consulte cada plan y sus características.

### <a name="7-list-on-appsource"></a>7. Publicar en AppSource

Una vez que haya integrado Power Automate en la aplicación, podrá publicarla en AppSource. Con AppSource, puede generar nuevos clientes potenciales para su empresa mediante la compilación de una aplicación y su publicación en AppSource para que los nuevos clientes las prueben. [Más información](dev-appsource-test-drive.md)
