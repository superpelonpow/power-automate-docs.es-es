---
title: Notas de la versión | Microsoft Docs
description: Problemas comunes y novedades de las versiones de Power Automate
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/31/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e617e6928d5295a9485c55e1efa57a945abf870f
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74374318"
---
# <a name="release-notes"></a>Notas de la versión
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="top-questions"></a>Preguntas importantes
1. Error en el flujo. ¿Cómo puedo corregirlo?
   
   1. Identifique el error Empiece por ir al icono de notificaciones en la parte superior del portal web o seleccione la pestaña **Actividad** en la aplicación móvil. Aquí debería aparecer el flujo para que pueda seleccionarlo.
   2. Ahora puede ver los detalles del flujo. Busque el paso con el icono de exclamación rojo, donde debería ver el mensaje de error del flujo.
   3. Según el mensaje de error, debe poder **editar** el flujo y corregirlo. [Más información acerca de cómo solucionar errores comunes de flujo](fix-flow-failures.md).
2. ¿Cómo se puede usar una condición o expresión avanzada?
   
   * Obtenga más información sobre la [incorporación de condiciones](add-condition.md).
   * Si desea que haya varios casos en un flujo, seleccione **Agregar condición** desde dentro de una condición ya existente.
   * Cree una expresión avanzada mediante la referencia a [una función de Logic Apps](https://docs.microsoft.com/rest/api/logic/definition-language).
3. ¿Cómo funciona la concesión de licencias con Office 365?
   
   * Los usuarios de Office 365 obtienen acceso completo a través del plan de Power Automate para Office 365. Para más información, consulte el [plan de precios de Power Automate](https://flow.microsoft.com/pricing/).
   * Si es administrador, consulte la información sobre [licencias de Power Automate](organization-q-and-a.md), incluida con Office 365.

## <a name="known-issues"></a>Problemas conocidos
1. No se admiten listas de SharePoint en Mis sitios que no sean del tipo *Lista personalizada*. Para solucionar este problema, cree una lista personalizada en un sitio de SharePoint estándar.
2. Los desencadenadores de archivo no se activarán para los archivos que se agreguen dentro de carpetas anidadas dentro de la carpeta que seleccione.

## <a name="whats-new"></a>Novedades

> [!IMPORTANT]
>
> **Anuncio de las notas de la versión**
>
> ¿Se pregunta sobre las funcionalidades próximas y recientemente lanzadas de Power Automate?
>[Vea las notas de la versión de octubre de 2018](https://docs.microsoft.com/business-applications-release-notes/October18/microsoft-flow/). Hemos tomado buena nota de todos los detalles que puede usar para la planeación. Para más información, revise [cada versión semanal](https://docs.microsoft.com/business-applications-release-notes/powerplatform/released-versions/flow) con las características y mejoras que contiene.
>
> Las notas de la versión anteriores a la versión de octubre de 2018 permanecerán aquí por si tuviera que consultarlas en otro momento, pero las nuevas versiones solo se incluirán en las ubicaciones anteriores y no en esta página.

### <a name="release-2018-09-24"></a>Versión del 24/09/2018

- **Acceso de administrador para ayuda y soporte técnico**: abra incidencias de soporte técnico para Power Automate en el centro de administración de Power Platform y proporcione detalles adicionales sobre el error de flujo de trabajo.
- **Comunidad de Flow rediseñada**: buscar lo que necesita ahora es más fácil en la comunidad de Flow.
- **Mejoras en el conector de Microsoft Teams**: desencadenadores nuevos para Microsoft Teams para que pueda ejecutar un flujo cuando hay nuevos mensajes en un canal.
- **Más acciones de SharePoint**: hay nuevas acciones para mover archivos y mucho más en el conector de SharePoint.
- **Nuevos informes de análisis de administración**: amplios análisis del entorno y del inquilino en el centro de administración de plataformas de aplicaciones empresariales.
- **Integración de Power Query**: se está construyendo una experiencia de Power Query que permitirá a los creadores dar forma a los mashups de datos desde SQL Server.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/support-tickets-teams-sharepoint/) acerca de esta versión.

### <a name="release-2018-08-31"></a>Versión del 31-08-2018

- **Probar el flujo con datos de ejemplo**: use los datos de ejemplo de conectores para probar el flujo a medida que lo compila desde el diseñador de Power Automate. Cuando pruebe el flujo con datos de ejemplo, confirme que el flujo se ejecutará según lo esperado cuando se implemente en producción.
- **Cinco nuevos conectores**: hemos agregado cinco nuevos conectores de administración: Power Apps para creadores de aplicaciones, Power Platform para administradores, Power Apps para administradores, Power Automate para administradores y Microsoft School Data Sync.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/test-data-management-connectors/) acerca de esta versión.

### <a name="release-2018-08-24"></a>Versión del 24-08-2018

- **Nuevas plantillas de sincronización de calendario**: nuevas plantillas que copian eventos entre Google Calendar y Office 365 u Outlook.com.
- **Compatibilidad con varios valores para SharePoint**: lectura y escritura para campos de varios valores en SharePoint, que son los tipos Elección, Persona o Búsqueda.
- **Enviar aprobaciones en nombre de otros usuarios de la organización**: envíe aprobaciones en nombre de otros usuarios de la organización, como por ejemplo, la persona que cargó el archivo en la lista de SharePoint, en lugar de la persona que creó el flujo.
- **Más tipos de entrada de botón**: los botones tienen dos nuevos tipos de entrada: Número y Sí/No.
- **Actualizaciones de conector**: Un nuevo conector de NetDocuments, mejoras en los conectores de Azure y mucho más.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/button-types-more/) acerca de esta versión.

### <a name="release-2018-08-02"></a>Versión del 02-08-2018

El programa de versión preliminar de Power Automate es la manera de acceder con antelación a las actualizaciones y nuevas funciones de Power Automate. Para tener acceso anticipado a las características más recientes, solo tiene que crear y, después, usar un entorno en la región de versión preliminar.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/flow-preview-program/) acerca de esta versión.

### <a name="release-2018-07-23"></a>Versión 2018-07-23

- **Compilación y ejecución de flujos desde Excel**: con el botón **Flujo** (al que se obtiene acceso desde la pestaña **Datos** de la cinta), puede crear y desencadenar automatizaciones desde Power Automate en sus datos de tabla en Excel. Automatice el procesamiento de datos o el copiado o la importación de datos.
- **Creación de un flujo de proceso de negocio**: un flujo de proceso de negocio es un nuevo tipo de flujo con estado y de interacción humana basado en Common Data Service. Utilice estos nuevos flujos para definir un conjunto de fases y pasos que sigan los usuarios. Pueden avanzar y retroceder según sea necesario.
- **Creación de un flujo para Microsoft To-Do en Outlook Web App **: si se \@menciona a alguien en Outlook Web App, verá un acceso directo para crear un flujo. Este flujo crea tareas automáticamente para la \@persona mencionada en Microsoft To-Do, basadas en el contenido del correo electrónico.
- **Compatibilidad con vistas de SharePoint**: ahora, el conector SharePoint admite la selección de una vista de SharePoint específica en desencadenadores y acciones. Esto filtra las columnas a solo los campos que se encuentran en la vista seleccionada.
- **Cuatro nuevos conectores**: Azure IoT Central agregado (una solución de software como servicio (SaaS) de IoT de alta escalabilidad), Survey 123, LMS365 y ProjectWise Design Integration.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/excel-bpf-todo-and-more/) acerca de esta versión.

### <a name="release-2018-06-29"></a>Versión 2018-06-29

- **Solicitud de flujo de aprobación creado en SharePoint**: al seleccionar un archivo o elemento en SharePoint, verá un nuevo flujo **Solicitar aprobación**. Este flujo no requiere configuración o instalación alguna y envía una solicitud de aprobación con un solo clic.
- **Dos nuevos conectores**: Cloud Connect Studio y PoliteMail agregados.
- **Mejoras en el historial y la página de creación**: estamos actualizando el historial de ejecución incluyendo tiempos de ejecución exactos y la página de creación agregando un nuevo vídeo tutorial.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/request-sign-off-four-connectors/) acerca de esta versión.

### <a name="release-2018-06-08"></a>Versión 2018-06-08

- **Cmdlets de PowerShell**: ahora, tanto los creadores de flujo como los administradores de inquilinos pueden usar PowerShell para administrar sus flujos mediante programación.
- **Mejoras en el bot de flujo de Teams**: el bot de flujo en Microsoft Teams puede ejecutar botones de flujo y describir sus flujos.
- **Tres nuevos conectores**: compatibilidad agregada con Marketo, ElasticOCR y DynamicSignal. 
- **Información de uso compartido adicional**: información adicional agregada al compartir flujos (o ejecutar flujos compartidos) para que sepa exactamente qué permisos van a recibir otras personas.
- **Direcciones URL de SharePoint de recorte automático**: al copiar y pegar una dirección URL de SharePoint en el explorador que puede incluir texto adicional más allá del sitio, este texto se quitará automáticamente para que pueda conectarse únicamente al sitio.
- **Documentación sobre solicitudes de RGPD**: hemos creado una guía y un conjunto de herramientas completos para que las organizaciones empresariales gestionen las solicitudes de derechos del interesado.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/powershell-flow-bot-marketo/) acerca de esta versión.

### <a name="release-2018-05-21"></a>Versión 21-05-2018

- **Flujos "propiedad de" listas y bibliotecas de SharePoint**: los flujos que funcionan con listas y bibliotecas de SharePoint se pueden compartir con esas listas o bibliotecas. Por tanto, en lugar de que se compartan con individuos o grupos, se comparten con todos los usuarios con acceso a la lista. A medida que se agreguen o quiten usuarios de la lista o biblioteca, su pertenencia cambia en consecuencia de forma automática.
- **Análisis de detalles de error**: un nuevo informe insertado en el que se proporciona información sobre todos los errores que se producen dentro de un flujo.
- **Compartir flujos con grupos de Office 365**: puede convertir un grupo moderno de Office 365 en el propietario de un flujo, y compartir flujos de botón con grupos de Office 365 para que cualquier integrante del grupo pueda ejecutar el flujo.
- **Mejoras del conector de SharePoint**: hay dos nuevas funciones del conector de SharePoint: desencadenar flujos cuando se eliminan archivos o elementos, y llamar a cualquier punto de conexión HTTP que sea compatible con la API REST de SharePoint.
- **Dos nuevos conectores**: se ha agregado compatibilidad para Azure Data Factory y MailParser.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/share-with-sharepoint-office-365/) acerca de esta versión.

### <a name="release-2018-05-01"></a>Versión 01-05-2018

- **Texto enriquecido en los mensajes de aprobación**: use Markdown para dar formato a los detalles de aprobación que envíe.
- **Botones con varias entradas de selección**: cree botones de flujo que usen una lista de selección múltiple para recopilar más de un valor a la vez.
- **Trabajar con flujos más amplios**: ahora, la aplicación móvil Power Automate admite la vista horizontal y el diseñador web tiene una barra de desplazamiento horizontal.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/rich-approvals-text-and-multiselect/) acerca de esta versión.

### <a name="release-2018-04-12"></a>Versión del 12/4/2018

- **Devolver datos a Power Apps a partir de un flujo**: cree flujos a los que se pueda llamar desde una aplicación compilada con Power Apps y que permitan devolver los datos a la aplicación. Use el diseñador de flujos visual, que permite arrastrar y colocar, para crear la lógica que necesite para sus aplicaciones. 
- **Agregar varios registros a entradas de matriz**: se ha agregado un creador de listas en Power Automate que se puede usar para agregar varios datos adjuntos a un correo electrónico, por ejemplo.
- **Probar flujos con datos ejecutados anteriormente**: se ha agregado un nuevo botón Probar flujo en el diseñador. Con él podrá probar el flujo con datos desencadenadores a partir de ejecuciones de flujos anteriores.
- **Nuevos campos workflow()**: ahora puede acceder al nombre del entorno y al nombre para mostrar del flujo con la expresión workflow().

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/return-data-to-powerapps/) acerca de esta versión.

### <a name="release-2018-04-04"></a>Versión del 4/4/2018

- **Aprobaciones de Common Data Service**: las aprobaciones modernas se crean con la versión más reciente de Common Data Service. Esto significa que puede crear flujos que lean el estado de las aprobaciones que envíe o reciba con el conector de Common Data Service.
- **Buscar errores en aplicar a ambos**: vaya directamente a los errores en bucles en la vista de ejecución de flujo, incluso aunque haya cientos de elementos en el bucle.
- **Volver a asignar aprobaciones**: puede asignar cualquier aprobación que reciba de otra persona para delegar en ella la aprobación. 
- **Listas de salas**: con el conector de Office 365 Outlook se han agregado acciones para obtener datos de salas de la organización.
- **Ver detalles de los botones de flujos**: al ejecutar un flujo compartido con usted, ahora puede ver todas las acciones que usa el flujo.
- **Región de Reino Unido**: ahora puede crear entornos para almacenar datos en el Reino Unido.
- **Dos nuevos conectores**: se ha agregado compatibilidad para AtBot Admin y Marketing Content Hub.
- **Nueva página de aterrizaje de documentación**: se ha actualizado la página de aterrizaje de documentación. Ahora el contenido está agrupado según el nivel de experiencia: principiante, usuario intermedio o experto. 

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/approvals-in-cds-and-seven-updates/) acerca de esta versión.

### <a name="release-2018-03-13"></a>Versión del 13/3/2018

- **Historial de aprobación**: vea todas las solicitudes de aprobación que ha enviado, incluidas las respuestas y los comentarios enviados, y la hora exacta en la que se hicieron.
- **Cuatro nuevos conectores**: se ha agregado Excel Online (Business), Excel Online (OneDrive), Azure SQL Data Warehouse y Pitney Bowes Tax Calculator.
- **Información en pantalla de contenido dinámico**: mantenga el puntero sobre el contenido dinámico para ver de dónde procede, dentro de las acciones, y obtener una vista previa de las expresiones sin abrir el editor de expresiones.
- **Control de simultaneidad**: habilite el control de simultaneidad para hacer que un flujo concreto no se ejecute varias veces al mismo tiempo.
- **Reintento exponencial**: se trata de un nuevo tipo de directiva de reintentos que separa los reintentos de forma exponencial en el tiempo.
- **Conformidad de accesibilidad**: se han publicado nuevos documentos de conformidad en los que se describe el cumplimiento de Power Automate con los estándares de accesibilidad.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/approval-history-accessibility/) acerca de esta versión.

### <a name="release-2018-02-09"></a>Versión 2018-02-09

- **Alta disponibilidad de la puerta de enlace**: cree clústeres de puertas de enlaces de datos locales para mantener las conexiones activas cuando una máquina deje de funcionar.
- **Opción Aplicar a cada uno mejorada**: con el plan de flujo 1 o el plan de flujo 2, se procesan hasta 100 000 elementos en una sola ejecución y 50 acciones en paralelo en bucles de Aplicar a cada uno. 

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/) acerca de esta versión.

### <a name="release-2018-01-29"></a>Versión 2018-01-29

- **Flujo dentro de Microsoft Teams**: desde Teams, puede crear y administrar flujos, revisar las aprobaciones recibidas y enviadas e iniciar flujos directamente desde la aplicación de escritorio de Teams o en teams.microsoft.com ([obtenga aquí más información](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/)).
- **Notificaciones de edición compartidas**: cada vez que un colega cambie un flujo que sea suyo, recibirá un correo electrónico de notificación en el que se le informa de quién cambio ese flujo.
- **Nuevas expresiones**: se han agregado dos nuevos conjuntos de expresiones: uno para analizar direcciones URL y otro para trabajar con objetos JSON.
- **Tres nuevos conectores**: esta semana hay dos nuevos conectores de Plumsail, Plumsail SP y Plumsail Forms, y un nuevo conector para kintone.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/shared-notifications-and-expressions/) acerca de esta versión.

### <a name="release-2018-01-17"></a>Versión 2018-01-17

- **Información de perfil de Office 365**: hemos agregado nuevas acciones al conector de usuarios de Office 365 que funcionan con perfiles y fotos de los usuarios.
- **Anexar a variables de cadena**: puede agregar a cadenas dentro de bucles para crear tablas u otras listas.
- **Conector de Infobip**: Infobip es un servicio que permite la comunicación de nivel empresarial, incluidas las llamadas de voz y la activación de SMS de entrada.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/o365-profile-infobip/) acerca de esta versión.

### <a name="release-2017-12-20"></a>Versión 2017-12-20

Los análisis de Power Automate ya están disponibles en todas las regiones, lo que significa que puede obtener más información sobre el estado de los flujos que se están ejecutando en su entorno.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/) acerca de esta versión.


### <a name="release-2017-12-14"></a>Versión 2017-12-14

- **Mejoras en el conector de Outlook**: puede guardar un correo electrónico como un archivo ".eml", responder a invitaciones de calendario automáticamente y desencadenar flujos cuando se le menciona en un hilo de correo.
- **Mejoras de las conexiones**: Power Automate le recuerda las conexiones que usó recientemente y le muestra todos los conectores recién agregados.
- **Cinco nuevos conectores**: se han agregado Azure Container Instances, Azure Kusto, Metatask, Microsoft To-Do y Plumsail Documents.
- **Mejoras de HTTP**: la acción de HTTP ahora admite la codificación fragmentada.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/outlook-connector-more/) acerca de esta versión.

### <a name="release-2017-12-05"></a>Versión 2017-12-05

El panel de inicio de Power Automate ya está disponible en todas las regiones. Este panel le permite agregar valores a un flujo cuando se ejecuta dentro de la biblioteca de documentos o lista de SharePoint.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/) acerca de esta versión.


### <a name="release-2017-11-28"></a>Versión 2017-11-28

- **Metadatos administrados**: lee datos de las columnas de SharePoint que usan el tipo de metadatos administrados (también conocidos como taxonomías) y también escribe datos en ellas.
- **Anexar a matrices**: permite agregar elementos al final de matrices mediante una nueva acción Anexar a la variable de matriz.
- **Tago**: un nuevo conector a Tago, que proporciona una conexión sencilla de dispositivos electrónicos con datos externos para impulsar una toma de decisiones más inteligentes mediante el análisis contextual.
- **iPhone X**: una nueva versión de la aplicación Power Automate que usa la pantalla completa en el iPhone X, y que incluye una mejora de la velocidad para la carga de imágenes.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/managed-metadata-tago/) acerca de esta versión.

### <a name="release-2017-11-09"></a>Versión 2017-11-09

- **Integración con OneDrive para la Empresa**: ahora ya hay [un botón de Flow dentro de OneDrive para la Empresa](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/) con el que puede crear o desencadenar flujos en los archivos o carpetas seleccionados.
- **Desencadenadores de programación**: permite iniciar flujos cuando se crea una nueva tarea, cuando se le asigna una tarea o cuando se completa una.
- **Datos adjuntos de SharePoint**: trabaje con datos adjuntos en los elementos de lista de SharePoint: enumere, descargue, agregue o elimine datos adjuntos.
- **Conector de administración de Flow**: cree flujos que automaticen la administración de otros flujos del entorno (por ejemplo, agregue permisos a los flujos automáticamente).
- **Cuatro nuevos conectores**: se ha incorporado Azure Custom Vision Service, D&B Optimizer, Enadoc y Derdak SIGNL4. 
- **Más acciones de conector**: ejecute consultas SQL, obtenga desencadenadores de correo electrónico más rápidos, use cualquier método con HTTP con Azure AD, etc.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/) acerca de esta versión.

### <a name="release-2017-11-02"></a>Versión 2017-11-02

- **Registro de auditoría**: los eventos de auditoría de Power Automate están ya disponibles en el Centro de seguridad y cumplimiento de Office 365 para todos los inquilinos.
- **Correcciones de widgets de Flow**: se ha corregido un problema en la aplicación móvil de Flow que hacía que los botones no se cargaran en el widget.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/security-and-compliance-center/) acerca de esta versión.

### <a name="release-2017-10-19"></a>Versión 2017-10-19

- **Acciones "aplicar a cada uno" anidadas**: puede agregar acciones "aplicar a cada uno", filtrarlas y seleccionarlas en otras acciones de contenedor "aplicar a cada uno".
- **Acciones de fecha y hora**: nuevas acciones de obtención de horas locales, y de suma, resta o aplicación de formato a las horas.
- **Cuatro nuevos conectores**: se ha incorporado Content Moderator, Docparser, Microsoft Kaizala y Pitney Bowes Data Validation.
- **Se ha mejorado la experiencia de conexión**: se envían notificaciones al portal de Power Automate cuando se rompe una conexión y se facilita una información más completa sobre las conexiones.
- **Colección portátil**: una nueva colección de plantillas para [trabajadores con gran movilidad](https://flow.microsoft.com/collections/onthego/).
- **Entradas de botones para direcciones de correo electrónico**: recopile direcciones de correo de electrónico de los usuarios cuando estos ejecuten los botones.
- **Entradas de botones para archivos**: obtenga archivos cargados como, por ejemplo, fotos, de los usuarios cuando estos ejecuten los botones.
- **Primera ejecución e inicio de sesión automático**: se han mejorado las experiencias de primera ejecución en la aplicación móvil, entre las que cabe destacar el inicio de sesión automático.
- **Desencadenadores de Microsoft Forms más rápidos**: Forms desencadena flujos mucho más rápido que antes (anteriormente era una vez cada hora).
- **Entradas de botones entre sesiones**: los botones desencadenados en el teléfono móvil le recordarán las entradas previas.
- **Fuente de actividades para dispositivos móviles**: se ha mejorado la fuente de actividades para que incluya resúmenes más detallados de ejecución e información sobre solución de problemas.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/nested-apply-to-each/) acerca de esta versión.

### <a name="release-2017-10-03"></a>Versión 2017-10-03

- **Debe ser aprobado por todos**: requiere que se envíe una solicitud de aprobación a más de una persona para que todo aquel que la reciba la apruebe.
- **Nuevas acciones de OneDrive para la Empresa**: como generar archivos PDF para los archivos almacenados en OneDrive para la Empresa y cuatro nuevas acciones más.
- **Conector Apache Impala**: Apache Impala (incubating) es la base de datos analítica, nativa y de código abierto para Apache Hadoop.
- **Incorporación de descripciones de flujos**: proporcione descripciones para sus flujos para que cuando los comparta, sus compañeros puedan ver un resumen de lo que hace el flujo.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/) acerca de esta versión.

### <a name="release-2017-09-25---q3-update-for-power-automate"></a>Versión de 2017-09-25 - Actualización del tercer trimestre para Power Automate

- **Integración de SharePoint más profunda en primera versión**: hay un nuevo envío "integrado" para flujos de revisión y un panel de Flow para recopilar entradas cuando se ejecuta un flujo para los inquilinos de la primera versión.
- **Aplicaciones de Dynamics 365**: Flow ahora está integrado en la interfaz de usuario de aplicaciones de Dynamics 365 como Dynamics 365 for Sales y Dynamics 365 Customer Service.
- **Centro de confianza de Microsoft**: Power Automate aparece en el Centro de confianza de Microsoft con las certificaciones HIPAA, ISO y SOC.
- **Análisis de uso**: cada flujo tiene un panel de Power BI insertado con un análisis de uso básico.
- **Registro de auditoría en la primera versión**: todos los eventos de administración de flujos se registran en el Centro de seguridad y cumplimiento de Office 365 para los inquilinos de la primera versión.
- **Seis nuevos conectores**: se ha incorporado LinkedIn, Office 365 Groups, Skype for Business, Adobe Sign, Bizzy y Azure Log Analytics Data Collection.
- **Desencadenadores SQL**: permiten ejecutar flujos cuando se agrega una nueva fila o cuando se actualiza una fila en una tabla SQL.
- **Conectores personalizados locales**: los conectores personalizados pueden usar ya la puerta de datos de enlace local para conectarse a puntos de conexión internos de la red.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/q3-2017-update/) acerca de esta versión.

### <a name="release-2017-09-21"></a>Versión 2017-09-21

- **Descarga del historial de flujos**: ya se puede descargar el historial de ejecución de un flujo como un archivo CSV para abrirlo en Excel.
- **Opciones avanzadas de periodicidad**: cree programaciones periódicas para desencadenar los flujos. Por ejemplo, para que solo se desencadenen en los días laborables.
- **IntelliSense**: al escribir expresiones, IntelliSense proporcionará sugerencias para los parámetros.
- **Cuatro nuevos conectores**: se han incorporado conectores para los servicios HTTP de Azure AD, Amazon Redshift, Azure Event Grid Publish y FlowForma.
- **Uso compartido de vínculos**: una nueva acción para generar vínculos que se pueden compartir para archivos de OneDrive o Azure Storage Blobs.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/download-history-recurrence/) acerca de esta versión.


### <a name="release-2017-08-25"></a>Versión 2017-08-25
* **Propiedades de documentos y otras cuestiones relativas a SharePoint** - [lea y establezca las propiedades de la biblioteca de documentos de SharePoint](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/)y use campos adicionales, como vínculos, en el elemento de SharePoint.
* **Colecciones de Flow**: las colecciones de Flow son un conjunto de colecciones de plantillas organizado por rol o por vertical.
* **Volver a compartir botones**: si comparte botones con sus compañeros de trabajo, estos también pueden volver a compartirlos con otras personas.
* **Recopilar listas de botones**: defina las listas desplegables de opciones que pueden elegir los usuarios al pulsar el botón.
* **Siete conectores nuevos**: AWeber, Azure Log Analytics, Azure Tables, DocFusion365, Azure Event Grid, Azure Event Hubs y StaffHub. 
* **Mejoras en Slack y MySQL**: cree o combine de canales en Slack y puede escribir en bases de datos MySQL.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/button-updates-seven-connectors/) acerca de esta versión.

### <a name="release-2017-08-02"></a>Versión 2017-08-02
* **Campos Write to Person, Choice and Lookup** (Escribir a persona, Opción y Búsqueda): las acciones Crear elemento y Actualizar elemento de SharePoint [ahora admiten la capacidad de](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) configurar los campos Persona, Elección y Búsqueda.
* **Mayor configuración de las acciones**: ahora hay más control sobre la ejecución de desencadenadores y acciones, lo que incluye la configuración de las directivas de reintento y de la paginación.
* **Cuatro nuevos conectores**: ahora se pueden usar Azure File Storage, Elastic Forms, Plivo y Video Indexer.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/four-connector-action-settings/) acerca de esta versión.

### <a name="release-2017-07-27---q2-update-for-power-automate"></a>Versión de 2017-07-27: actualización del segundo trimestre de Power Automate
* **Importar y exportar**: importe y exporte soluciones de flujo entre entornos o de la fase de prueba a la de producción. 
* **Usar expresiones en acciones**: escriba expresiones en cualquier acción y obtenga ayuda en línea sobre cómo utilizarlas.
* **Crecer hasta Azure Logic Apps**: guarde los flujos como un recurso de Azure Logic Apps que se pueda implementar a través de Visual Studio o de Azure Portal.
* **Visibilidad de la administración**: descargue el uso de Power Automate en su inquilino para saber exactamente dónde y cómo se usan los flujos.
* **Flujos en Dynamics 365**: use flujos en de Dynamics 365 for Operations & Financials, Business Edition.
* **Buscar escenarios más fácilmente**: examine todo lo que el conector pueda hacer y, después, utilice cualquier desencadenador como punto de partida para generar flujos.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/q2-2017-update/) acerca de esta versión.

### <a name="release-2017-07-13"></a>Versión 2017-07-13
* **Mejora en la publicación de plantillas**: cualquier flujo que cree, junto con sus categorías, se puede publicar en la galería pública.
* **Obtener los eventos de Outlook Calendar**: una nueva acción que devuelve todos los eventos entre dos horas del calendario.
* **Nueva funcionalidad para dispositivos móviles**: ejecute flujos a petición y vuelva a enviar las ejecuciones con errores en la aplicación móvil.
* **Listas desplegables dinámicas en conectores personalizados**: cree listas desplegables dinámicas y desencadenadores de sondeo, y probar sus conectores personalizados.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/publishing-and-custom-connectors/) acerca de esta versión.

### <a name="release-2017-06-28"></a>Versión 2017-06-28
* **Actualización de la configuración de idioma**: puede personalizar el idioma y la región que usa Power Automate en el menú de configuración.
* **Cinco nuevos conectores**: compatibilidad agregada con Adobe Creative Cloud, Bing Maps, Bing Search, JotForm y Freshservice.
* **Configuración de los tiempos de espera**: cambie las acciones de larga duración, como aprobaciones, ejecútelas antes de que se agote el "tiempo de espera" y el flujo continuará.
* **Incluir comentarios en Outlook en las aprobaciones**: cuando reciba una solicitud de aprobación, puede incluir comentarios sin salir de Outlook.
* **Identidad cromática para conectores personalizados**: ahora puede especificar un color para los conectores personalizados que se usará para los fondos.
* **Opción Guardar como para los flujos de equipo**: haga copias de los flujos, incluidos los flujos de equipo
* **Eliminación de la información de flujo**: al eliminar un flujo, se le mostrará la lista de todas las ejecuciones pendientes de dicho flujo.
* **Filtrado en la página de conectores**: busque los conectores que desee en la página de conectores y filtre por tipo de conector.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/language-settings-3-connectors/) acerca de esta versión.

### <a name="release-2017-06-19"></a>Versión 2017-06-19
Ahora puede ver el estado de todas las solicitudes de aprobación pendientes que ha enviado. Además, puede examinar y actuar directamente en todas las aprobaciones pendientes desde el dispositivo móvil.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/sent-requests-flow-mobile/) acerca de esta versión.

### <a name="release-2017-06-15"></a>Versión 2017-06-15
* **Conversión de contenido**: un nuevo conector que puede convertir contenido HTML en texto sin formato, útil para manejar correos electrónicos con formato HTML.
* **Tres nuevos conectores de base de datos**: agregue compatibilidad de solo lectura para MySQL, PostgreSQL y Teradata. Estos conectores se conectan a través de la puerta de enlace de datos local.
* **Otros tres conectores**: conéctese a Azure Application Insights, Calendly y Teamwork Projects.
* **Mejor visualización del control de errores**: los pasos que se ejecutan después de los errores se muestran ahora con flechas con puntos rojos para que pueda identificarlos fácilmente.
* **Ejecución del panel de detalles**: cuando se produce un error en un flujo, ahora hay un nuevo panel derecho que contiene algunos pasos útiles para saber cómo corregir el flujo.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/seven-connectors-and-html/) acerca de esta versión.

### <a name="release-2017-06-04"></a>Versión 2017-06-04
* **Disponibilidad general para Windows Phone** - [La aplicación móvil de Power Automate es ahora de disponibilidad general para Windows Phone](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **Correos electrónicos al producirse errores de flujo**: reciba las notificaciones por correo electrónico si se produce un error en algún flujo. Estos mensajes de error se enviarán solo una vez por semana y el usuario puede activarlos o desactivarlos.
* **Acción de selección para tablas**: use la nueva acción de selección para cambiar el conjunto de columnas que se incluirán en las tablas.
* **Conector de Microsoft Forms**: Microsoft Forms es un nuevo elemento de Office 365 Educación que permite a los profesores y alumnos crear cuestionarios personalizados de forma rápida y sencilla, así como encuestas, registros y mucho más.
* **Plan de Office 365 Enterprise K1**: Power Apps y Power Automate ahora se incluyen con el plan de Office 365 Enterprise K1 con ciertas cuotas.
* **Encabezados HTTP más sencillos**: al igual que la acción de selección, puede especificar un nombre y un valor de encabezado rellenando simplemente los cuadros de texto en la acción.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/) acerca de esta versión.

### <a name="release-2017-05-23"></a>Versión 2017-05-23
* **Conector de Microsoft Teams** - [Microsoft Teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) es un área de trabajo de Office 365 basado en chat que reúne a personas, conversaciones y contenido, junto con las herramientas que necesitan los equipos, para que puedan colaborar fácilmente para lograr objetivos superiores.
* **Widgets en iOS y Android**: los widgets de Power Automate son accesos directos de botón que proporcionan una manera más rápida y sencilla de desencadenar los botones desde la pantalla principal.
* **Crear pasos de "control de errores"**: defina los pasos que se van a ejecutar después de que se produzca un error en una acción. Por ejemplo, obtener inmediatamente una notificación si un flujo no crea un registro en Dynamics 365.
* **Variables enteras y flotantes**: inicialice los contadores e increméntelos o redúzcalos en una ejecución de flujo para contar el número de veces que se ejecuta un conjunto de lógica determinado.
* **Página de detalles de flujo**: al seleccionar un flujo en la lista **Mis flujos**, verá una página con detalles de dicho flujo, como quién tiene acceso y el historial de ejecución.
* **Cuotas de ejecución de flujo para administradores**: ahora, los administradores pueden supervisar el uso de las ejecuciones de flujos en una organización con respecto a la cuota habitual de ejecuciones de una empresa y obtener un desglose de la cuota para saber qué licencias contribuyen a ella.
* **Mejoras en el desencadenador de solicitud HTTP**: use distintos métodos de HTTP y agregue segmentos de ruta al desencadenador de solicitud.
* **Dos conectores asociados**: ahora, Power Automate puede conectarse a Parserr, un servicio de análisis de correo electrónico, y Cognito Forms, un servicio de formularios en línea.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/error-handling/) acerca de esta versión.

### <a name="release-2017-05-12"></a>Versión 2017-05-12
* **Integración con bibliotecas de documentos de SharePoint**: puede seleccionar cualquier archivo en una biblioteca de documentos y comenzar un flujo, por ejemplo, para enviarlo a su administrador para su aprobación, [y mucho más](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/).
* **Conector de Microsoft Planner**: Microsoft Planner le permite reunir fácilmente los equipos, las tareas, los documentos y las conversaciones para obtener unos mejores resultados.
* **Vista de administrador de las licencias**: los administradores pueden ver todas las licencias de Power Automate y Power Apps (tanto de prueba como pagadas) en el Centro de administración de Power Apps.
* **Plan de la Comunidad de PowerApps**: el plan de la Comunidad de PowerApps es un plan gratis para que usuarios puedan explorar, aprender y desarrollar habilidades para Power Apps, Power Automate y Common Data Service.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/planner-community-and-licenses/) acerca de esta versión.

### <a name="release-2017-05-09"></a>Versión 2017-05-09
* **Conector de Azure AD**: hay un nuevo conector para llevar a cabo acciones de administrador desde Power Automate, incluida la creación de usuarios o su incorporación a grupos.
* **Mejoras de Office 365 Outlook**: los flujos se pueden desencadenar ya con los buzones de correo compartidos y el envío de un correo electrónico a un buzón compartido. También pueden establecer o leer las respuestas automáticas.
* **Disponible en Canadá**: ya puede crear los flujos en Canadá.
* **Creación de API y webhooks personalizados**: los desarrolladores de conectores personalizados pueden agregar desencadenadores a sus API personalizadas con webhooks.
* **Administración de los propietarios del flujo en el centro de administración**: los administradores de entornos pueden administrar propietarios de flujos en el centro de administración de Power Automate.
* **Referencia a documentación sobre conectores**: ahora ya disponemos de una [completa referencia sobre conectores en docs.microsoft.com](https://docs.microsoft.com/Connectors/).
* **Dos servicios de asociados**: se publicaron dos nuevos servicios de asociados: Nexmo y Paylocity.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/canada-mailboxes-aad) acerca de esta versión.

### <a name="release-2017-04-27"></a>Versión 2017-04-27
* **Creación de flujos con pasos paralelos**: cree flujos con la ejecución en paralelo, lo que significa que dos o más pasos se pueden ejecutar al mismo tiempo.
* **Cinco nuevos servicios admitidos**: Approvals, Benchmark Email, Capsule CRM, LiveChat y Outlook Customer Manager.
* **Supervisión de reintentos para acciones**: Power Automate volverá a realizar un reintento cuando haya errores con los servicios. Ahora puede consultar cuántos reintentos automáticos se han producido y los detalles de lo que ha ocurrido.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/parallel-actions/) acerca de esta versión.

### <a name="release-2017-04-17---q1-update-for-power-automate"></a>Versión de 2017-04-17: actualización del primer trimestre de Power Automate
* **Experiencias modernas de aprobación**: cree flujos de trabajo donde los aprobadores pueden aprobar forma segura desde la misma aplicación móvil de Power Automate o en el centro de aprobaciones unificadas del sitio web de Power Automate.
* **Disponibilidad general de flujos de equipo**: varias personas pueden poseer y administrar un flujo junto con flujos de equipo, que ahora están disponibles con carácter general.
* **Creación de conectores para Power Automate**: cualquier persona puede enviar su propio conector de Power Automate gratis para que lo use todo el mundo.
* **Un diseñador "a medida"**: en algunas plantillas, la nueva versión del diseñador presenta solo aquellos campos que son necesarios para crear un flujo, lo que simplifica la experiencia.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/q1-2017-update/) acerca de esta versión.

### <a name="release-2017-04-11"></a>Versión 2017-04-11
* **Nuevas acciones para compilar tablas y listas**: acciones de creación de nuevas tablas HTML, creación de tablas CSV y combinación que pueden procesar listas de elementos (en lugar del anterior método que se aplicaba de forma individual).
* **Inserción de pasos en cualquier lugar**: ahora puede insertar un nuevo paso en cualquier parte del flujo de trabajo sin necesidad de arrastrar y colocar.
* **Cuatro nuevos servicios**: Flow es ahora compatible con 10 to 8 Scheduling, Act!, Inoreader y Computer Vision API. Con Computer Vision API puede procesar imágenes para obtener el contenido de texto (proceso conocido como OCR) o etiquetar automáticamente las imágenes en función de su contenido.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/) acerca de esta versión.

### <a name="release-2017-04-03"></a>Versión 2017-04-03
* **Versión Beta para Windows Phone**: la versión beta de la aplicación para Windows Phone está disponible para obtener una versión preliminar de la aplicación en su Windows Phone. [Más información](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/)
* **Muhimbi PDF**: ahora puede convertir archivos de Microsoft Word en PDF, agregar marcas de agua, combinar documentos y mucho más con Muhimbi PDF. [Más información](https://flow.microsoft.com/blog/convert-files-using-muhimbi/)
* **Desencadenar flujos desde botones físicos**: anunciamos asociaciones con dos de los principales productos en el espacio de los botones físicos: Flic, de Shortcut Labs, y Bttn, de The Button Corporation. [Más información](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>Versión 2017-03-22
* **Copia de su flujo**: ahora puede realizar una copia de su flujo para trabajar en versiones de borrador o duplicar un flujo que creó anteriormente.
* **Dos nuevos servicios**: se agrega compatibilidad con Toodledo, que permite administrar su lista de tareas mediante la creación y actualización de las tareas, y con Zendesk, que proporciona un servicio al cliente y admite una plataforma de tickets.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/make-a-copy/) acerca de esta versión.

### <a name="release-2017-03-15"></a>Versión 2017-03-15
* **Compartir botones con compañeros de trabajo**: ahora puede compartir los botones de flujo con otras personas, lo que ayuda a cualquier usuario corporativo a realizar tareas rápidas.
* **Desencadenar botones desde la pantalla principal**: los accesos directos a los botones de flujo en las pantallas principal y de bloqueo de los dispositivos móviles hacen que sea más rápido que nunca desencadenar un flujo.
* **Flujos de equipos en la aplicación Power Automate**: ahora puede ver los flujos de otros propietarios de la aplicación Power Automate para iOS o Android.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/button-sharing/) acerca de esta versión.

### <a name="release-2017-03-10"></a>Versión 2017-03-10
* **Mejor experiencia de conector personalizado**: ahora puede usar una colección Postman para crear un conector personalizado y editar, agregar y probar acciones.
* **Dos nuevos servicios**: se ha agregado compatibilidad con Power Apps Notifications y PivotalTracker.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/new-updates-custom-api/) acerca de esta versión.

### <a name="release-2017-02-27"></a>Versión 2017-02-27
* **Desencadenar los botones de flujo**: ahora puede desencadenar los botones de flujo directamente desde Power Automate. En la lista de flujos, simplemente seleccione el menú "..." y elija el comando Ejecutar ahora.
* **Cinco nuevos servicios**: se ha agregado compatibilidad con Oracle Database, Intercom, FreshBooks, LeanKit y WebMerge.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/trigger-flow-buttons-web/) acerca de esta versión.

### <a name="release-2017-02-21"></a>Versión 2017-02-21
* **Ver flujos de entorno**: los administradores de entorno ahora pueden ver la lista completa de todos los flujos dentro de un determinado entorno, así como habilitar, deshabilitar o eliminar flujos.
* **Dos nuevos servicios**: se ha agregado compatibilidad con Azure Automation y Basecamp 2.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) acerca de esta versión.

### <a name="release-2017-02-16"></a>Versión 2017-02-16
* **Cinco nuevos servicios**: se ha agregado compatibilidad con Azure Data Lake, Bitbucket (un servicio de hospedaje basado en web para proyectos que usan el control de revisión de GIT), Eventbrite, Infusionsoft y Pipedrive.
* **Autenticación HTTP personalizada**: en el diseñador de flujos ahora es posible usar la autenticación con puntos de conexión HTTP personalizados.
* **Analizar mensajes JSON**: puede analizar datos JSON procedentes del desencadenador Solicitud HTTP o devueltos desde la acción HTTP.
* **Filtrado de la ejecución de flujo**: filtrado mejorado para las ejecuciones de flujo, con opciones más específicas, incluida la visualización de los flujos en ejecución o las ejecuciones canceladas.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) acerca de esta versión.

### <a name="release-2017-02-06"></a>Versión 06-02-2017
* **Flujos de equipo**: los flujos de equipo permiten que varias personas posean y administren un flujo de forma conjunta y que, aunque cualquiera de ellas abandone la organización, los flujos creados se sigan ejecutando.
* **Uso compartido de conectores personalizados**: los conectores personalizados, como los flujos de equipo, se pueden compartir y administrar colectivamente dentro de una organización.
* **Compatibilidad con Gmail y LUIS**: conéctese a Gmail y a Language Understanding Intelligent Service de Azure Cognitive Services.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/team-flows/) acerca de esta versión.

### <a name="release-2017-01-30"></a>Versión 30-01-2017
* **Entradas de los botones de flujos**: los botones de flujos pueden recibir acciones de usuario en tiempo de ejecución, por lo que los creadores de flujos pueden definir la información que se pasa al pulsar el botón.
* **Tareas de Outlook y HelloSign**: el servicio Tareas de Outlook le permite administrar tareas, mientras que HelloSign permite proteger las firmas electrónicas.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/button-user-inputs/) acerca de esta versión.

### <a name="release-2017-01-23"></a>Versión 2017-01-23
* **Buscar por servicio**: examine por servicio cuando agregue un desencadenador o una acción para ver todas las acciones de cada servicio.
* **Cambio de mayúsculas y minúsculas**: agregue bloques de cambios para tener varias ramas de lógica en paralelo.
* **Más acciones de correo electrónico**: nueva funcionalidad de los servicios Office 365 Outlook y Outlook.com para trabajar con mensajes de correo marcados.
* **Cinco nuevos servicios**: Conexión a sistemas de archivos locales o de red, el servicio de pago Stripe, IBM Informix, IBM DB2 y UserVoice.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/search-by-service/) acerca de esta versión.

### <a name="release-2017-01-14"></a>Versión 2017-01-14
* **Volver a enviar ejecuciones**: si tiene un flujo con un error y desea intentar corregirlo y ejecutarlo de nuevo, se puede volver a enviar esa ejecución.
* **Cancelación de ejecuciones**: cuando un flujo se queda bloqueado ya puede cancelar explícitamente la ejecución.
* **Dos nuevos servicios**: incorporación de compatibilidad con GoToTraining y GoToWebinar.
* **Conexión por teléfono móvil**: ya puede compartir plantillas directamente desde la aplicación móvil y se ha agregado un vínculo de descarga rápida de las aplicaciones de la parte superior del sitio web.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/managing-runs/) acerca de esta versión.

### <a name="release-2016-12-29"></a>Versión 2016-12-29
Power Automate ahora admite DocuSign, para controlar firmas electrónicas y la administración de transacciones digitales, SurveyMonkey, para encuestas basadas en web, y la aplicación para tomar notas OneNote (solo cuentas empresariales).

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/final-2016-services/) acerca de esta versión.

### <a name="release-2016-12-20"></a>Versión 2016-12-20
* **Ejecutar ahora**: se puede enviar rápidamente un desencadenador recurrente
a petición (por ejemplo, si tiene un informe programado cada día, pero necesita que el informe se ejecute también **ahora**).
* **Seis nuevos servicios**: genere flujos que se conectan a MSN El Tiempo, Medium, Contactos de Google, Buffer, Harvest y TypeForm.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/run-now-and-six-more-services/) acerca de esta versión.

### <a name="release-2016-12-14"></a>Versión 2016-12-14
Ahora puede sacar provecho de información valiosa al desencadenar un flujo de botón, como desde dónde se desencadenó el botón, quién lo hizo, a qué hora, etc.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/button-trigger-tokens/) acerca de esta versión.

### <a name="release-2016-12-06"></a>Versión 2016-12-06
* **Introducción a aprendizaje guiado**: empiece a trabajar con un conjunto de cursos en secuencia que emparejan vídeos y documentación para ayudarle a comprender las numerosas y eficaces funcionalidades de Power Automate.
* **Dos nuevos servicios**: ahora los flujos pueden usar Freshdesk, una solución de soporte al cliente y GoToMeeting, una herramienta de reuniones en línea.
* **Compatibilidad con HTTP Webhook**: ahora un flujo puede ser un punto de conexión de webhooks que se registrará y anulará su registro automáticamente.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/guided-learning-and-two-services/) acerca de esta versión.

### <a name="release-2016-11-23"></a>Versión 2016-11-23
* **Compatibilidad con alertas de Power BI**: convierte la información en acción gracias a la activación de flujos desde alertas de datos de Power BI.
* **Mejoras de aplicaciones móviles**: se ha agregado la capacidad de crear flujos desde cero, además de la experiencia ya existente de creación mediante plantillas. También se ha mejorado el rendimiento al ver las ejecuciones de los flujos.
* **Ocho nuevos servicios**: ahora puede conectarse a Azure Resource Manager, las colas de Azure, Chatter, Disqus, Azure Cosmos DB, Face API de Cognitive Services, HipChat y Wordpress.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/) acerca de esta versión.

### <a name="release-2016-11-15"></a>Versión 2016-11-15
* **Programa de asociados de Power Automate**: Power Automate tiene ahora un programa de asociados certificados para realizar conexiones y aprovechar las ventajas de la experiencia y los talentos de diferentes empresas con Power Automate en todo el mundo.
* **Seis nuevos servicios**: también vamos a lanzar seis servicios esta semana: Asana, Campfire, EasyRedmine, JIRA, Redmine y Vimeo.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/partner-program-six-new-services/) acerca de esta versión.

### <a name="release-2016-10-31---general-availability"></a>Versión 2016-10-31: disponibilidad general
* **Precios y licencias**: ya está disponible tanto de forma gratuita como de pago, además de estar incluido en Office 365 y Dynamics 365.
* **Centro de administración de Power Automate**: preparado para la empresa con el nuevo Centro de administración. En el Centro de administración se pueden administrar los entornos de la organización.
* **Directivas de prevención de pérdida de datos**: los administradores pueden crear directivas de prevención de pérdida de datos para controlar el flujo de datos entre servicios.
* **Disponibilidad en Android**: la aplicación Power Automate para dispositivos móviles ya está disponible tanto para iOS como para Android. La aplicación permite recibir notificaciones, supervisar la actividad e iniciar flujos pulsando un botón.
* **Nuevas experiencias de diseño**: ya se puede buscar en el contenido dinámico que se pasa paso a paso, lo que agiliza mucho la referencia a los datos que se desee.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/announcing-ga/) acerca de esta versión.

### <a name="release-2016-10-26"></a>Versión 2016-10-26
* **Flujos de botón**: hay innumerables operaciones que nos gustaría poder desencadenar en cualquier momento y lugar. Ahora, con los flujos de botón, es posible hacerlo con un solo clic un botón, y desde cualquier dispositivo móvil.
* **Anuncio de entornos**: los entornos son espacios diferenciados para almacenar y administrar los flujos de una organización. Los entornos están geolocalizados, lo que significa que los flujos, las aplicaciones y los datos empresariales de un entorno estarán en la región en que se encuentra el entorno.
* **Seis nuevos servicios**: se agrega compatibilidad con Bit.ly, Cognitive Services Text Analytics, Dynamics NAV, Dynamics 365 for Financials, Instapaper y Pinterest.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/environments-for-makers/) acerca de esta versión.

### <a name="release-2016-10-16"></a>Versión 2016-10-16
* **Conectores personalizados con más tipos de autenticación**: los conectores personalizados ahora admiten la autenticación de clave de API y pueden autenticarse en cualquier servicio que admita la especificación OAuth 2.0 completa.
* **Tres nuevos servicios**: hemos agregado compatibilidad con Basecamp 3, Blogger y PagerDuty.
* **Mejoras del diseñador**: el rendimiento ha mejorado y ahora puede actualizar y reparar las conexiones directamente desde el menú "..." de cada acción; hemos agregado también un nuevo paso llamado Finalizar que puede usar para finalizar la ejecución de un flujo.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/early-october-updates/) acerca de esta versión.

### <a name="release-2016-09-25"></a>Versión 2016-09-25
Ahora se pueden crear flujos en teléfonos móviles. Examine nuestra completa galería de plantillas, repase nuestra lista de servicios o seleccione la categoría de plantillas que desea ver con más detalle. [Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/mobile-creation/) acerca de esta versión.

### <a name="release-2016-09-22"></a>Versión 2016-09-22
* **Selector de personas de Microsoft Graph**: hay un nuevo selector de personas de Microsoft Graph integrado directamente en la interfaz de usuario de Power Automate para ayudarlo a elegir el contacto o la dirección de correo electrónico correctos.
* **Compatibilidad con Microsoft Dynamics AX**: ahora puede actuar sobre los datos de sus operaciones de Dynamics AX Online desde dentro de los flujos, desde crear nuevos registros a consultar los datos.
* **Dos nuevos servicios de asociados**: ahora puede usar appFigures o Insightly desde los flujos.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/more-september-updates/) acerca de esta versión.

### <a name="release-2016-09-14"></a>Versión 2016-09-14
* **Inserción en su sitio web o aplicación**: los desarrolladores pueden insertar Power Automate directamente en sus aplicaciones o sitios web para ofrecer a sus usuarios una manera sencilla de automatizar sus tareas profesionales o personales.
* **Usar un flujo como un punto de conexión HTTP**: ahora puede usar un flujo como una API HTTP. En Flow hay un desencadenador llamado Request (Solicitud) y puede elegir responder a la solicitud entrante agregando una tarjeta Response (Respuesta).
* **Compatibilidad con Todoist**: Todoist ofrece perspectiva sobre todos los proyectos, en el trabajo y en casa.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/extend-web-site-application/) acerca de esta versión.

### <a name="release-2016-09-01"></a>Versión 2016-09-01
Ahora, Power Automate está disponible para todos. Inicialmente, la versión preliminar se abrió solo para las direcciones de correo electrónico de trabajo o escuela, como las usadas con Office 365 Empresa u Office 365 Enterprise. Hoy anunciamos que la versión preliminar está disponible oficialmente para todos los usuarios, de forma gratuita, independientemente de qué correo electrónico tengan. [Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/available-for-everyone/) acerca de esta versión.

### <a name="release-2016-08-31"></a>Versión 2016-08-31
* **Instrucciones condicionales anidadas**: ahora puede agregar una segunda condición dentro de otra, o una tercera o más.
* **Aplicar a cada**: el bucle ‘aplicar a cada’ permite controlar la lista en la que se repetirá la acción.
* **Hacer hasta**: el bucle ‘hacer hasta’ permite repetir un paso hasta que se cumpla una determinada condición.
* **Filtrar matrices**: un único paso de filtro nativo permite asegurarse de que todos los elementos de la lista coincidan con una expresión que defina.
* **Componer variables de cadena**: ahora puede componer una variable de cadena.
* **Ámbitos**: los ámbitos son una manera sencilla de agrupar dos o más acciones.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/build-advanced-flows/) acerca de esta versión.

### <a name="release-2016-08-27"></a>Versión 2016-08-27
* **Comentarios en pasos**: los comentarios permiten agregar notas a cada acción individual para recordar fácilmente lo que el flujo necesita.
* **Compatibilidad con Smartsheet**: esta semana agregamos compatibilidad para conectarse a Smartsheet. Smartsheet es un servicio que facilita la colaboración en hojas en la nube.
* **Mejoras en la interfaz de usuario durante la creación de flujos**: hemos centrado el nombre del flujo en el frente y hemos movido el botón de guardar a la parte superior de la página para facilitar el acceso.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/add-comments-smartsheet/) acerca de esta versión.

### <a name="release-2016-08-18"></a>Versión 2016-08-18
Ahora puede disfrutar de la nueva experiencia de listas modernas de SharePoint Online, que incluye la integración con Power Automate. [Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/) acerca de esta versión.

### <a name="release-2016-08-13"></a>Versión 2016-08-13
* **Visual Studio Team Services**: con Flow, ahora puede conectar VSTS a una gran variedad de servicios como Correo de Office 365, Slack, Trello y Wunderlist.
* **Mejoras de SharePoint**: las listas de SharePoint admiten diversos tipos de datos, desde objetos simples como líneas individuales de texto o fecha y hora, a objetos complejos tales como personas o grupos, búsqueda y opciones.
* **Probar las conexiones de O365 Outlook**: siempre que cree una nueva conexión a Office 365 Outlook, la probaremos para estar seguros de que está listo para usarla.
* **Control booleano**: también hemos agregado un control booleano para aclarar qué valores se deben especificar en los campos de entrada booleanos, por ejemplo Tiene datos adjuntos en el desencadenador Cada vez que reciba un correo electrónico.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/) acerca de esta versión.

### <a name="release-2016-08-08"></a>Versión 2016-08-08
Versión preliminar pública de Microsoft Common Data Service integrado en Power Automate. [Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/flow-and-common-data-model/) acerca de esta versión.

### <a name="release-2016-08-05"></a>Versión 2016-08-05
* **SharePoint local**: al igual que con SharePoint Online, puede crear flujos para las listas de SharePoint local y las bibliotecas de documentos, mediante plantillas predefinidas o partiendo de cero.
* **Burbujas de información en el diseñador**: para proporcionar información sobre las funcionalidades de cada desencadenador y acción, hemos agregado burbujas de información en cada paso del flujo.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/) acerca de esta versión.

### <a name="release-2016-07-15"></a>Versión 2016-07-15
* **Cuatro nuevos servicios agregados**: conecte con Google Calendar, Google Tasks, YouTube y SparkPost.
* **Cambie el nombre de las acciones**: ahora, puede cambiar el nombre de estas acciones para diferenciarlas.
* **Retraso de diferentes períodos de tiempo**: ahora, puede seleccionar cualquier número de segundos, minutos, horas o días.
* **Explorador de carpetas más fácil de usar**: hemos simplificado el explorador de carpetas. Ahora, al seleccionar en el lado izquierdo, se elegirá esa carpeta y al seleccionar en el lado derecho, se abrirá la carpeta para que pueda elegir las subcarpetas.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/new-google-services-rename-more/) acerca de esta versión.

### <a name="release-2016-07-08"></a>Versión 2016-07-08
Conectividad local para Power Automate con la puerta de enlace de datos local. Esto permite establecer conexiones seguras a SQL Server e integrarlas con los flujos. [Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/on-premises-data-gateway/) acerca de esta versión.

### <a name="release-2016-07-02"></a>Versión 2016-07-02
* **Compatibilidad con Google Sheets**: en el pasado, podíamos usar Excel y Google Drive, pero esta semana hemos agregado compatibilidad nativa con Google Sheets.
* **Comience a trabajar más rápidamente con las plantillas**: también hemos optimizado la forma de comenzar a trabajar con las plantillas. Ahora, puede seleccionar qué cuentas desea usar para una plantilla directamente en la página de la plantilla.
* **Las autorizaciones no expiran para SharePoint y Office 365**: ahora, Power Automate renovará automáticamente el acceso a los servicios basados en Azure Active Directory, por lo que todos los flujos seguirán funcionando incluso después de cambiar la contraseña.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/more-june-updates/) acerca de esta versión.

### <a name="release-2016-06-20"></a>Versión 2016-06-20
* **Presentación de la nueva aplicación móvil para Power Automate**: hoy nos complace presentar otra pieza importante de nuestra oferta: una aplicación móvil que ya está disponible para su descarga en iOS (próximamente también en Android) y que ofrece la posibilidad de administrar, realizar seguimiento y explorar sus flujos de trabajo automatizados en cualquier momento y en cualquier lugar.  
* **Inicio de sesión único**: hemos implementado el inicio de sesión único que le permite autenticar Power Automate en otros servicios de Microsoft, por ejemplo, Office 365.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/) acerca de esta versión.

### <a name="release-2016-06-18"></a>Versión 2016-06-18
* **Nuevo servicio de correo**: ahora puede enviar correos electrónicos directamente desde Power Automate sin necesidad de conectarse a sus cuentas de correo electrónico personales o de trabajo dentro de Power Automate.
* **Notificaciones en el portal**: ahora verá las notificaciones en la parte superior del portal cada vez que algo vaya mal con los flujos.
* **Toda la actividad en el portal**: para ver la actividad de todos los flujos, ahora puede hacer clic en la nueva pestaña de actividad en el sitio web de Flow.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/mail-and-all-activity/) acerca de esta versión.

### <a name="release-2016-05-27"></a>Versión 2016-05-27
* **Explorar plantillas por servicio**: ahora puede ver todos los servicios que admitimos, sin tener que iniciar sesión. En esta página puede ver una descripción de cada uno de los servicios y consultar las plantillas que tenemos para ese servicio.
* **Creación y uso de conectores personalizados**: igual que se crean conectores personalizados en Power Apps, también puede conectar con sus propias API directamente en flow.microsoft.com:
* **Probar los flujos antes de finalizar**: cada vez que guarde un flujo, ahora verá los resultados de la ejecución del flujo directamente en la página, si realiza la acción de inicio.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/) acerca de esta versión.

### <a name="release-2016-05-07"></a>Versión 2016-05-07
Se han agregado dos nuevos servicios: Microsoft Project Online y Mandrill de Mailchimp. [Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/) acerca de esta versión.

### <a name="release-2016-04-27---public-preview"></a>Versión 2016-04-27: versión preliminar pública
Si utiliza flujos de lógica como parte de [Microsoft Power Apps](https://powerapps.microsoft.com), la versión preliminar de Power Automate ofrece varias características nuevas:

* Ahora puede examinar una galería de docenas de plantillas y ordenarlas por popularidad, nombre o fecha de publicación.
* Puede [publicar sus propias plantillas](publish-a-template.md) en la galería después de personalizar un flujo.
* Puede ver el historial de cada comprobación y ejecución de los flujos.
* Al guardar un flujo, puede [verlo en acción de inmediato](see-a-flow-run.md), solo tiene que realizar la acción del desencadenador.
* Tenemos una [nueva comunidad](https://go.microsoft.com/fwlink/?LinkID=787467), donde puede intercambiar información sobre Flow o [enviar sus ideas](https://go.microsoft.com/fwlink/?LinkID=787474).

## <a name="next-steps"></a>Pasos siguientes
Si tiene algún problema que no se haya incluido en estas notas de la versión o en la sección de [preguntas más frecuentes](frequently-asked-questions.md), [únase a nuestra comunidad](https://go.microsoft.com/fwlink/?LinkID=787467), donde puede realizar cualquier pregunta, o [póngase en contacto con el departamento de soporte técnico](https://go.microsoft.com/fwlink/?LinkID=787479).

