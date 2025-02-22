---
title: Información sobre cómo editar flujos de interfaz de usuario web | Microsoft Docs
description: Obtenga información sobre cómo editar flujos de interfaz de usuario web.
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 74c323f844c6bdc0f4cb1ad3d1a37977070a0a26
ms.sourcegitcommit: bba5bd4ae3879b6bf1521d8ed636374fe09709e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "3298757"
---
# <a name="edit-web-ui-flows"></a>Edición de los flujos de la interfaz de usuario web

Los flujos de interfaz de usuario web automatizan los sitios web que se ejecutan en la [versión 80 o posterior de Microsoft Edge](https://www.microsoft.com/edge/) o en Google Chrome. Una vez que haya [creado un flujo de interfaz de usuario web](create-web.md), es posible que tenga que editarlo. Siga los pasos de este documento para aprender a editar los flujos de interfaz de usuario web.

## <a name="edit-in-selenium-ide"></a>Edición en el IDE de Selenium

Use el IDE de Selenium para editar los flujos de interfaz de usuario web.

>[!NOTE]
>La edición en el IDE de Selenium está dirigida a desarrolladores y usuarios avanzados.

Puede consultar los [comandos de Selenium](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) para aprender a editar el script.

El IDE de Selenium sugiere distintos selectores y uno predeterminado cuando el destino es un elemento de la interfaz de usuario. También puede definir un selector nuevo si ninguno de los propuestos es adecuado. Esto suele ocurrir cuando la estructura HTML del sitio web es muy dinámica.

Este es un ejemplo de los posibles selectores que identificó el IDE de Selenium:

![Posibles selectores](../media/edit-web/possible-selectors.png "Posibles selectores")

## <a name="accessing-a-property-of-an-object-variable-or-item-of-an-array-variable"></a>Acceso a una propiedad de una variable de objeto o un elemento de una variable de matriz**

Esta funcionalidad le permite usar una sintaxis como \${foo.bar} para acceder a la propiedad bar del objeto foo. También puede escribir en la propiedad bar de foo si usa foo.bar como la propiedad value de un comando store. También puede usar una sintaxis como \${foo[0]} para acceder al elemento en índice 0 en la matriz foo.

## <a name="next-steps"></a>Pasos siguientes

- [Creación de flujos de interfaz de usuario web](create-web.md)
- [Ejecución de flujos de interfaz de usuario](run-ui-flow.md)
