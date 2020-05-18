---
title: Información acerca de las operaciones de datos | Microsoft Docs
description: Aprenda a realizar operaciones, como crear una tabla HTML, crear una tabla CSV, componer, combinar, seleccionar y filtrar matriz con Power Automate.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/02/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0541a89ad0fe5f8d7dae0acfc6f257be7532ef15
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297569"
---
# <a name="use-data-operations-with-power-automate"></a>Usar operaciones con Power Automate

En este tutorial, obtendrá información acerca de algunas de las operaciones de datos más usadas de Power Automate, como componer, combinar, seleccionar, filtrar matriz, crear tabla y analizar JSON que se pueden usar para manipular datos al crear flujos.

## <a name="prerequisites"></a>Requisitos previos
* Obtenga acceso a Power Automate.
* Una herramienta como [PostMan](https://www.getpostman.com/postman) para enviar solicitudes HTTP POST con una matriz JSON al flujo.

## <a name="use-the-compose-action"></a>Uso de la acción de redacción
Use la acción **Operaciones de datos - Redactar** (compose) para evitar especificar los mismos datos varias veces al diseñar un flujo. Por ejemplo, si necesita especificar una matriz de dígitos: ````[0,1,2,3,4,5,6,7,8,9]```` varias veces al diseñar su flujo puede usar esta acción para guardar la matriz así:

1. Busque **Redactar**y, después, seleccione la acción **Operaciones de datos - Redactar** (compose).
   
    ![buscar y seleccionar la acción redactar](./media/data-operations/search-select-compose.png)
2. Especifique la matriz en el cuadro **Entradas** al que desea hacer referencia posteriormente:
   
    ![configurar la acción de redacción](./media/data-operations/add-array-compose.png)

> [!TIP]
> Para facilitar la posterior referencia, cambie el nombre de la tarjeta **Redactar** haciendo clic en el texto "Redactar" de la barra de título de la tarjeta **Redactar**.
> 
> 

Cuando necesite acceder al contenido de la acción de redacción, hágalo a través del token **Salida** de la lista **Agregue contenido dinámico de las aplicaciones y conectores que se usan en este flujo** mediante estos pasos:

1. Agregue una acción como **Operaciones de datos – Unirse**.
2. Seleccione el control al que desea agregar el contenido que ha guardado en la acción redactar.
   
    Se abre **Agregue contenido dinámico de las aplicaciones y conectores que se usan en este flujo**.
3. En el **Agregue contenido dinámico de las aplicaciones y conectores que se usan en este flujo**, seleccione el token **Salida** que se encuentra debajo de la categoría **Redactar** de la pestaña **Contenido dinámico**.
   
    ![usar salida en la acción de redacción](./media/data-operations/use-compose-output.png)

## <a name="use-the-join-action"></a>Uso de la acción de unirse
Use la acción **Operaciones de datos – Unirse** (join) para delimitar una matriz con el separador que prefiera. Por ejemplo, suponga que el flujo recibe una solicitud web que incluye la siguiente matriz de direcciones de correo electrónico: ````["d@example.com", "k@example.com", "dal@example.com"]````. Sin embargo, el programa de correo electrónico requiere que las direcciones sean una sola cadena separada mediante signos de punto y coma. Para ello, use la acción **Operaciones de datos – Unirse** (join) para cambiar el delimitador de coma a punto y coma ";" siguiendo estos pasos:

1. Agregue una nueva acción, busque **Unirse** y, a continuación, seleccione **Operaciones de datos – Unirse** (join).
   
    ![buscar y seleccionar la acción de unión](./media/data-operations/search-select-join.png)
2. Especifique la matriz en el cuadro **Desde** y, después, escriba el nuevo delimitador que desea utilizar en el cuadro **Unir con**.
   
    En este caso, se ha usado el punto y coma (;) como delimitador nuevo.
   
    ![configurar la acción de unirse](./media/data-operations/add-array-join.png)
3. Guarde el flujo y ejecútelo.
4. Tras la ejecución del flujo, la salida de la acción **Operaciones de datos – Unirse** será:
   
    ![salida de unirse](./media/data-operations/join-output.png)

## <a name="use-the-select-action"></a>Uso de la acción seleccionar
Use la acción **Operaciones de datos – Seleccionar** (select) para transformar la forma de los objetos en una matriz. Por ejemplo, puede agregar, quitar o cambiar el nombre de los elementos de todos los objeto de una matriz.

> [!NOTE]
> Aunque con la acción seleccionar se pueden agregar o quitar elementos, pero no se puede cambiar el número de objetos de la matriz.
> 
> 

Por ejemplo, puede usar la acción seleccionar si los datos entran en el flujo a través de una solicitud web que tenga este formato:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

y desea volver a dar forma a los datos entrantes, para lo que cambiar "first" por "FirstName" y "last" por "LastName", y agrega un nuevo miembro llamado "FamilyName" que "first" y "last" (separados por un espacio):

````[ { "FirstName": "Deon", "FamilyName": "Herb", "FullName": "Deon Herb" }, { "FirstName": "K", "FamilyName": "Herb", "FullName": "K Herb" } ]````.

Para hacerlo:

1. Agregue la acción **Solicitud/respuesta – Respuesta** (request) al flujo.
2. Seleccione **Usar una carga de ejemplo para generar el esquema** en la tarjeta **Solicitud**.
3. En el cuadro que se muestra, pegue un ejemplo de la matriz de datos de origen y, después, seleccione el botón **Listo**.
4. Agregue la acción **Operaciones de datos – Seleccionar** (select) y realice la configuración como muestra la siguiente imagen.
   
    ![configurar la acción seleccionar](./media/data-operations/select-card.png)
   
   > [!TIP]
   > La salida de la acción seleccionar es una matriz que contiene los objetos a los que se vuelve a dar forma. Esta matriz se puede usar posteriormente en cualquier otra acción, como **Redactar**, que ya se ha descrito.
   > 
   > 

## <a name="use-the-filter-array-action"></a>Use la acción filtrar matriz
Use **Operaciones de datos - Filtrar matriz** (matriz de filtro) para reducir el número de objetos de una matriz a un subconjunto que coincida con los criterios que se proporcionan.

> [!NOTE]
> Filtrar matriz no se puede usar para cambiar la forma de los objetos de una matriz. Además, el texto por el que se filtra distingue mayúsculas de minúsculas.
> 
> 

Por ejemplo, filtrar matriz se puede usar en esta matriz:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

para crear una nueva matriz que contenga solo aquellos objetos en los que *first* esté establecido en "Deon".

Vamos a hacerlo.

1. Busque y agregue la acción **Operaciones de datos - Filtrar matriz** (filter array) al flujo.
2. Configure la acción filtrar matriz como se muestra en la imagen siguiente.
   
    ![configurar la acción filtrar matriz](./media/data-operations/add-configure-filter-array.png)
3. Guarde el flujo y ejecútelo.
   
    Puede usar [PostMan](https://www.getpostman.com/postman) para generar una solicitud web que envía una matriz JSON al flujo.
4. Cuando se ejecuta el flujo, siempre que la entrada de JSON sea similar a esta matriz:
   
    ````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````,
   
    la salida es similar a esta matriz (tenga en cuenta que los objetos en los que *first* se establece en "Deon" son los únicos que se incluyen en la salida de la acción):
   
    ````[ { "first": "Deon", "last": "Herb" } ]````

## <a name="use-the-create-csv-table-action"></a>Uso de la acción crear tabla csv
Use la acción **Operaciones de datos - Crear tabla CSV** (create csv table) para cambiar una entrada de una matriz JSON en una tabla de valores separados por comas (CSV). Si lo desea, puede mantener los encabezados visibles en la salida CSV. Por ejemplo, puede convertir la siguiente matriz en una tabla CSV mediante el uso de la acción **Crear tabla CSV**:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

1. Busque, agregue y configure la acción **Operaciones de datos - Crear tabla CSV** de modo que se parezca a la siguiente imagen.
   
    ![configurar la acción crear tabla csv](./media/data-operations/create-csv-table.png)
   
    Nota: El token **Cuerpo** de esta imagen procede de una acción **Solicitud/respuesta – Respuesta**; sin embargo, los datos de entrada de la acción **Crear tabla CSV** se pueden obtener de la salida de cualquier acción anterior del flujo, o bien se pueden escribir directamente en el cuadro **Desde**.
2. Guarde el flujo y ejecútelo.
   
    Cuando se ejecuta el flujo, la salida de **Crear tabla CSV** es similar a esta imagen:
   
    ![crear salida de tabla csv](./media/data-operations/create-csv-table-output.png)

## <a name="use-the-create-html-table-action"></a>Uso de la acción crear tabla html
Use **Operaciones de datos - Crear tabla HTML** para cambiar una entrada de una matriz JSON por una tabla HTML. Si lo desea, puede mantener los encabezados visibles en la salida HTML.

Para ello, siga los pasos descritos en la [sección crear tabla csv](#use-the-create-csv-table-action) para obtener un ejemplo detallado. Asegúrese de utilizar la acción **Operaciones de datos - Crear tabla HTML**, en lugar de la acción **Operaciones de datos - Crear tabla CSV**.

> [!TIP]
> Si planea enviar la tabla HTML por correo electrónico, no olvide seleccionar "IsHtml" en la acción de correo electrónico.
> 
> 

