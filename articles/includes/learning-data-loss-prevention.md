Con una lista cada vez mayor de [servicios disponibles](https://flow.microsoft.com/services) para crear flujos de trabajo con [Power Automate](https://flow.microsoft.com), puede que necesite proteger datos empresariales confidenciales o críticos almacenados en servicios empresariales, como SharePoint o Salesforce. Es posible que su organización necesite crear una directiva que garantice que los datos empresariales confidenciales no se publiquen en servicios de consumidor, como Twitter y Facebook. Con Power Automate, puede crear fácilmente directivas de **prevención de pérdida de datos** (DLP) para controlar de forma estricta con qué servicios al consumidor pueden compartirse sus datos empresariales cuando los usuarios creen flujos.  

## <a name="terms-you-should-get-familiar-with"></a>Términos con los que debe familiarizarse

| Término | Descripción |
| --- | --- |
| **DLP** |Abreviatura de prevención de pérdida de datos. Creará una directiva DLP para administrar el uso compartido de datos entre **servicios**. |
| **Servicios** |Los [servicios](https://flow.microsoft.com/services) son aplicaciones como Salesforce, SharePoint y Twitter. Estos servicios, y mucho más, se usan para crear flujos. |
| **Grupo de datos** |Agrupación lógica de servicios. Los servicios que pueden compartir datos se colocan en el mismo grupo de datos. Hay dos grupos de datos: **business data only** y **no business data allowed**. |
| **Entorno** |Un DLP se aplica a un [entorno](../environments-overview-admin.md). Un entorno contiene los usuarios. |
| **Usuarios** |Los usuarios son miembros de su organización a los que se aplicará una directiva DLP, en función de su pertenencia a un entorno. |
| **Flujo** |Un flujo es una aplicación de flujo de trabajo que utiliza cualquier combinación de los servicios disponibles. |

## <a name="all-about-how-dlp-policies-work"></a>Toda la información sobre cómo funcionan las directivas DLP
Una directiva DLP simplemente es una regla con nombre que coloca cada servicio en uno de los dos grupos de datos mutuamente excluyentes. A continuación, esta regla se aplica a un entorno. Un entorno es una agrupación lógica de usuarios. Los usuarios no pueden crear flujos que compartan datos entre los servicios que ha colocado en grupos de datos diferentes. En otras palabras, sus usuarios solo pueden crear flujos que compartan datos entre los servicios dentro de un **único** grupo de datos. No se pueden compartir datos entre grupos.  

| **Nombre del grupo de datos** | **Descripción del grupo de datos** |
| --- | --- |
| **Business data only** |Todos los servicios de este grupo pueden compartir datos entre ellos. No pueden compartir datos con el grupo de datos **no business data allowed**. |
| **No Business data allowed** |Todos los servicios de este grupo pueden compartir datos entre ellos. No pueden compartir datos con el grupo de datos **business data only**. |

**Nota**: Al agregar automáticamente un servicio al grupo de datos, se quita del otro grupo. Por ejemplo, si actualmente Twitter está en el grupo de datos **business data only** y no desea permitir que los datos empresariales se compartan con Twitter, basta con agregar el servicio Twitter al grupo **no business data allowed**. Así se quita Twitter del grupo de datos **business data only**.

## <a name="heres-what-you-need-to-create-a-dlp"></a>Qué se necesita para crear una DLP
* Acceso al [centro de administración](https://admin.flow.microsoft.com) de Power Automate  
* Una cuenta en el rol del administrador del entorno  
* Un entorno con los usuarios asignados  

## <a name="create-a-dlp-policy"></a>Crear una directiva DLP
Introducción rápida acerca de cómo crear una directiva DLP:  

1. Asigne un nombre a la directiva
2. Seleccione el entorno al que se aplicará la directiva
3. Agregue los servicios a uno de los dos grupos de datos. Recuerde que solo los servicios que se encuentran en un grupo específico pueden compartir datos, por lo que cualquier flujo que se haya creado para compartir datos entre los servicios situados en dos grupos de datos se bloqueará automáticamente cuando el creador lo guarde.  

También hay un [tutorial más detallado](../prevent-data-loss.md) sobre las directivas DLP disponibles.  

## <a name="examples"></a>Ejemplos
* Si creara una directiva que restringiera flujos para compartir datos empresariales solo entre SharePoint, usuarios de Office 365, Office 365 Outlook, OneDrive para la Empresa, Dynamics 365, SQL Server y Salesforce, sería similar al siguiente:  
  ![](./media/learning-data-loss-prevention/a-few-business-centric-services.png)  
* Esta es la apariencia que tendría si decide crear una directiva que no permita a ningún miembro de un entorno concreto crear un flujo que comparta datos de SharePoint. Tenga en cuenta que SharePoint es el único servicio en el grupo de datos **solo datos empresariales**:  
  ![business data only](./media/learning-data-loss-prevention/sharepoint-only-no-sharing-guided-learning.png)

