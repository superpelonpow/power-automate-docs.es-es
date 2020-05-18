---
title: Uso de expresiones con condiciones. | Microsoft Docs
description: Usar expresiones avanzadas como "and", "or", "empty", "less" y "greater" con las condiciones de Power Automate.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/15/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3c1eb0f208f964f2a41e26ca831c60edef0d747c
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298449"
---
# <a name="use-expressions-in-conditions-to-check-multiple-values"></a>Uso de expresiones en condiciones para comprobar varios valores

En este tutorial, aprenderá a utilizar expresiones y **condiciones** para comparar varios valores en **modo avanzado**.

Cuando se crea un flujo, puede usar la tarjeta [**Condición**](add-condition.md#add-a-condition) en modo básico para comparar rápidamente un valor individual con otro. Sin embargo, hay veces en las que necesita comparar varios valores. Por ejemplo, puede comprobar el valor de varias columnas de una hoja de cálculo o de una tabla de base de datos.

En las condiciones puede usar cualquier combinación de las siguientes expresiones lógicas.

Expression|Descripción|Ejemplo
--------|-----------|-------
|[y](#use-the-and-expression)|Toma dos argumentos y devuelve true si ambos valores son true.<br><b>Nota</b>: ambos argumentos deben ser valores booleanos.|Esta expresión devuelve false: <br>and(greater(1,10),equals(0,0))
|[o](#use-the-or-expression)|Toma dos argumentos y devuelve true si cualquiera de los dos argumentos es true. <br><b>Nota</b>: ambos argumentos deben ser valores booleanos.|Esta expresión devuelve true:<br>or(greater(1,10),equals(0,0))
|es igual a|Devuelve true si los dos valores son iguales.|Por ejemplo, si el valor de parameter1 es someValue, esta expresión devuelve true:<br>equals(parameters('parameter1'), 'someValue')
|[menos](#use-the-less-expression)|Toma dos argumentos y devuelve true si el primer argumento es menor que el segundo. <br><b>Nota</b>: los tipos admitidos son integer, float y string.|Esta expresión devuelve true:<br>less(10,100)
|lessOrEquals|Toma dos argumentos y devuelve true si el primer argumento es menor o igual que el segundo. <br><b>Nota</b>: los tipos admitidos son integer, float y string.|Esta expresión devuelve true:<br>lessOrEquals(10,10)
|[mayor que](#use-the-greater-expression)|Toma dos argumentos y devuelve true si el primero es mayor que el segundo. <br><b>Nota</b>: los tipos admitidos son integer, float y string.|Esta expresión devuelve false:<br>greater(10,10)
|greaterOrEquals|Toma dos argumentos y devuelve true si el primer argumento es mayor o igual que el segundo. <br><b>Nota</b>: los tipos admitidos son integer, float y string.|Esta expresión devuelve false:<br>greaterOrEquals(10,100)
|[empty](#use-the-empty-expression)|Devuelve true si el objeto, matriz o cadena están vacíos.|Esta expresión devuelve true:<br>empty('')
|not|Devuelve el opuesto de un valor booleano. |Esta expresión devuelve true:<br>not(contains('200 Success','Fail'))
|if|Devuelve un valor específico si el resultado de la expresión es true o false.|Esta expresión devuelve "yes":<br>if(equals(1, 1), 'yes', 'no')

## <a name="prerequisites"></a>Requisitos previos
* Obtenga acceso a Power Automate.
* Una hoja de cálculo con las tablas que se describirán más adelante en este tutorial. Asegúrese de guardar la hoja de cálculo en una ubicación como Dropbox o Microsoft OneDrive para que Power Automate pueda acceder a ella.
* Microsoft Office 365 Outlook (aunque aquí se usa Office 365 Outlook, se puede utilizar cualquier servicio de correo electrónico compatible en los flujos).

## <a name="use-the-or-expression"></a>Use la expresión or
En ocasiones un flujo de trabajo debe realizar una acción si el valor de un elemento es valueA **o** valueB. Por ejemplo, puede hacer un seguimiento del estado de las tareas de una tabla de una hoja de cálculo. Suponga que la tabla tiene una columna denominada *Estado* y los posibles valores en la columna *Estado* son:

* **completed**
* **blocked**
* **unnecessary**
* **not started**

A continuación se muestra un ejemplo del aspecto que podría tener la hoja de cálculo:

![hoja de cálculo de ejemplo](./media/use-expressions-in-conditions/spreadsheet-table.png)

Dada la hoja de cálculo anterior, es posible que desea usar Power Automate para quitar todas las filas con una columna *Estado* que se establece en *completed* o *unnecesary*.

Vamos a crear el flujo.

### <a name="start-with-a-blank-flow"></a>Comience con un flujo en blanco
1. Inicie sesión en [Power Automate](https://flow.microsoft.com).

    ![iniciar sesión](includes/media/modern-approvals/sign-in.png)
2. Seleccione la pestaña **Mis flujos**.

    ![seleccionar mis flujos](includes/media/modern-approvals/select-my-flows.png)
3. Seleccione **Crear desde cero**.

    ![crear desde cero](includes/media/modern-approvals/blank-template.png)

### <a name="add-a-trigger-to-your-flow"></a>Agregue un desencadenador al flujo
1. Busque **Programación** y seleccione el desencadenador **Programación - Periodicidad**

    ![desencadenador de programación](includes/media/schedule-trigger/schedule-trigger.png)
2. Configure la programación para que se ejecute una vez al día.

    ![configurar programación](includes/media/schedule-trigger/set-schedule.png)

### <a name="select-the-spreadsheet-and-get-all-rows"></a>Seleccione la hoja de cálculo y obtenga todas las filas
1. Seleccione **Nuevo paso** > **Agregar una acción**.

    ![nuevo paso](includes/media/new-step/action.png)
2. Busque **filas** y seleccione **Excel - Obtener filas**.

    Nota: Seleccione la acción "obtener filas" que corresponda a la hoja de cálculo que vaya a usar. Por ejemplo, si va a utilizar Hojas de cálculo de Google, seleccione **Hojas de cálculo de Google - Obtener filas**.

    ![obtener filas](includes/media/new-step/get-excel-rows.png)
3. Seleccione el icono de la carpeta en el cuadro **Nombre de archivo**, busque la hoja de cálculo que contiene los datos y selecciónela.

    ![seleccionar hoja de cálculo](includes/media/new-step/select-spreadsheet.png)
4. Seleccione la tabla que contiene los datos en la lista **Nombre de tabla**.

    ![seleccionar tabla](includes/media/new-step/select-table.png)

### <a name="check-the-status-column-of-each-row"></a>Compruebe la columna de estado de cada fila
1. Seleccione **Nuevo paso** > **Más** > **Agregar Aplicar a cada uno**.

    ![seleccionar tabla](includes/media/new-step/apply-to-each.png)
2. Agregue el token **Valor** al cuadro **Seleccionar una salida de los pasos**.

    ![seleccionar tabla](includes/media/apply-to-each/add-value-token.png)
3. Seleccione **Agregar una condición** > **Editar en el modo avanzado**.
4. Agregue la siguiente expresión **or**. Esta expresión **or** comprueba el valor de cada fila de la tabla (una fila se conoce como un elemento cuando se accede a ella en una expresión). Si el valor de la columna **status** es *completed* **o** *unnecesary*, la expresión **or** se evalúa como "true".

    La expresión **or** aparece como se muestra aquí:

    ````@or(equals(item()?['status'], 'unnecessary'), equals(item()?['status'], 'completed'))````

    La tarjeta **Condición** es como la que aparece en esta imagen:

    ![Imagen de la expresión or](./media/use-expressions-in-conditions/or-expression.png)

### <a name="delete-matching-rows-from-the-spreadsheet"></a>Eliminación de las filas coincidentes de la hoja de cálculo
1. Seleccione **Agregar una acción** en la sección **IF YES, DO NOTHING** (En caso positivo, no hacer nada) de la condición.
2. Busque **Eliminar fila**y, después, seleccione **Excel - Eliminar fila**.

    ![imagen de eliminar fila](includes/media/new-step/select-delete-excel-row.png)
3. En el cuadro **Nombre de archivo**, busque y seleccione el archivo de la hoja de cálculo que contiene los datos que desea eliminar.
4. En la lista **Nombre de tabla**, seleccione la tabla que contiene los datos.
5. Coloque el token **Id. de fila** en el cuadro **Id. de fila**.

    ![archivo de hoja de cálculo](includes/media/new-step/delete-excel-row.png)

### <a name="name-the-flow-and-save-it"></a>Asigne un nombre al flujo y guárdelo
1. Asigne un nombre al flujo y haga clic en el botón **Crear flujo**.

    ![guardar el flujo](./media/use-expressions-in-conditions/name-and-save.png)

### <a name="run-the-flow-with-the-or-expression"></a>Ejecución del flujo con la expresión or
El flujo se ejecuta después de que se guarda. Si ha creado la hoja de cálculo que se ha mostrado anteriormente en el tutorial, así debería ser una vez que se complete la ejecución:

![Se completa la expresión or](./media/use-expressions-in-conditions/spreadsheet-table-after-or-expression-runs.png)

Observe que se han eliminado todos los datos de las filas en los que aparece "completed" o "unnecessary" en la columna Status.

## <a name="use-the-and-expression"></a>Use la expresión and
Suponga que tiene una tabla de hoja de cálculo con dos columnas, cuyos nombres son Status y Assigned. Suponga también que desea eliminar todas las filas si el valor de la columna Status es "blocked" y el valor de la columna Assigned es "John Wonder".  Para realizar esta tarea, siga todos los pasos indicados anteriormente en este tutorial, pero cuando edite la tarjeta **Condición** en modo avanzado, use la expresión **and** que se muestra aquí:

````@and(equals(item()?['Status'], 'blocked'), equals(item()?['Assigned'], 'John Wonder'))````

La tarjeta **Condición** es como la que aparece en esta imagen:

![Imagen de la expresión and](./media/use-expressions-in-conditions/and-expression.png)

### <a name="run-the-flow-with-the-and-expression"></a>Ejecución del flujo con la expresión and
Si ha seguido todos los pasos, la hoja de cálculo se parecerá a la de la siguiente imagen:

![antes de que se ejecute and](./media/use-expressions-in-conditions/spreadsheet-table-before-and-expression-runs.png)

Después de la ejecución del flujo, la hoja de cálculo es similar a la de esta imagen:

![después de que se ejecute and](./media/use-expressions-in-conditions/spreadsheet-table-after-and-expression-runs.png)

## <a name="use-the-empty-expression"></a>Utilice la expresión empty
Observe que ahora hay varias filas vacías en la hoja de cálculo. Para quitarlas, utilice la expresión **empty** para identificar todas las filas que no tengan texto en las columnas Assigned y Status.

Para realizar esta tarea, siga todos los pasos indicados en la sección **Uso de la expresión and** de este tutorial, sin embargo, cuando edite la tarjeta **Condición** en modo avanzado, use la expresión empty como se muestra a continuación:

````@and(empty(item()?['Status']), empty(item()?['Assigned']))````

La tarjeta **Condición** es como la que aparece en esta imagen:

![Imagen de la expresión empty](./media/use-expressions-in-conditions/empty-expression.png)

Después de la ejecución del flujo, la hoja de cálculo es similar a la de esta imagen:

![después de que se ejecute empty](./media/use-expressions-in-conditions/spreadsheet-table-after-empty-expression-runs.png)

Tenga en cuenta que las líneas adicionales se quitan de la tabla.

## <a name="use-the-greater-expression"></a>Uso de la expresión greater
Imagine que ha comprado entradas para un partido de béisbol para sus compañeros de trabajo y que usa una hoja de cálculo para asegurarse de que todos se las pagan. Puede crear rápidamente un flujo que envíe un correo electrónico diario a cada persona que no haya pagado la cantidad total.

Use la expresión **greater** para identificar los empleados que no hayan pagado la cantidad total. Posteriormente, puede enviar automáticamente un recordatorio amistoso por correo electrónico a quienes no hayan pagado la totalidad.

Esta es una vista de la hoja de cálculo:

![vista de la hoja de cálculo](./media/use-expressions-in-conditions/tickets-spreadsheet-table.png)

Esta es la implementación de la expresión **greater** que identifica a todas las personas que han pagado menos de lo que deben:

````@greater(item()?['Due'], item()?['Paid'])````

## <a name="use-the-less-expression"></a>Uso de la expresión less
Suponga que ha comprado entradas para un partido de béisbol para sus compañeros de trabajo y que usa una hoja de cálculo para asegurarse de que todos se las pagan antes de la fecha acordada. Puede crear un flujo que envíe un recordatorio por correo electrónico a todos aquellos que no hayan pagado el importe íntegro si la fecha actual es menos de un día antes de la fecha de vencimiento.

Use la expresión **and** junto con la función **less**, ya que se deben validar dos condiciones:


|          Condición que se valida          | expresión que se usa |                    Ejemplo                     |
|-----------------------------------------|-------------------|------------------------------------------------|
|   ¿Se ha pagado el importe total que se debe?    |      mayor que      |   @greater(item()?['Due'], item()?['Paid'])    |
| ¿Es el fecha de vencimiento inferior a un día? |       menos        | @less(item()?['DueDate'], addDays(utcNow(),1)) |

## <a name="combine-the-greater-and-less-expressions-in-an-and-expression"></a>Combinación de las expresiones greater y less en una expresión and
Utilice la expresión **greater** para identificar a los empleados que han pagado menos que la cantidad total que se debe y la expresión **less** para determinar si la fecha de vencimiento del pago sea inferior a un día desde la fecha actual. Luego puede usar la acción **Enviar un correo electrónico** para enviar un recordatorio amistoso por correo electrónico a aquellos que no hayan pagado la totalidad cuando la fecha de vencimiento sea inferior a un día.

Esta es una vista de la tabla de la hoja de cálculo:

![vista de la hoja de cálculo](./media/use-expressions-in-conditions/spreadsheet-table-due-date.png)

Esta es la implementación de la expresión **and** que identifica a todas las personas que han pagado una cantidad inferior a la que debe y cuya fecha de vencimiento sea inferior a un día desde la fecha actual:

````@and(greater(item()?['Due'], item()?['Paid']), less(item()?['dueDate'], addDays(utcNow(),1)))````

## <a name="use-functions-in-expressions"></a>Uso de funciones en expresiones

Algunas expresiones obtienen sus valores de acciones en tiempo de ejecución que es posible que aún no existan cuando un flujo empiece a ejecutarse. Para hacer referencia a estos valores o trabajar con ellos en expresiones, puede usar las funciones que proporciona el lenguaje de definición de flujo de trabajo. Más información: [Referencia de funciones para el lenguaje de definición de flujo de trabajo en Power Automate](https://docs.microsoft.com/azure/logic-apps/workflow-definition-language-functions-reference)
