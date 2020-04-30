---
title: Uso de Markdown para dar formato a las aprobaciones de Power Automate | Microsoft Docs
description: Aprenda a usar Markdown para dar formato a las solicitudes de aprobación de Power Automate.
services: ''
suite: flow
documentationcenter: na
author: gcorvera
manager: kfile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/27/2020
ms.author: gcorvera
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 739d407df91661a6a82aa72f2891a3dac3bda3cf
ms.sourcegitcommit: 28adfdffc00c149bc46fab85b7307e4e819000c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "82189620"
---
# <a name="use-markdown-in-power-automate-approval-requests"></a>Uso de Markdown en las solicitudes de aprobación de Power Automate


En este artículo se muestra cómo usar la sintaxis de [Markdown](https://en.wikipedia.org/wiki/Markdown) para agregar formato enriquecido a las solicitudes de aprobación.

> [!IMPORTANT]
> Los correos electrónicos de solicitud de aprobación son *mensajes accionables*. Si el [cliente de Microsoft Outlook](https://docs.microsoft.com/outlook/actionable-messages/#outlook-version-requirements-for-actionable-messages) no admite mensajes accionables, muestra las solicitudes de aprobación en formato HTML. 

> [!IMPORTANT]
> Todos los representadores de Markdown tienen diferencias de implementación. Revise la sección [Compatibilidad con clientes](#client-support) para más información.

## <a name="client-support"></a>Compatibilidad con clientes

La compatibilidad con Markdown entre clientes es incoherente. El equipo de Power Automate trabaja para corregir estas incoherencias, pero aún no ha podido lograrlo. En la tabla siguiente se indican las limitaciones conocidas entre los clientes admitidos.

| Característica | Power Automate | Aplicación móvil de Power Automate | Escritorio de Outlook | Web de Outlook | Teams | Aplicación móvil de Teams |  
|---------|--------|---------------|-----------------|-------------|-------|--------------|
| **Encabezados** | Sí | Sí | Sí | Sí | **_No_** | **_No_** |
| **Listas numeradas** | Sí | Sí | **_No_** | Sí | Sí | Sí |
| **Listas numeradas anidadas** | Sí | Sí | **_No_** | Sí | Sí | Sí |
| **Tablas** | Sí | Sí | Sí | Sí | **_No_** | **_No_** |
| **Imágenes** | **_No_** | **_No_** | **_No_** | **_No_** | **_No_** | **_No_** |
| **Saltos de línea forzosos** | Sí | Sí | **_No_** (usar en su lugar una línea de salto) | Sí | Sí | Sí |
| **Líneas en blanco** | **_No_** | **_No_** | Sí | Sí | **_No_** | Sí |

## <a name="headers"></a>Headers

Estructure sus comentarios mediante encabezados. Los encabezados segmentan los comentarios más largos, lo que facilita su lectura.

Inicie una línea con un carácter de almohadilla `#` para establecer un encabezado. Organice sus comentarios con subtítulos empezando una línea con caracteres de almohadilla adicionales, por ejemplo `####`. Se admiten hasta seis niveles de encabezados.

**Ejemplo:**  
```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Resultado:**  
![Exportación del flujo](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>Párrafos y saltos de línea

Facilite la lectura de su texto dividiéndolo en párrafos o saltos de línea. Escriba dos espacios antes del salto de línea para obligar a la mayoría de los clientes a iniciar una nueva línea.  
   
**Ejemplo:**  
```Markdown
This is line 1.(space, space)
Now text will appear on the next line.
```

**Resultado:**    
Esta es la línea 1.  
Ahora el texto aparecerá en la línea siguiente. 

**Ejemplo 2**  
```Markdown
This is line 1.(space, space)  

Line 2 has extra space before it.
```

**Resultado:**  
Esta es la línea 1.  

La línea 2 tiene delante un espacio adicional.
  

## <a name="lists"></a>Listas

Organice los elementos relacionados con listas. Puede agregar listas ordenadas con números, o listas sin ordenar solo con viñetas.

Las listas ordenadas empiezan con un número seguido de un punto por cada elemento de lista. Las listas desordenadas comienzan con un `*`. Empiece cada elemento de la lista en una nueva línea. En un archivo o widget de Markdown, introduzca dos espacios antes del salto de línea para comenzar un párrafo nuevo, o introduzca dos saltos de línea consecutivamente para comenzar un párrafo nuevo.   

### <a name="ordered-or-numbered-lists"></a>Listas numeradas u ordenadas

**Ejemplo:**  
```Markdown
0. First item.
0. Second item.
0. Third item.
```

**Resultado:**  
1. First item.
2. Second item.
3. Third item.

### <a name="bullet-lists"></a>Listas con viñetas

**Ejemplo:**  
```Markdown
- Item 1
- Item 2
- Item 3
```

**Resultado:**  
- Item 1
- Item 2
- Item 3

### <a name="nested-lists"></a>Listas anidadas

**Ejemplo:**  
```Markdown
1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
   - Nested item 2
   - Nested item 3
```

**Resultado:**  
1. First item.

    - Item 1
    - Item 2
    - Item 3
2. Second item.
    - Nested item 1
    - Nested item 2
    - Nested item 3


## <a name="links"></a>Vínculos

Las direcciones URL HTTP y HTTPS obtienen formato de vínculo automáticamente. 

Puede establecer hipervínculos de texto para la dirección URL utilizando la sintaxis del vínculo de Markdown estándar:

```Markdown
[Link Text](Link URL)
```

**Ejemplo:**  
```Markdown
[Power Automate](https://flow.microsoft.com)
```

**Resultado:**  
[Power Automate](https://flow.microsoft.com)

## <a name="tables"></a>Tablas

Organice datos estructurados con tablas. 

- Coloque cada fila de la tabla en su propia línea 
- Separe las celdas de la tabla con el carácter de barra vertical `|` 
- Las dos primeras líneas de una tabla establecen los encabezados de columna y la alineación de los elementos de la tabla
- Utilice signos de dos puntos (`:`) al dividir el encabezado y el cuerpo de las tablas para especificar la alineación de la columna (izquierda, centro, derecha) 
- Para iniciar una nueva línea, use la etiqueta de salto HTML (`<br/>`)
- Asegúrese de terminar cada fina con un CR o LF. 

**Ejemplo:**  
```Markdown
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```

**Resultado:**  
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:---------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Resaltado (negrita, cursiva, tachado)  

Se puede resaltar texto mediante la aplicación de negrita, cursiva o tachado a los caracteres: 
- Para aplicar cursiva: delimite el texto con un asterisco `*` o carácter de subrayado `_`   
- Para aplicar negrita: delimite el texto con asteriscos dobles `**`.    
- Para aplicar tachado: delimite el texto con caracteres de tilde de la ñ doble `~~`.   

Combine estos elementos para aplicar varios resaltados al texto.    

**Ejemplo:**  
```Markdown
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
```

**Resultado:**  
Use el _resaltado_ en los comentarios para expresar opiniones **contundentes** e indicar <s>correcciones</s> .  
**_Texto en negrita y cursiva_**    
**~~Texto en negrita y tachado~~**  

## <a name="special-characters"></a>Caracteres especiales

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Sintaxis</th>
<th width="350px">Ejemplo/notas</th>
</tr>



<tr>
<td>
<p>Para insertar uno de los caracteres siguientes: coloque delante una barra diagonal inversa:</p>

<p style="margin-bottom:2px;">```\   backslash ``` </p>
<p style="margin-bottom:2px;"><code>\`</code>   `backtick`</p>
<p style="margin-bottom:2px;">```_   underscore  ```</p>
<p style="margin-bottom:2px;">```{}  curly braces  ``` </p>
<p style="margin-bottom:2px;">```[]  square brackets ```</p>
<p style="margin-bottom:2px;">```()  parentheses  ```</p>
<p style="margin-bottom:2px;">```#   hash mark  ``` </p>
<p style="margin-bottom:2px;">```+   plus sign  ```</p>
<p style="margin-bottom:2px;">```-   minus sign (hyphen) ```</p>
<p style="margin-bottom:2px;">```.   dot  ``` </p>
<p style="margin-bottom:2px;">```!   exclamation mark ```</p>


</td>
<td>Algunos ejemplos sobre cómo insertar caracteres especiales
<p>Escriba ```\\``` para obtener \\ </p>
<p>Escriba ```\_``` para obtener _ </p>
<p>Escriba ```\#``` para obtener \# </p>
<p>Escriba ```\(``` para obtener \( </p>
<p>Escriba ```\.``` para obtener \. </p>
<p>Escriba ```\!``` para obtener \! </p>
</td>
</tr>

</tbody>
</table>
