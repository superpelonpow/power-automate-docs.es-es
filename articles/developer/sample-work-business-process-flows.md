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
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74364727"
---
# <a name="sample-work-with-business-process-flows"></a>Ejemplo: Trabajar con flujos de proceso de negocio
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

En este ejemplo se muestra cómo trabajar con flujos de proceso de negocio mediante programación, por ejemplo para recuperar instancias del flujo de proceso de negocio para un registro de entidad, recuperar la ruta de acceso activa de una instancia de flujo de proceso de negocio y sus fases, y cambiar la fase activa. Para obtener información sobre estos conceptos, vea [Work with business process flows using code](business-process-flows-code.md) (Trabajar con flujos de proceso de negocio mediante código).  

 Este ejemplo está disponible para descargar desde [Sample: Work with business process flows](https://go.microsoft.com/fwlink/p/?LinkId=846108) (Ejemplo: Trabajar con flujos de proceso de negocio empresariales).  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Antes de poder ejecutar el ejemplo:  

1. Tener acceso a un entorno de Common Data Service.  

2. Tener los privilegios adecuados en las entidades Cliente potencial, Oportunidad y Flujo de trabajo, y los registros de entidad de definición de flujo de trabajo de proceso de negocio que se usan en este ejemplo.  

3. Tener Visual Studio 2015 o una versión posterior para ejecutar el ejemplo.  

4. Tener conexión a Internet para descargar el proyecto de ejemplo y restaurar los paquetes NuGet que se usan en el proyecto de ejemplo.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>Qué hace este ejemplo  

1.  Crea un registro Cliente potencial de ejemplo. Esto crea de forma automática una instancia del flujo de proceso de negocio "Proceso de cliente potencial a ventas de la oportunidad" para el registro Cliente potencial.  

2.  Convierte el registro Cliente potencial en un registro Oportunidad.  


4.  Recupera las instancias de flujo de proceso de negocio asociadas con el registro "Oportunidad" mediante el mensaje `RetrieveProcessInstances`. El primer registro de la colección que se devuelve es la instancia de flujo de proceso de negocio activa para el registro de oportunidad que, en este caso, es "Proceso de cliente potencial a ventas de la oportunidad".  

5.  Recupera la ruta de acceso activa y las fases de proceso para la instancia de "Proceso de cliente potencial a ventas de la oportunidad" mediante el mensaje `RetrieveActivePath`.  

6.  Recupera el escenario activo actualmente para la instancia de "Proceso de cliente potencial a ventas de la oportunidad" y pregunta al usuario si quiere pasar a la fase siguiente. Después de confirmarlo, establece la fase siguiente de la ruta de acceso activa en la fase activa para la instancia de "Proceso de cliente potencial a ventas de la oportunidad".  

7.  Por último, pregunta al usuario si quiere eliminar los registros creados durante la ejecución de ejemplo.  

     Este es el resultado del ejemplo:  

    ![Salida de ejemplo](media/work-with-bpf-sample-output.png "Salida de ejemplo")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Ejecución del ejemplo  

1. [Descargue](https://go.microsoft.com/fwlink/p/?LinkId=846108) el proyecto de ejemplo WorkWithBPF de Visual Studio y extráigalo en una carpeta en el equipo.  

2. Busque el archivo `WorkWithBPF.sln` en la carpeta que ha extraído y ábralo en Visual Studio.  

3. En el proyecto de ejemplo se usan paquetes NuGet que se deben restaurar antes de ejecutar el ejemplo. Asegúrese de que la restauración automática de paquetes NuGet está habilitada en Visual Studio. Más información: [Habilitar y deshabilitar la restauración de paquetes NuGet](https://go.microsoft.com/fwlink/?linkid=846106)  

    Como alternativa, seleccione **Proyecto** > **Administrar paquetes NuGet** y haga clic en **Restaurar** para restaurar manualmente los paquetes que se usan en el ejemplo.  

4. Presione F5 o seleccione **Depurar** > **Iniciar depuración**.  

5. Si no ha ejecutado antes uno de los ejemplos, tendrá que especificar información para ejecutar el código; en caso contrario, escriba el número de una de las instancias que ha configurado previamente.  


   |                                 Mensaje                                  |                                                                                             Descripción                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Escriba un nombre de servidor y un puerto de Dynamics 365 [crm.dynamics.com]       | Escriba el nombre del servidor de Dynamics 365. El valor predeterminado es Dynamics 365 (en línea) (crm.dynamics.com) en Norteamérica.<br /><br /> Ejemplo: <br />crm5.dynamics.com |
   | Esta organización está aprovisionada en Microsoft Online Services (s/n) [n] |                                                 Escriba **s** si se trata de una organización aprovisionada en Microsoft Online Services. En caso contrario, escriba **n**.                                                  |
   |                          Escriba el dominio\nombre de usuario                          |                                                                                    Escriba la cuenta Microsoft.                                                                                     |
   |                             Escribir la contraseña                              |                      Escriba la contraseña. Los caracteres se mostrarán como "\*" en la ventana. La contraseña se guarda de forma segura en el Administrador de credenciales de Microsoft para su uso posterior.                       |
   |                Especifique un número de organización (1-n) [1]                 |                      En la lista de organizaciones a las que pertenece que se muestra, escriba el número correspondiente. El valor predeterminado es 1, que indica la primera organización de la lista.                       |


6. El ejemplo realizará las operaciones descritas en [Qué hace este ejemplo](#what-this-sample-does) y puede que le solicite opciones adicionales.  

7. Cuando se complete el ejemplo, presione ENTRAR para cerrar la ventana de consola.  

