---
title: Introducción a las directivas de prevención de pérdida de datos (DLP). | Microsoft Docs
description: Introducción a las directivas de prevención de pérdida de datos de Power Automate.
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
ms.date: 04/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 63e49b656527f471d7bdd5a5d7a0b02d572c1221
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "74374778"
---
# <a name="data-loss-prevention-dlp-policies"></a>Directivas de prevención de pérdida de datos (DLP)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este documento presenta las directivas de prevención de pérdida de datos, que ayudan a proteger los datos de la organización al evitar que se compartan con una lista de conectores que se definen.

## <a name="whats-a-data-loss-prevention-policy"></a>¿Qué es una directiva de prevención de pérdida de datos?

Los datos de una organización son fundamentales para su éxito. Los datos tienen que estar disponibles de inmediato para la toma de decisiones, pero tienen que protegerse de manera que no se compartan con personas que no deben tener acceso a ellos. Para proteger estos datos, Power Automate ofrece la posibilidad de crear y aplicar directivas que definen qué conectores de consumidor pueden acceder a los datos empresariales y compartirlos. Estas directivas que definen cómo se pueden compartir los datos se conocen como directivas de prevención de pérdida de datos (DLP).

## <a name="why-create-a-dlp-policy"></a>¿Por qué crear una directiva DLP?

Una directiva de DLP se crea para definir claramente qué conectores de consumidor pueden acceder a los datos empresariales y compartirlos. Por ejemplo, es posible que una organización que usa Power Automate no quiera que sus datos empresariales de SharePoint se publiquen automáticamente en su fuente de Twitter. Para evitarlo, se crea una directiva de DLP que bloquea el uso de los datos de SharePoint como fuente de tweets.

## <a name="benefits-of-a-dlp-policy"></a>Ventajas de una directiva DLP

* Garantiza que los datos se administran de forma uniforme en toda la organización.
* Evita que los datos empresariales importantes se publiquen accidentalmente en conectores como sitios de redes sociales.

## <a name="managing-dlp-policies"></a>Administración de directivas DLP

### <a name="prerequisites-for-managing-dlp-policies"></a>Requisitos previos para administrar directivas de DLP

* Permisos del administrador de inquilinos o entornos.

    Puede obtener más información sobre permisos en el [artículo sobre entornos](environments-overview-admin.md).
* Una [licencia P2 de Power Automate](billing-questions.md).

## <a name="create-a-dlp-policy"></a>Crear una directiva DLP

### <a name="prerequisites-for-creating-dlp-policies"></a>Requisitos previos para crear directivas de DLP

Para crear una directiva de DLP, es preciso tener permisos al menos en un entorno.

Siga estos pasos para crear una directiva de DLP que evite que los datos del sitio de SharePoint de la empresa se publiquen en Twitter:

1. Inicie sesión en el [Centro de administración de Power Automate](https://admin.flow.microsoft.com) (Centro de administración).

1. Seleccione la pestaña Directivas de datos y luego el vínculo **Nueva directiva**:

    ![Iniciar sesión](./media/prevent-data-loss/create-policy-1.png)
1. Seleccione la pestaña **Grupos de datos**.

1. Escriba el nombre de la directiva de DLP, por ejemplo *Secure Data Access for Contoso*, en la etiqueta **Nombre de la directiva de datos** de la parte superior de la página:

    ![Iniciar sesión](./media/prevent-data-loss/create-policy-2.png)

1. Seleccione el [entorno](environments-overview-admin.md) en la pestaña **Entornos**.

    > [!NOTE]
    > Como administrador de entorno, puede crear directivas que se apliquen solo a un entorno. Como administrador de inquilinos, puede crear directivas que se apliquen a cualquier combinación de entornos:
    >
    >

    ![Seleccionar entorno](./media/prevent-data-loss/create-policy-3.png)

1. Seleccione la pestaña **Grupos de datos**:

    ![Selección de grupos de datos](./media/prevent-data-loss/create-policy-4.png)

1. Seleccione el vínculo **Agregar** que se encuentra dentro del cuadro de grupo **Business data only** (Solo datos profesionales):

    ![Selección de Agregar](./media/prevent-data-loss/create-policy-5.png)

1. Seleccione los conectores **SharePoint** y **Salesforce** en la página **Agregar conectores**:

   ![Selección de conectores](./media/prevent-data-loss/create-policy-6.png)

1. Seleccione el botón **Agregar conectores** para agregar los conectores que pueden compartir datos empresariales.

1. Seleccione **Guardar directiva** en la esquina superior derecha de la pantalla.

1. Transcurridos unos minutos, la nueva directiva DLP se mostrará en la lista de directivas de prevención de pérdida de datos:

    ![Lista de DLP](./media/prevent-data-loss/create-policy-9.png)

1. **Opcional** Envíe un correo electrónico u otra comunicación al equipo avisándoles de que hay ahora una nueva directiva DLP disponible.

Enhorabuena, ya ha creado una directiva de DLP que permite a la aplicación compartir datos entre SharePoint y Salesforce y que bloquea el uso compartido de datos con cualquier otro servicio.

> [!NOTE]
> Al agregar un servicio a un grupo de datos, automáticamente se quita del otro grupo de datos. Por ejemplo, si actualmente Twitter está en el grupo de datos **business data only** y no desea permitir que los datos empresariales se compartan con Twitter, basta con agregar el servicio Twitter al grupo **no business data allowed**. Esto quitará Twitter desde el grupo de datos "business data only".
>
>

## <a name="data-sharing-violations"></a>Infracciones de uso compartido de datos

Si ha creado la directiva de DLP descrita arriba, si un usuario crea un flujo que comparte datos entre Salesforce (que está en el grupo de datos de **solo datos empresariales**) y Twitter (que está en el grupo de datos de **ningún dato empresarial permitido**), se notifica al usuario que el flujo se ha **suspendido** debido a un conflicto con la directiva de prevención de pérdida de datos creada.

![Creación de flujo](./media/prevent-data-loss/10.png)

Si los usuarios se ponen en contacto con usted acerca de flujos suspendidos, aquí hay algunas cosas a tener en cuenta:

1. En este ejemplo, si hay una razón empresarial válida para compartir datos empresariales entre SharePoint y Twitter, puede editar la directiva de DLP.

1. Pida al usuario que modifique el flujo para cumplir con la directiva DLP.

1. Pida al usuario que deje el flujo en estado suspendido hasta que se tome una decisión sobre el uso compartido de datos entre estas dos entidades.

## <a name="find-a-dlp-policy"></a>Buscar una directiva DLP

### <a name="admins"></a>Administradores

Los administradores pueden usar la característica de búsqueda desde el Centro de administración para buscar directivas DLP específicas.

> [!NOTE]
> Los administradores deben publicar todas las directivas de DLP para que los usuarios de la organización las conozcan antes de crear flujos.
>
>

### <a name="makers"></a>Responsables de toma de decisiones

Si no tiene permisos de administrador y desea obtener más información acerca de las directivas DLP en su organización, póngase en contacto con su administrador. También puede obtener más información en el [artículo sobre entornos de creadores](environments-overview-maker.md).

> [!NOTE]
> Los administradores son los únicos que pueden editar o eliminar directivas de DLP.
>
>

## <a name="edit-a-dlp-policy"></a>Editar una directiva DLP

1. Inicie el [Centro de administración](https://admin.flow.microsoft.com).

1. En el Centro de administración que se inicia, seleccione la **datos directivas** vínculo en el lado izquierdo.

    ![Selección de directivas de datos](./media/prevent-data-loss/2.png)

1. Busque en la lista de directivas de DLP existentes y seleccione el botón de edición que aparece junto a la directiva que quiere editar.

1. Realice los cambios necesarios en la directiva. Puede modificar el entorno o los servicios en los grupos de datos, por ejemplo.

1. Seleccione **Guardar directiva** para guardar los cambios.

> [!NOTE]
> Los administradores de entorno pueden ver las directivas de DLP creadas por los administradores de inquilinos, pero no pueden editarlas.
>
>

## <a name="delete-a-dlp-policy"></a>Eliminar una directiva DLP

1. Inicie el [Centro de administración](https://admin.flow.microsoft.com).

1. Seleccione la pestaña **Directivas de datos** en el lado izquierdo.

    ![Selección de la pestaña Directivas de datos](./media/prevent-data-loss/2.png)

1. Busque en la lista de directivas de DLP existentes y luego seleccione el botón de eliminación que aparece junto a la directiva que quiere eliminar:

    ![Selección del botón de eliminación](./media/prevent-data-loss/3-delete.png)

1. Confirme que realmente desea eliminar la directiva seleccionando el botón **Eliminar**:

    ![Confirmación de que realmente quiere eliminar la directiva](./media/prevent-data-loss/4.png)

## <a name="dlp-policy-permissions"></a>Permisos de las directivas DLP

Solo los administradores de inquilinos y entornos pueden crear y modificar directivas DLP. Puede obtener más información sobre permisos en el artículo sobre [entornos](environments-overview-admin.md).


## <a name="custom-and-http-connectors"></a>Conectores HTTP y personalizados

Los conectores personalizados y HTTP se deben agregar a las DLP mediante una plantilla de Power Automate o PowerShell.

> [!TIP]
> No puede cambiar a una versión anterior desde la versión de esquema 2018-11-01. No se puede quitar la compatibilidad con HTTP de una directiva. Si intenta quitar la compatibilidad con HTTP, se podría dañar la directiva DLP. Además, si se actualiza una directiva DLP para admitir conectores HTTP, es posible que los flujos actuales que usan estas funcionalidades HTTP se cierren.

Estos son los conectores HTTP que se pueden agregar a una directiva:

- HTTP (y HTTP + Swagger)
- Webhook HTTP
- Solicitud HTTP

## <a name="add-connectors-custom-and-http-connectors-with-templates"></a>Incorporación de conectores personalizados y HTTP con plantillas

Para agregar un conector personalizado a una directiva con una [plantilla](https://flow.microsoft.com/galleries/public/templates/ae9683086770420e902c043e5ed4b363/), escriba el nombre de la directiva, el grupo al cual que va a agregar el conector y el nombre, el identificador y el tipo del conector. Ejecute el flujo una vez para agregar el conector personalizado a la directiva y al grupo especificados.

Para agregar los conectores HTTP a una directiva existente a través de la [plantilla](https://flow.microsoft.com/galleries/public/templates/834eb1366aa54335a5f979014a9e0477/), escriba el nombre de la directiva a la que quisiera agregarlos y ejecute el flujo.

## <a name="add-custom-and-http-connectors-with-powershell"></a>Incorporación de conectores personalizados y HTTP con PowerShell

Para agregar compatibilidad con conectores personalizados o conectores HTTP a una directiva con PowerShell, puede [descargar](https://docs.microsoft.com/powerapps/administrator/powerapps-powershell) e importar los últimos scripts de PowerShell de Power Apps y después usar los cmdlets  “New-AdminDlpPolicy”, “Set-AdminDlpPolicy”, “Add-CustomConnectorToPolicy” y “Remove-CustomConnectorFromPolicy” para modificar la directiva. Use el cmdlet "Get-Help -detailed" como referencia.


> [!IMPORTANT]
> Use la versión del esquema 2018-11-01 al crear o actualizar una directiva DLP para incluir conectores HTTP. Agregar compatibilidad con HTTP mediante la plantilla o PowerShell solo afectará la directiva especificada. Las directivas nuevas creadas a través del Centro de administración no contendrán los conectores HTTP.



## <a name="next-steps"></a>Pasos siguientes

* [Aprender más acerca de los entornos](environments-overview-admin.md)
* [Más información sobre Power Automate](getting-started.md)
* [Más información acerca del Centro de administración](admin-center-introduction.md)
* [Más información sobre la integración de datos](https://docs.microsoft.com/common-data-service/entity-reference/dynamics-365-integration)
