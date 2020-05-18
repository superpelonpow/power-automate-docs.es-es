---
title: Introducción a los tokens de desencadenadores de botones | Microsoft Docs
description: Introducción a los tokens de desencadenadores de botones para flujos de botón de Microsoft.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/12/2016
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d2a7cbf1f3bb582853583a790e2bd26f319655d3
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297503"
---
# <a name="get-started-with-button-trigger-tokens"></a>Introducción a los tokens de desencadenadores de botones

## <a name="what-are-button-trigger-tokens"></a>¿Qué son los tokens de desencadenadores de botones?
Los tokens de desencadenadores de botones son puntos de datos conocidos y disponibles para el dispositivo en el que un [flujo de botones](introduction-to-button-flows.md) se está ejecutando. Estos tokens cambian en función de factores como la hora actual o la ubicación geográfica del dispositivo en un momento dado.  

Por ejemplo, si está ejecutando un flujo de botones en un smartphone, es probable que el **teléfono conozca la hora** en su ubicación actual, así como la fecha y la dirección actuales. En este contexto, la hora, la fecha y la dirección donde se encuentra el teléfono están determinadas en el momento en que se ejecuta el flujo de botones. Están automáticamente disponibles para su uso en los flujos de botones que se ejecutan en el dispositivo. Puede usar estos tokens de desencadenadores para generar flujos útiles que minimizarán tareas repetitivas como proporcionar la ubicación a alguien o realizar el seguimiento de cuánto tiempo ha tardado en una llamada de trabajo o servicio determinada.

### <a name="list-of-button-trigger-tokens"></a>Lista de tokens de desencadenador de botón
Esta es la lista de los tokens de desencadenadores de botones que están disponibles para su uso al crear los flujos de botones.

| Parámetro | Descripción |
| --- | --- |
| Ciudad |Ciudad donde se encuentra el dispositivo que ejecuta el flujo. |
| País o región |País o la región donde se encuentra el dispositivo que ejecuta el flujo. |
| Full address |La dirección completa donde se encuentra el dispositivo que está ejecutando el flujo. |
| Latitud |La latitud en la que se encuentra el dispositivo que ejecuta el flujo. |
| Longitud |La longitud en la que se encuentra el dispositivo que ejecuta el flujo. |
| PostalCode |El código postal en el que se encuentra el dispositivo que ejecuta el flujo. |
| Estado o provincia |El estado en el que se encuentra el dispositivo que ejecuta el flujo. |
| Calle |La calle en la que se encuentra el dispositivo que ejecuta el flujo. |
| Marca de tiempo |La hora en el área donde se encuentra el dispositivo que está ejecutando el flujo. |
| Fecha |La fecha en el área donde se encuentra el dispositivo que está ejecutando el flujo. |
| Nombre de usuario |El nombre de usuario de la persona que inició sesión en el dispositivo que está ejecutando el flujo. |
| User email |La dirección de correo electrónico de la persona que inició sesión en el dispositivo que está ejecutando el flujo. |

## <a name="create-a-button-flow-that-uses-trigger-tokens"></a>Creación de un flujo de botón que usa tokens de desencadenador
Cuando crea un botón, puede utilizar tokens de desencadenadores para agregarle funciones enriquecidas.

En este tutorial se creará un flujo de botones en un dispositivo Android. El flujo de botones utilizará tokens de desencadenadores para enviar la fecha y la dirección completa en un correo electrónico con asunto "**Trabajo desde casa**" a su jefe.

En este tutorial, verá capturas de pantalla de un dispositivo Android, sin embargo, la experiencia es similar en los dispositivos de iOS y Windows Phone.

### <a name="prerequisites"></a>Requisitos previos
* Una dirección de correo electrónico profesional o educativa o una [cuenta de Microsoft](https://account.microsoft.com/about?refd=www.microsoft.com) con acceso a Power Automate.
* La aplicación móvil de Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).

Empecemos:

1. Inicie Flow y seleccione **Examinar**   
   ![token de desencadenador de botones](./media/introduction-to-button-trigger-tokens/1.png)  
2. Seleccione el servicio **Enviar un correo electrónico 'Trabajo desde casa hoy' a su jefe** en la categoría **Botón**   
   ![token de desencadenador de botones](./media/introduction-to-button-trigger-tokens/2.png)  
3. Seleccione **USAR ESTA PLANTILLA**  
   ![token de desencadenador de botones](./media/introduction-to-button-trigger-tokens/3.png)  
4. Seleccione **Editar** en la tarjeta **Enviar un correo electrónico**  
   ![token de desencadenador de botones](./media/introduction-to-button-trigger-tokens/3-5.png)  
5. Pulse en el cuadro de texto **Asunto** y escriba: "**hoy -**" después del texto "WFH". Tenga en cuenta que cuando pulse en el cuadro de texto, se abrirá también una lista de parámetros/tokens. Vamos a usar uno de estos tokens en el paso siguiente para agregar la fecha al asunto del correo electrónico.  
   ![token de desencadenador de botones](./media/introduction-to-button-trigger-tokens/4.png)  
6. Con el cursor todavía en el cuadro de texto del asunto, desplácese hasta la lista **manual** de parámetros y pulse **Fecha**. Observe que el parámetro de fecha está ahora en el cuadro de texto **Asunto**:  
   ![token de desencadenador de botones](./media/introduction-to-button-trigger-tokens/6.png)  
7. Desplácese hasta el cuadro de texto **Cuerpo** y pulse después del mensaje predeterminado para que los tokens adicionales se puedan incluir allí.  
   ![token de desencadenador de botones](./media/introduction-to-button-trigger-tokens/7.png)  
8. Pulse en el parámetro **Dirección completa** y, a continuación, pulse en **Crear**  
   ![token de desencadenador de botones](./media/introduction-to-button-trigger-tokens/8.png)  
9. Pulse en **Listo**. Se ha creado el flujo de botón.  
   ![token de desencadenador de botones](./media/introduction-to-button-trigger-tokens/9.png)  

## <a name="run-the-button-flow"></a>Ejecución del flujo de botón
**NOTA**: este flujo de botones enviará su ubicación actual a través de correo electrónico.  

1. Pulse la categoría **Botones** en la parte inferior de la pantalla. Verá una lista de los botones de los que tiene permiso para usarlos. Pulse el botón que representa el flujo de botones que acaba de crear:  
   ![token de desencadenador de botones](./media/introduction-to-button-trigger-tokens/10.png)  
2. Pulse **PERMITIR** para indicar que está de acuerdo con que el flujo de botones acceda a la información de ubicación del dispositivo:  
   ![token de desencadenador de botones](./media/introduction-to-button-trigger-tokens/11.png)  
3. En unos instantes, observe que el correo electrónico se envió a su jefe:  
   ![token de desencadenador de botones](./media/introduction-to-button-trigger-tokens/12.png)  

Enhorabuena, ha creado un flujo de botones que utiliza los tokens de desencadenadores de la fecha y la dirección completa. 

## <a name="next-steps"></a>Pasos siguientes
* [Compartir flujos de botones](share-buttons.md)
* [Más información sobre los flujos de botones](introduction-to-button-flows.md)
