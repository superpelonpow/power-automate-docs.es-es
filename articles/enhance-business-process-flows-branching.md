---
title: Mejora de los flujos de proceso de negocio con bifurcación con Power Apps | MicrosoftDocs
description: Obtenga información sobre cómo usar las ramas en un flujo de proceso de negocio
ms.custom: ''
ms.date: 06/27/2018
ms.tgt_pltfrm: ''
ms.topic: article
ms.service: flow
author: MSFTMAN
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: Deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2fedda5160291362d1ff4fcbcf91cec9f4e78713
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297899"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Tutorial: Mejora de los flujos de proceso de negocio con ramas


Los flujos de proceso de negocio le guían por las distintas fases de ventas, marketing o procesos de servicio hacia su finalización. En casos simples, un flujo de proceso de negocios lineal es una buena opción. Sin embargo, en situaciones más complejas, puede mejorar un flujo del proceso de negocio mediante bifurcación. Si tiene los permisos de creación de flujos de proceso de negocio, podrá crea el flujo de proceso de negocio con varias bifurcaciones utilizando la lógica `If-Else`. La condición de bifurcación se puede formar con varias expresiones lógicas que usan una combinación de operadores `AND` o `OR`. La selección de bifurcación se realiza automáticamente, en tiempo real, en función de reglas definidas durante la definición del proceso. Por ejemplo, en la venta de los coches, puede configurar un solo flujo de proceso de negocio, que después de una fase de calificación común se divide en dos ramas en función de una regla (prefiere el cliente un coche nuevo o uno usado, es el presupuesto del comprador inferior a $20.000 o superior, etc.) ), una bifurcación para vender coches nuevos y otra para vender coches usados. Para obtener más información acerca de los flujos de proceso de negocio, consulte [Información general sobre flujos de proceso de negocio](business-process-flows-overview.md).  
  
 El diagrama siguiente muestra un flujo de proceso de negocio con dos ramas.  
  
 ![Diagrama de flujo que muestra los pasos en el proceso de ventas de automóviles](media/example-car-sales-flow-chart.png "Diagrama de flujo en el que se muestran los pasos de un proceso de venta de coches")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>Qué debe conocer al diseñar los flujos de proceso de negocio con ramas  
 Tome nota de la siguiente información cuando diseñe el flujo de proceso de negocio con las ramas:  
  
-   Un proceso puede abarcar un máximo de 5 entidades únicas.  
  
-   Puede usar un máximo de 30 fases por proceso y un máximo de 30 pasos para fase.  
  
-   Cada rama puede tener un máximo de 5 niveles de profundidad.  
  
-   La regla de bifurcación se debe basar en los pasos de la fase que inmediatamente la precede.  
  
-   Puede combinar varias condiciones en una regla mediante el operador `AND` o el operador `OR`, pero no ambos operadores.  
  
-   Al definir un flujo de proceso, puede seleccionar de manera opcional una relación de entidad. Esta relación debe ser relación de entidad de 1:N (uno a varios).  
  
-   En el mismo registro de datos se puede ejecutar en paralelo más de un proceso activo.  
  
-   Puede reorganizar las ventanas (Fases, Pasos, Condiciones, etc.) en el flujo de proceso mediante arrastrar y colocar.  
  
-   Al combinar ramas, todas las ramas del mismo nivel deben combinarse en una sola fase. Las ramas del mismo nivel deben combinarse en una sola fase, o cada rama del mismo nivel debe finalizar el proceso. Una rama del mismo nivel no se puede combinar con otras ramas y a la vez finalizar el proceso.  
  
> [!NOTE]
> - Una entidad usada en el proceso puede ser revisitada varias veces (varios bucles de entidad cerrados).  
> - Un proceso puede volver a la fase anterior independientemente del tipo de entidad. Por ejemplo, si la fase activa es **Entregar oferta** en un registro de oferta, los usuarios del proceso pueden devolver la fase activa a la fase **Proponer** en un registro de oportunidad.  
>   
>   En otro ejemplo, suponga que un proceso está en la fase **Presentar propuesta** del flujo de proceso: **Aprobar cliente potencial** > **Identificar necesidades** > **Crear propuesta** > **Presentar propuesta** > **Cerrar**. Si la propuesta presentada al cliente requiere más investigación para identificar las necesidades del cliente, los usuarios pueden, sencillamente, seleccionar la fase **Identificar necesidades** del proceso y elegir **Activar**.  
  
<a name="CarSelling365"></a>   
## <a name="example-car-selling-process-flow-with-two-branches"></a>Ejemplo: proceso de venta de coche con dos ramas
 
Veamos el ejemplo del flujo de proceso de negocio con dos ramas, para la venta de automóviles nuevos y usados.  
  
 Primero, crearemos un nuevo proceso llamado **Proceso de venta en coche**.  
  
1.  [Abra el Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) y, después, en el panel de navegación de la izquierda, haga clic en **Procesos**.  
  
2.  Seleccione **Nuevo** para crear un nuevo proceso.  
  
3.  Especifique la **Categoría** como **Flujo de proceso de negocio** y para la **Entidad** primaria elija **Cliente potencial**.  
  
4.  Agregue la primera fase al proceso llamada **Calificar** y agregaremos pasos, **Intervalo de tiempo de compra** y **Preferencia de coche**.  
  
5.  Después de la fase común **Calificar**, dividimos el proceso en dos ramas separadas, mediante la ventana **Condición**.  
  
    1.  Configure la ventana de condición con las reglas que cumplan sus requisitos empresariales.  
  
    2.  Para agregar la primera rama de una fase, agregue una ventana Fase en la ruta “Sí” de la ventana de condición.  
  
    3.  Para agregar la segunda rama que se ejecuta cuando la condición no se cumple, agregue otra ventana Fase en la ruta ”No” de la ventana de condición.  
  
> [!TIP]
>  Puede agregar otra condición en la ruta ”No” de una ventana existente para crear bifurcaciones más complejas.  
  
 ![Imagen que muestra la fase de calificar creada](media/example-car-sales-qualify-stage.JPG "Imagen que muestra la fase de aprobación creada")  
  
 Si **Preferencia de coche** = **Nuevo**, el proceso se bifurca a la fase **Ventas de coches nuevos**; de lo contrario, salta a la fase **Ventas de coches usados**, en la segunda rama, como se muestra a continuación.  
  
 ![Imagen que muestra la nueva fase de venta de automóviles](media/example-car-sales-new-stage-1.JPG "Imagen que muestra la nueva fase de venta de automóviles")  
  
 ![Fase de ventas de automóviles de segunda mano](media/example-car-sales-pre-owned-stage.JPG "Fase de ventas de automóviles de segunda mano")  
  
 Después de completar todos los pasos de la fase **Ventas de coches nuevos** o **Ventas de coches usados**, el proceso regresa al flujo principal, con la fase **Entregar oferta**.  
  
 ![Entregar fase de oferta](media/example-car-sales-deliver-quote-stage.JPG "Entregar fase de oferta")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Evitar la divulgación de información  
 Imagine un flujo de proceso de negocio con ramas para procesar una solicitud de préstamo en un banco, como se muestra a continuación. Aparecen entre paréntesis las entidades personalizadas que se usan en las fases.  
  
 ![Gráfico de flujo que muestra los pasos en un ejemplo del proceso para evitar la revelación de información](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Gráfico de flujo que muestra los pasos en un ejemplo del proceso para evitar la revelación de información")  
  
 En este escenario, el gestor de préstamos del banco necesita tener acceso al registro Solicitud, pero no debería tener ninguna visibilidad en la investigación de la solicitud. En el primer vistazo, parece que podemos hacerlo fácilmente asignando al responsable de préstamos un rol de seguridad que especifique sin acceso a la entidad de investigación. Pero, veamos el ejemplo con mayor detalle y si esto es así realmente.  
  
 Digamos que un cliente realiza la solicitud de préstamo de más de $60.000 al banco. El responsable de préstamos revisa la solicitud en la primera fase. Si se cumple la regla de bifurcación que comprueba si el importe debido al banco superará $50,000, la siguiente fase en el proceso es investigar si la solicitud es fraudulenta. Si se determina que se trata de un caso de fraude, el proceso pasará a tomar acciones legales contra el solicitante. El gestor de préstamos no debería tener visibilidad a las dos fases de investigación, ya que no tiene acceso a la entidad de investigación.  
  
 Pero si el gestor de préstamos abre el registro Solicitud, todos podrían ver el proceso completo. El gestor de préstamos no solo podrá ver la fase de investigación del fraude, sino también identificar el resultado de la investigación, ya que podrá ver la fase Acciones legales del proceso. Además, podrá acceder a la vista previa de los pasos de las fases de investigación si selecciona la fase. Aunque no podrá ver los datos ni el estado de finalización del paso, podrá identificar las posibles acciones que se tomaron contra el remitente de la solicitud durante las fases de investigación y acciones legales.  
  
 En este flujo del proceso, el responsable de préstamos podrá ver las fases de la investigación de fraude y de acción legal, lo que constituye una divulgación de información indebida. Se recomienda prestar especial atención a información que pueda divulgarse debido a la bifurcación. En nuestro ejemplo, divida el proceso en dos procesos independientes, una para el procesamiento de solicitudes y otro para la investigación del fraude, a fin de evitar la divulgación de información. El proceso para el responsable de préstamos tendría el siguiente aspecto:  
  
 ![Gráfico de flujo que muestra pasos adicionales del proceso para evitar la revelación de información](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Diagrama de flujo en el que se muestran los pasos adicionales de un proceso para impedir la divulgación de información")  
  
 El proceso para la investigación será independiente e incluirá las fases siguientes:  
  
 ![Gráfico de flujo que muestra los pasos de un proceso de investigación para obtener información de los casos revelación](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Diagrama de flujo en el que se muestran los pasos de un proceso de investigación para casos de divulgación de información")  
  
 Tendrá que proporcionar un flujo de trabajo para sincronizar la decisión de aprobar o denegar desde el registro Investigación al registro Solicitud.  
  
### <a name="next-steps"></a>Pasos siguientes  
 [Crear un flujo de proceso de negocio](create-business-process-flow.md)   
 [Crear una lógica de negocios personalizada con procesos](guide-staff-through-common-tasks-processes.md)   
 
