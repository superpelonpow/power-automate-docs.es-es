---
title: Introducción acerca de los entornos para administradores | Microsoft Docs
description: Uso, creación y administración de entornos de Power Automate
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: sunayv
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 7a2ff7c0957e52f076ccc0cc7fdcb4d09109a404
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194379"
---
# <a name="using-environments-within-power-automate"></a>Uso de entornos en Power Automate


## <a name="benefits"></a>Ventajas

Los entornos proporcionan las ventajas siguientes:

* **Localidad de datos**: los entornos se pueden crear en regiones diferentes y se enlazan a esa ubicación geográfica. Cuando se crea un flujo en un entorno, dicho flujo se enruta a todos los centros de datos de su ubicación geográfica. Esto también mejora el rendimiento.

    Si los usuarios están en Europa, cree y use el entorno en la región de Europa. Si los usuarios están en Estados Unidos, cree y use el entorno de Estados Unidos. 

    > [!IMPORTANT]
    > Si elimina el entorno, también se eliminarán todos los flujos dentro de ese entorno. Esto es aplicable a cualquier elemento que haya creado en ese entorno, incluidas las conexiones, las puertas de enlace, Power Apps y otros.
* **Prevención de la pérdida de datos**: los administradores no desean flujos que obtengan datos de una ubicación interna (como *OneDrive para la Empresa* o una lista de SharePoint que contenga información sobre salarios) y que, después, publiquen los datos públicamente (como en to *Twitter*). Use la prevención de pérdida de datos para controlar los servicios que pueden compartir datos dentro de la implementación de Power Automate.

    Por ejemplo, puede agregar los servicios *SharePoint* y *OneDrive para la Empresa* a una directiva solo de datos empresariales. Los flujos creados en este entorno pueden usar los servicios *SharePoint* y *OneDrive para la Empresa*. Pero no podrán compartir datos con otros servicios que no estén incluidos en la directiva solo de datos empresariales.

  > [!NOTE]
  > Prevención de pérdida de datos está disponible con los SKU de algunas licencias, entre las que se incluye la licencia de P2.

* **Límite de aislamiento para todos los recursos**: todos los flujos, puertas de enlace, conexiones, conectores personalizados, etc. residen en un entorno específico. No existen en ningún otro entorno.
* **Common Data Service**: estas son las opciones que tiene si desea crear un flujo que inserte datos en un servicio:

  * Insertar datos en un archivo de Excel y almacenar este archivo en una cuenta de almacenamiento en la nube, como OneDrive.
  * Cree una instancia de SQL Database y almacene los datos en ella.
  * Utilice Common Data Service para almacenar los datos.

    Todos los entornos pueden tener un máximo de una base de datos para los flujos en Common Data Service. El acceso a Common Data Service depende de la licencia que se compró, porque Common Data Service no se incluye con la licencia gratuita.

## <a name="limitations"></a>Limitaciones

Aunque los entornos proporcionan muchas ventajas, también introducen nuevas limitaciones. El hecho de que los entornos sean un límite de aislamiento significa que nunca se pueden tener recursos que hagan referencia a recursos en *distintos* entornos. Por ejemplo, no puede crear un conector personalizado en un entorno para luego crear un flujo que usa ese conector personalizado en otro entorno.

## <a name="use-the-default-environment"></a>Uso del entorno predeterminado

Todos los usuarios comparten el entorno **predeterminado** y cualquier usuario puede crear flujos en **él**.

> [!TIP]
> En los usuarios de versión preliminar, todos los flujos existentes residen en el entorno predeterminado. Un *usuario de versión preliminar* es alguien que usaba Power Automate antes de su versión de disponibilidad general (GA).

## <a name="the-admin-center"></a>El centro de administrador

Los administradores usan el centro de administrador para crear y administrar los entornos. El centro de administrador se puede abrir de cualquiera de estas dos formas:

### <a name="option-1-select-settings"></a>Opción 1: Selección de Configuración

1. Inicie sesión en [flow.microsoft.com](https://flow.microsoft.com).
1. Seleccione el icono de engranaje para la configuración y elija **Centro de administrador** en la lista:

   ![Configuración y Portal de administrador](./media/environments-overview-admin/settings.png)
1. Se abre el centro de administrador.

### <a name="option-2-open-adminflowmicrosoftcom"></a>Opción 2: Apertura de admin.flow.microsoft.com

Vaya a [admin.flow.microsoft.com](https://admin.flow.microsoft.com) e inicie sesión con su cuenta de trabajo.

## <a name="create-an-environment"></a>Creación de un entorno

1. En el [Centro de administración de Power Automate](https://admin.flow.microsoft.com), seleccione **Entornos**. Verá todos los entornos existentes: ![Entornos](./media/environments-overview-admin/environments-list.png)
2. Seleccione **Nuevo entorno** y proporcione la información necesaria:


   |     Propiedad     |                                                 Descripción                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | Nombre de entorno |              Escriba el nombre del entorno, como `Human Resources` o `Europe flows`.              |
   |      Región      | Elija la ubicación para hospedar el entorno. Para obtener un rendimiento óptimo, use la región más cercana a los usuarios. |
   | Tipo de entorno |                  Elija un tipo de entorno en función de la licencia: producción o evaluación.                   |

     ![configuración del entorno](./media/environments-overview-admin/new-environment-dialog.png)
3. Haga clic en **Crear entorno**.
4. Ahora tiene la opción **Crear base de datos** u **Omitir**.
5. Si elige la opción **Crear base de datos**, se le pedirá que indique una **moneda** y un **idioma** para la base de datos. Además, también puede elegir tener implementados datos y aplicaciones de ejemplo.

   ![configuración de base de datos](./media/environments-overview-admin/create-database-dialog2.png)


Ahora puede agregar usuarios al entorno.

## <a name="manage-your-existing-environments"></a>Administre los entornos existentes

1. En el [Centro de administración de Power Automate](https://admin.flow.microsoft.com), seleccione **Entornos**:

   ![elemento de menú entornos](./media/environments-overview-admin/select-environments.png)
1. Seleccione un entorno para abrir sus propiedades.
1. Use la pestaña **Detalles** para ver información adicional sobre un entorno, entre la que se incluye quién lo creó, su ubicación geográfica y mucho más:

   ![pestaña detalles](./media/environments-overview-admin/open-environment.png)
1. Seleccione **Seguridad**.

    Si no ha seleccionado **Crear base de datos** en los pasos anteriores, hay dos opciones en **Roles de entorno**: **Administrador de entornos** y **Creador de entornos**:

    ![los roles de administrador](./media/environments-overview-admin/environment-roles.png)

    Un **Creador** puede crear recursos nuevos como flujos, conexiones de datos y puertas de enlace en un entorno.

   > [!NOTE]
   > No es necesario que un usuario sea **Creador** para *editar* los recursos de un entorno. Cada Creador determina quién puede editar sus recursos. Para ello, concede permisos a usuarios que no son Creadores de entorno.
   > 
   > 

    Un **Administrador** puede crear directivas de prevención de pérdida de datos y realizar otras tareas administrativas, como crear entornos, agregar usuarios a los entornos y asignar privilegios de administrador o creador.

   1. Seleccione el rol **Creador de entornos** y luego seleccione **Usuarios**: ![rol de creador](./media/environments-overview-admin/add-environment-maker.png)
   1. Escriba un nombre, una dirección de correo electrónico o un grupo de usuarios al que desee asignar el rol de **Creador**.
   1. Seleccione **Guardar**.

1. En **Seguridad**, seleccione **Roles de usuario**:

    ![roles de usuario](./media/environments-overview-admin/security-user-roles.png)

    Se muestran los roles existentes y se incluyen las opciones para editar o eliminar el rol.

    Seleccione **Nuevo rol** para crear un rol nuevo.
1. En **Seguridad**, seleccione **Conjuntos de permisos**:

    ![configuración de permisos](./media/environments-overview-admin/security-permission-set.png)

    Verá todos los conjuntos de permisos y las opciones existentes para editar o eliminar roles.

    Seleccione **Nuevo conjunto de permisos** para crear uno nuevo.
1. Si eligió **Crear base de datos** para almacenar sus datos, esta base de datos forma parte de Common Data Service. Cuando haga clic en la pestaña **Seguridad**, se le pedirá navegar al **Centro de administración de instancias de Dynamics 365** donde se puede aplicar la seguridad basada en roles.
![configuración de seguridad de dynamics](./media/environments-overview-admin/Security-Link-D365.png)

1. Seleccione el usuario en la lista de usuarios del entorno o la instancia.
  ![configuración de seguridad de dynamics](./media/environments-overview-admin/D365-Select-User.png)

1. Asigne el rol al usuario.

   ![asignar el rol al usuario](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> Los usuarios o grupos asignados a estos roles de entorno no reciben automáticamente acceso a la base de datos del entorno (si existe) y un propietario de la base de datos les debe conceder acceso por separado. 
>
>

### <a name="database-security"></a>Seguridad de la base de datos
Los conjuntos de permisos y los roles de usuario de la base de datos controlan la capacidad de crear y modificar un esquema de la base de datos y de conectar con los datos almacenados dentro de una base de datos que se aprovisiona en el entorno. Puede administrar los roles de usuario y los conjuntos de permisos para la base de datos del entorno en la sección **Roles de usuario** y **Conjuntos de permisos** de la pestaña **Seguridad**. 

   ![asignar el rol al usuario](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="can-i-move-a-flow-between-environments"></a>¿Puedo mover un flujo entre distintos entornos?

Sí, los flujos se pueden exportar de un entorno e importarlos a otro.

### <a name="which-license-includes-the-common-data-service"></a>¿Qué licencia incluye Common Data Service?

Solo el plan 2 de Microsoft Power Apps incluye los derechos necesarios para crear bases de datos con Common Data Service. Sin embargo, todos planes de pago (los planes 1 y 2 de Power Automate y los planes 1 y 2 de Microsoft Power Apps) tienen los derechos necesarios para usar Common Data Service.

Para elegir un plan adecuado, visite la página sobre [precios de Power Automate](https://flow.microsoft.com/pricing/).

Consulte el documento [Preguntas sobre facturación](billing-questions.md) para conocer las respuestas a las preguntas más frecuentes relativas a la facturación.

### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>¿Se puede usar Common Data Service fuera de un entorno?

No. Common Data Service requiere un entorno. [Obtenga más información](common-data-model-intro.md) sobre él.

### <a name="what-regions-include-power-automate"></a>¿Qué regiones incluyen Power Automate?

Power Automate admite la mayoría de las regiones que admite Office 365. Consulte [la información general sobre las regiones](regions-overview.md) para más detalles.

### <a name="whats-needed-to-create-my-own-custom-environment"></a>¿Qué necesito para crear mi propio entorno personalizado?

Todos los usuarios con la licencia de plan 2 de Power Automate pueden crear sus propios entornos. Todos los usuarios de Power Automate pueden usar los entornos creados que crean los administradores del plan 2, pero no pueden crear sus propios entornos.
