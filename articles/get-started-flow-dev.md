---
title: Creación de conectores personalizados e inserción de flujos | Microsoft Docs
description: Cree un conector personalizado, compártalo e inserte un flujo, entre otras operaciones.
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
ms.date: 11/22/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: feca66dc9148d6416e2bac8a6e690cee62d6aa9b
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74369097"
---
# <a name="start-to-build-with-power-automate"></a>Inicio del proceso de compilación con Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Estos son algunos métodos mediante los que puede ampliar su aplicación con Power Automate:

* Crear un conector personalizado y conectarse a él.
* Compartir el conector personalizado con todos los usuarios de Power Automate.
* Insertar la experiencia del flujo en una aplicación.
* Resaltar todos los conectores personalizados para que los usuarios puedan interactuar con Power Automate de la mejor manera posible para ellos.

## <a name="prerequisites"></a>Requisitos previos

* Una cuenta de [Power Automate](https://flow.microsoft.com).

## <a name="create-a-custom-connector"></a>Creación de un conector personalizado

Si dispone de un servicio web al que quiera conectarse desde Power Automate, primero será necesario crear un conector personalizado. Al registrar un conector personalizado, enseña a Power Automate las características de su servicio web, incluido el tipo de autenticación que requiere, los desencadenadores y las acciones que admite, y los parámetros y las salidas de cada una de dichas acciones.

Siga este tutorial para obtener información sobre cómo [registrar y usar conectores personalizados](https://powerapps.microsoft.com/tutorials/register-custom-api/). Después de registrar el conector personalizado, puede compartirlo en su organización para realizar pruebas.

## <a name="share-a-custom-connector-with-all-power-automate-users"></a>Uso compartido de un conector personalizado con todos los usuarios de Power Automate

Después de probar por completo el conector personalizado, inicie el [proceso de revisión](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) para que Microsoft apruebe que lo comparta con todos los demás usuarios de Power Automate.

Esto es lo que necesitará para el proceso de revisión:

* Archivo OpenAPI que represente la API y la información de autenticación.
* Icono para el conector.
* Descripción del conector.
* Aproximadamente diez ideas sobre cómo puede beneficiar el conector a otros usuarios a través de plantillas.

Después de enviar esta información, Microsoft empezará a evaluar la funcionalidad de la API en Power Automate y Microsoft Power Apps.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>Inserción de la experiencia de flujo en un sitio web o una aplicación

Puede [insertar](developer/embed-flow-dev.md) Power Automate en su aplicación para habilitar la integración profunda en contexto entre la aplicación y el resto de servicios que admite Power Automate. Por ejemplo, puede:

* Examinar todas las plantillas relacionadas con el servicio y que permiten que el usuario seleccione una plantilla.
* Administrar los flujos que los usuarios han relacionado con su aplicación.

## <a name="next-steps"></a>Pasos siguientes

Obtenga información acerca de cómo [insertar](developer/embed-flow-dev.md) Power Automate en la aplicación.
