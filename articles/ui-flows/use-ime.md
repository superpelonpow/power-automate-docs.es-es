---
title: Uso de editores de métodos de entrada (IME) en flujos de interfaz de usuario | Microsoft Docs
description: Obtenga más información sobre el uso de editores de métodos de entrada (IME) en flujos de interfaz de usuario.
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
ms.date: 02/25/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 167f9321dba853e801102bed2ebe7e8902437d71
ms.sourcegitcommit: 26cda5060446812f3725ccd4fe435839088f50fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "78253189"
---
# <a name="use-input-method-editors-imes-in-ui-flows"></a>Uso de editores de métodos de entrada (IME) en flujos de interfaz de usuario

Puede usar la característica **Agregar texto estático** para grabar entradas de texto en cualquier idioma con editores de métodos de entrada (IME) o teclados normales. Use **Agregar texto estático** si quiere que la automatización inserte el mismo texto cada vez que se ejecute el flujo de interfaz de usuario. 

>[!TIP]
>Use **Entrada de texto** si tiene previsto usar texto dinámico que cambie cada vez que se ejecute el flujo de interfaz de usuario.

## <a name="invoke-ime"></a>Invocación de IME

Siga estos pasos cuando haya empezado a grabar y esté a punto para insertar la entrada de texto estático:

1. Seleccione el control en el que quiera escribir el texto estático.

   ![Selección del control](../media/use-ime/select-control.png)

1. Seleccione **Usar entrada** en la grabadora y, después, **Agregar texto estático**.

   ![Selección de Agregar texto estático](../media/use-ime/add-static-text.png)

   Verá un cuadro de entrada en el que escribir el texto estático. Puede usar el IME, inglés o cualquier teclado internacional.

   ![Escritura de texto estático](../media/use-ime/enter-static-text.png)

1. Escriba el texto.

1. Seleccione **Agregar a la aplicación** y, después, el control en el que quiera insertar el texto. Verá el texto insertado en el control. 

   Este texto se escribirá automáticamente en el momento de la reproducción, incluso aunque las máquinas de reproducción no tengan las mismas distribuciones de teclado o el IME que se haya empleado en la grabación.

   ![Texto de reproducción](../media/use-ime/playback-text.png)

   >[!TIP]
   >En Web Designer, expanda la acción **Insertar entrada de texto** para revisar o editar el texto.

   ![Inserción de la entrada de texto](../media/use-ime/insert-text-input.png)


## <a name="use-the-replay-keystroke-action"></a>Uso de la acción de pulsación de tecla en la reproducción

Si ha grabado una entrada de texto sin usar la opción **Agregar texto estático**, cada pulsación se grabará y se reproducirá cronológicamente. Esto incluye las teclas especiales como CTRL, ALT, Windows, etc. en inglés o en cualquier otra distribución de teclado internacional.

En el diseñador, puede revisar y editar la información de grabación en el formato [Tecla virtual](https://docs.microsoft.com/windows/win32/inputdev/virtual-key-codes) en la acción **Reproducir pulsaciones de teclas**. 

![Tecla virtual](../media/use-ime/virtual-key.png)


> [!NOTE]
> Una versión anterior de la grabadora de los flujos de interfaz de usuario usaba las acciones **SendKeys** y **PostElement**. Estas acciones quedarán en desuso. Se recomienda actualizar la grabadora de flujos de interfaz de usuario a la versión más reciente y, después, volver a grabar los scripts para aprovechar las ventajas de las nuevas características.

## <a name="troubleshooting-tips"></a>Sugerencias de solución de problemas

1. Si graba acciones de teclado con el modo **Reproducir pulsaciones de teclas**, asegúrese de que la máquina de reproducción use el mismo teclado que el entorno de grabación, ya que, en distintos teclados, las mismas secuencias de teclas de reproducción pueden introducir valores distintos.

1. Solo puede aplicar **Usar entrada** a los controles que sean de tipo texto. Actualmente, **Usar entrada** no permite escribir texto en otros tipos de controles, como cuadros combinados, listas desplegables, elementos ListView, etc.

## <a name="next-steps"></a>Pasos siguientes

- Obtenga información sobre cómo [configurar flujos de interfaz de usuario](setup.md). 
- Obtenga más información sobre los [diferentes tipos de flujos](..\getting-started.md#types-of-flows) que puede usar para automatizar los flujos de trabajo.


