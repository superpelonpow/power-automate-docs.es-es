---
title: 'Ejemplo: Uso de flujos de proceso de negocio | MicrosoftDocs'
description: En el ejemplo se muestra cómo trabajar con flujos de proceso de negocio mediante programación, por ejemplo para recuperar instancias del flujo de proceso de negocio para un registro de entidad, recuperar la ruta de acceso activa de una instancia de flujo de proceso de negocio y sus fases, y cambiar la fase activa.
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
ms.assetid: 7d378504-b4b2-4a09-838c-69ee094072ef
caps.latest.revision: 15
author: msftman
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 4f7566c6d6430c9167c0d1b7cc082792d0939780
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297767"
---
# <a name="sample-work-with-business-process-flows"></a>Ejemplo: Trabajar con flujos de proceso de negocio
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

En este ejemplo se muestra cómo trabajar con flujos de proceso de negocio mediante programación, por ejemplo para recuperar instancias del flujo de proceso de negocio para un registro de entidad, recuperar la ruta de acceso activa de una instancia de flujo de proceso de negocio y sus fases, y cambiar la fase activa. Para obtener información sobre estos conceptos, vea [Work with business process flows using code](business-process-flows-code.md) (Trabajar con flujos de proceso de negocio mediante código).  

 Este ejemplo está disponible para descargar desde [Ejemplo: Trabajar con flujos de proceso de negocio](https://go.microsoft.com/fwlink/p/?LinkId=846108).  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Antes de poder ejecutar el ejemplo:  

1. Obtenga acceso a un entorno de Common Data Service.  

2. Tener los privilegios adecuados en las entidades Cliente potencial, Oportunidad y Flujo de trabajo, y los registros de entidad de definición de flujo de trabajo de proceso de negocio que se usan en este ejemplo.  

3. Utilice Visual Studio 2015 o posterior para ejecutar el ejemplo.  

4. Se requiere conexión a Internet para descargar el proyecto de ejemplo y para restablecer los paquetes de NuGet que se usan en el proyecto de ejemplo.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>Qué hace este ejemplo  

1.  Crea un registro de cliente potencial de ejemplo. Esto crea automáticamente una instancia del flujo de proceso de negocio “Proceso de venta de cliente potencial a oportunidad" para el registro de cliente potencial.  

2.  Convierte el registro de cliente potencial a un registro de oportunidad.  


4.  Recupera las instancias de flujo de proceso de negocio asociadas al registro de” oportunidad” mediante el mensaje `RetrieveProcessInstances`. El primer registro de la colección devuelta es la instancia de flujo de proceso de negocio activa para el registro de oportunidad, que es “Proceso de venta de cliente potencial a oportunidad” en este caso.  

5.  Recupera la ruta activa y las fases de proceso para la instancia "Proceso de venta de cliente potencial a oportunidad” mediante el mensaje `RetrieveActivePath`.  

6.  Recupera la fase activa actualmente para la instancia "Proceso de venta de cliente potencial a oportunidad”, y pregunta al usuario si pasa a la siguiente fase. Si se confirmación el paso, se establece la siguiente fase en la ruta activa como la fase activa para la instancia "Proceso de venta de cliente potencial a oportunidad”.  

7.  Finalmente, pide al usuario que elimine los registros de entidad creados durante la ejecución de ejemplo.  

     Esta es la salida del ejemplo:  

    ![Salida de muestra](media/work-with-bpf-sample-output.png "Salida de ejemplo")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Ejecutar el ejemplo  

1. [Descargue el proyecto de ejemplo](https://go.microsoft.com/fwlink/p/?LinkId=846108) WorkWithBPFVisual Studio, y extráigalo en una carpeta de su equipo.  

2. Busque el archivo `WorkWithBPF.sln` en la carpeta extraída, y ábralo en Visual Studio.  

3. El proyecto de ejemplo usa los paquetes de NuGet que se deben restablecer antes de ejecutar el ejemplo. Asegúrese de que la restauración automática de los paquetes de NuGet está habilitada en Visual Studio. Más información: [Habilitación y deshabilitación de restauración de paquetes de NuGet](https://go.microsoft.com/fwlink/?linkid=846106)  

    Como alternativa, seleccione **Proyecto** > **Administrar paquetes de NuGet** y seleccione **Restaurar** para restablecer manualmente los paquetes que se usan en el ejemplo.  

4. Presione la F5 o seleccione **Depurar** > **Iniciar depuración**.  

5. Si no ha ejecutado antes uno de los ejemplos, tendrá que especificar información para ejecutar el código; en caso contrario, escriba el número de una de las instancias que ha configurado previamente.  


   |                                 Pregunta                                  |                                                                                             Descripción                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Escriba un nombre de servidor y un puerto de Dynamics 365 [crm.dynamics.com]       | Escriba el nombre de su Dynamics 365 server. El valor predeterminado es Dynamics 365 (online) (crm.dynamics.com) en Norteamérica.<br /><br /> Ejemplo: <br />crm5.dynamics.com |
   | Está esta organización aprovisionada en servicios en línea de Microsoft (y/n) [n] |                                                 Escriba **y** si esta es una organización aprovisionada en servicios en línea de Microsoft. De lo contrario, escriba **n**.                                                  |
   |                          Escriba domain\username                          |                                                                                    Escriba su cuenta de Microsoft.                                                                                     |
   |                             Escriba la contraseña                              |                      Escriba la contraseña. Los caracteres se mostrarán en la ventana como "\*". Su contraseña se guardará con seguridad en el Administrador de credenciales de Microsoft para poder utilizarla posteriormente.                       |
   |                Especifique un número de organización (1-n) [1]                 |                      En la lista de organizaciones que muestra que usted pertenece, escriba el número correspondiente. El valor predeterminado es 1, que indica la primera organización de la lista.                       |


6. El ejemplo realizará las operaciones descritas en [¿Qué hace este ejemplo?](#what-this-sample-does) y puede pedirle opciones adicionales.  

7. Cuando se complete el ejemplo, presione ENTRAR para cerrar la ventana de consola.  

