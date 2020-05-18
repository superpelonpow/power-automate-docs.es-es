---
title: Filtrado y copia de datos | Microsoft Docs
description: Aprenda a filtrar y copiar datos de un origen a un destino con Microsoft Power Automate
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
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6a71b3ae1e72588dc6fb21aad83631a91ae1d4ba
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297723"
---
# <a name="filter-and-copy-data-with-power-automate"></a>Filtrar y copiar datos con Power Automate

En este tutorial se muestra cómo crear un flujo que supervise un origen para los elementos nuevos o cambiado, y, luego, copia dichos cambios a un destino. Puede crear un flujo como este si los usuarios escriben datos en una ubicación, pero el equipo los necesita en otra ubicación o formato.

Aunque este tutorial copie datos de una [lista](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) de Microsoft SharePoint (el origen) a una tabla de [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview) (el destino), es posible copiar datos entre cualesquiera de los más de [150 servicios](https://flow.microsoft.com/connectors/) que admite Power Automate.

> [!IMPORTANT]
> Los cambios que se realizan en el destino no se copian en el origen porque no se admiten las sincronizaciones bidireccionales. Si intenta configurar una sincronización bidireccional, creará un bucle infinito en el que los cambios se envían continuamente entre el origen y el destino.
> 
> 

## <a name="prerequisites"></a>Requisitos previos
* Acceso a un origen de datos y un destino. En este tutorial no se incluyen los pasos para crear el origen y el destino.
* Tener acceso a [Power Automate](https://flow.microsoft.com).
* Conocimientos básicos sobre cómo se almacenan los datos.
* Conocer los aspectos básicos de la creación de flujos. Puede revisar cómo agregar [acciones, desencadenadores](multi-step-logic-flow.md#add-another-action) y [condiciones](add-condition.md). En los pasos siguientes se da por hecho que sabe cómo realizar estas acciones.

> [!TIP]
> No es necesario que coincidan todos los nombres de columna del origen y del destino, pero cuando inserte o actualice un elemento debe especificar los datos de todas las columnas *necesarias*. Power Automate identifica los campos obligatorios.
> 
> 

## <a name="quick-overview-of-the-steps"></a>Descripción rápida de los pasos
Si se siente a gusto con Power Automate, siga estos pasos rápidos para copiar datos desde un origen de datos a otro:

1. Identifique el origen que va a supervisar y el destino al que va a copiar los datos modificados. Confirme que tiene acceso a ambos.
2. Identifique al menos una columna que identifica de forma única los elementos de origen y de destino. En el ejemplo siguiente, se utiliza la columna **Title**, pero puede usar las que desee.
3. Configure un desencadenador que supervise los cambios en el origen.
4. Busque en el destino para determinar si existe el elemento modificado.
5. Use un **condición** similar a la siguiente:
   * Si el elemento nuevo o modificado no existe en el destino, créelo.
   * Si el elemento nuevo o modificado existe en el destino, actualícelo.
6. Desencadene el flujo y, después, confirme que se copian los elementos nuevos o modificados del origen al destino.

> [!NOTE]
> Si no ha creado previamente una conexión a SharePoint o una instancia de Azure SQL Database anteriormente, siga las instrucciones cuando se le pida que inicie sesión.
> 
> 

Estos son los pasos detallados para crear el flujo.

## <a name="monitor-the-source-for-changes"></a>Supervisión del origen de los cambios
1. Iniciar sesión en [Power Automate](https://flow.microsoft.com), seleccione **Mis flujos** > **Crear desde cero**.
2. Busque **SharePoint** y seleccione el desencadenador **SharePoint - Cuando se crea o modifica** un elemento en la lista de desencadenadores.
3. Escriba la **dirección del sitio** y seleccione el **nombre de lista** en la tarjeta **Cuando se crea o se modifica un elemento**.
   
    Especifique los valores de **Dirección del sitio** y **Nombre de lista** de la lista de SharePoint en la que el flujo supervisa si hay elementos nuevos o actualizados.
   
    ![configurar desencadenador de sharepoint](media/odata-filters/configure-sharepoint-trigger.png)

## <a name="search-the-destination-for-the-new-or-changed-item"></a>Búsqueda del elemento nuevo o modificado en el destino
La acción **SQL Server - Obtener filas** se usa para buscar un elemento nuevo o modificado en el destino.

1. Seleccione **Nuevo paso** > **Agregar una acción**.
2. Busque **Obtener filas**, seleccione **SQL Server - Obtener filas** y, después, la tabla que desea supervisar en la lista **Nombre de tabla**.
3. Seleccione **Mostrar opciones avanzadas**.
4. En el cuadro **Consulta de filtro** cuadro, escriba **Título eq '**, seleccione el símbolo (token) **Título** en la lista de contenido dinámico y, después, escriba **'**.
   
    En el paso anterior se da por supuesto que va a asociar los títulos de las filas del origen y del destino.
   
    La tarjeta **Obtener filas** debe parecerse a la de esta imagen:
   
    ![intentar obtener el elemento de la base de datos de destino](media/odata-filters/configure-sql-get-rows-action.png)

## <a name="check-if-the-new-or-changed-item-was-found"></a>Compruebe si se ha encontrado el elemento nuevo o modificado
Seleccione **Nuevo paso** > **Agregar una condición** para abrir la tarjeta **Condición**.

En la tarjeta Condición:

1. Seleccione el cuadro de la izquierda.
   
    Se abrirá la lista **Agregar contenido dinámico de las aplicaciones y conectores que se usan en este flujo**.
2. Seleccione **value** en la categoría **Obtener filas**.
   
   > [!TIP]
   > Confirme que ha seleccionado **value** en la categoría **Obtener filas**. No seleccione **value** en la categoría **Cuando se crea o se modifica un elemento**.
   > 
   > 
3. Seleccione **es igual a** en la lista del cuadro central.
4. Escriba **0** (cero) en el cuadro de la derecha.
   
    La tarjeta **Condición** ahora es como la que aparece en esta imagen:
   
    ![configurar una condición](media/odata-filters/configure-condition.png)
5. Seleccione **Editar en modo avanzado**.
   
    Cuando se abre el modo avanzado, se muestra la expresión **\@equals(body('Get_rows')? ['value'], 0)** en el cuadro. Edite esta expresión mediante la adición de **length()** a la función **body('Get_items')? [' value']**. Ahora la expresión completa es como esta: **@equals(length(body('Get_rows')?['value']), 0)**
   
    La tarjeta **Condición** ahora es como la que aparece en esta imagen:
   
    ![configurar una condición](media/odata-filters/configure-condition-add-length.png)
   
   > [!TIP]
   > Al agregar la función **length()** se permite que el flujo compruebe la lista **value** y determine si contiene algún elemento.
   > 
   > 

Cuando el flujo "obtiene" elementos del destino, hay dos resultados posibles.

| Resultado | Paso siguiente |
| --- | --- |
| El elemento existe |[Actualizar el elemento](odata-filters.md#update-the-item-in-the-destination) |
| El elemento no existe |[Crear un nuevo elemento](odata-filters.md#create-the-item-in-the-destination) |

> [!NOTE]
> Es posible que las imágenes de las tarjetas **Insertar fila** y **Actualizar fila** que se muestran a continuación no sean las mismas que las suyas, ya que estas muestran los nombres de las columnas de la tabla de Azure SQL Database que se usa en el flujo.
> 
> 

## <a name="create-the-item-in-the-destination"></a>Creación del elemento en el destino
Si el elemento no existe en el destino, créelo mediante la acción **SQL Server - Insertar fila**.

En la rama **En caso positivo** de la **condición**:

1. Seleccione **Agregar una acción**, busque **Insertar fila** y seleccione **SQL Server - Insertar fila**.
   
    En la tarjeta **Insertar fila**:
2. En la lista **Nombre de tabla**, seleccione la tabla en la que se va a insertar el nuevo elemento.
   
    La tarjeta **Insertar fila** se expande y muestra todos los campos de la tabla seleccionada. Para que la fila sea válida, los campos con un asterisco (*) son necesarios y se deben rellenar.
3. Seleccione todos los campos que desee rellenar y escriba los datos.
   
    Dichos datos se pueden especificar manualmente, se puede seleccionar uno o varios tokens desde el **contenido dinámico**, o bien se puede especificar cualquier combinación de texto y tokens en los campos.
   
    Ahora, la tarjeta **Insertar fila** es como la que aparece en esta imagen:
   
    ![configurar una condición](media/odata-filters/insert-row.png)

## <a name="update-the-item-in-the-destination"></a>Actualización del elemento en el destino
Si el elemento existe en el destino, actualícelo con los cambios.

1. Agregue la acción **SQL Server - Actualizar fila** a la rama **En caso negativo** de la **condición**.
2. Siga los pasos de la sección de [creación del elemento](odata-filters.md#create-the-item-in-the-destination) de este mismo documento para rellenar los campos de la tabla.
   
    ![ver entornos](media/odata-filters/update-row.png)
3. En la parte superior de la página, escriba el nombre del flujo en el cuadro **Nombre de flujo** y seleccione **Crear flujo** para guardarlo.
   
    ![asignar un nombre al centro](media/odata-filters/give-the-flow-a-name.png)

Ahora, cada vez que cambie algún elemento de la lista de SharePoint (origen), el flujo desencadena e inserta un elemento nuevo, o bien actualiza un elemento existente en la instancia de Azure SQL Database (destino).

> [!NOTE]
> El flujo no se desencadena cuando se elimina un elemento desde el origen. Si se trata de un escenario importante, considere la posibilidad de agregar una columna independiente que indique si un elemento deja de ser necesario.
> 
> 

## <a name="learn-more"></a>Más información
Use [operaciones de datos](data-operations.md) en sus flujos.

