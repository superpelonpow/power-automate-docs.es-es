---
title: Preguntas y respuestas sobre la suscripción de Power Automate en su organización | Microsoft Docs
description: Preguntas comunes y respuestas acerca de las licencias, administración y usuarios que se suscriben a Power Automate en el inquilino de Office 365.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/05/2016
ms.author: stepsic
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: fbadbf62760544410cf8fee74f4cecb43cbdefd5
ms.sourcegitcommit: 4b9261984a554dfccb0d0d77f3d5fdca60e26433
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "3340104"
---
# <a name="power-automate-in-your-organization-qa"></a>Preguntas más frecuentes sobre Power Automate en la organización

En este tema se describe cómo los usuarios de su organización pueden usar Power Automate y cómo controlar el servicio Power Automate.

## <a name="signing-up-for-power-automate"></a>Registrarse a Power Automate
### <a name="what-is-power-automate"></a>¿Qué es Power Automate?
Power Automate es un servicio público en la nube para ayudar a usuarios y equipos a configurar flujos de trabajo automatizados entre sus aplicaciones y servicios favoritos para sincronizarlos, recibir notificaciones, recopilar datos y mucho más. 

### <a name="how-do-people-sign-up-for-power-automate"></a>¿Cómo se realiza la suscripción a Power Automate?
Hay dos formas de suscribirse a Power Automate mediante el portal web:

#### <a name="option-1"></a>Opción 1
Los usuarios pueden suscribirse en [flow.microsoft.com](https://flow.microsoft.com); para ello, deben seleccionar **Regístrese gratis** y completar el proceso de suscripción a Power Automate desde [admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free) o [signup.live.com](https://signup.live.com).

#### <a name="option-2"></a>Opción 2
Los usuarios pueden suscribirse en [flow.microsoft.com](https://flow.microsoft.com) para ello, deben seleccionar **Iniciar sesión**, suscribirse con su correo electrónico profesional, educativo o personal y aceptar las condiciones de uso de Power Automate.    

Cuando un usuario de su organización se suscribe a Power Automate con la opción 2, se le asignará una licencia gratuita de Power Automate automáticamente.

El artículo [Suscribirse a Flow](sign-up-sign-in.md) incluye más información.

### <a name="what-is-the-power-automate-free-plan"></a>¿Cuál es el plan gratuito de Power Automate?

El plan gratuito de Power Automate solo se incluye con fines de seguimiento. Habilitarlo o deshabilitarlo no tiene ningún efecto en la capacidad del usuario para crear flujos. Si deshabilita el plan gratuito de Power Automate, se vuelve a habilitar cuando un usuario inicia sesión. Este es el comportamiento esperado.

### <a name="can-i-block-another-person-from-signing-up-for-flow"></a>¿Puedo bloquear la suscripción de otra persona a Flow?
Power Automate es un servicio en la nube totalmente público, y todas las personas pueden suscribirse y utilizarlo para automatizar sus tareas diarias. Para utilizar Power Automate no es necesario que los usuarios tengan o usen una cuenta de Office 365. Por este motivo, no hay ningún mecanismo en este momento para impedir que una persona use Power Automate (como cualquier otra persona del mundo, con independencia de su dirección de correo electrónico).

Sin embargo, si una persona se suscribe a Power Automate y decide no admitirlo en su organización, de ninguna forma puede incurrir en costos para su empresa. Cuando una persona se suscribe a Power Automate, es la relación se establece entre ella y Microsoft, que es como muchos otros servicios en la nube de Microsoft, como Bing, OneDrive o Outlook.com. El hecho de que un individuo use Power Automate no implica en absoluto que su organización proporcione el servicio.

Por último, si su compañía desea limitar el uso de los datos de solo de la organización dentro de Power Automate, eso es posible a través de las directivas de prevención de pérdida de datos (DLP).

### <a name="how-can-people-gain-access-to-the-paid-features-of-power-automate"></a>¿Cómo se puede acceder a las características de pago de Power Automate?
Las personas pueden acceder a las características de pago de Power Automate de tres maneras diferentes:

1. Pueden suscribirse a un Flow Plan 1 o Flow Plan 2, con una prueba gratuita de 90 días.
2. Puede asignarles una licencia de Power Automate en el portal de administración de Office 365.
3. Se ha asignado al usuario planes de Office 365 y Dynamics 365, que incluyen el acceso a Power Automate. Vea la [página de precios de Power Automate](https://flow.microsoft.com/pricing/) para la lista de planes de Office 365 y Dynamics 365 que incluyen capacidades de Power Automate.

### <a name="can-i-block-another-person-from-using-the-paid-features-of-flow"></a>¿Puedo bloquear la suscripción de otra persona a las características de pago de Flow?
Cualquier persona puede probar las características de pago de Power Automate durante 90 días sin incurrir en ningún costo. Sin embargo, puede administrar completamente la asignación de las licencias de pago perpetuas dentro de su organización mediante el portal de administración de Office 365.

Igual que con las ofertas gratuitas, si una persona decide suscribirse a la versión de prueba, se trata de una relación directa entre la persona y Microsoft, no necesariamente reconocida por su empresa.

## <a name="administration-of-flow"></a>Administración de Flow
### <a name="why-has-the-power-automate-icon-appeared-in-the-office-365-app-launcher"></a>¿Por qué aparece el icono de Power Automate en el iniciador de aplicaciones de Office 365?
Como se anunció en agosto, ahora Power Automate es una parte fundamental del conjunto de Office 365. Tres meses después de este anuncio, se habilitó Power Automate como un servicio en todas las SKU de Office 365 existentes. Como ahora los usuarios de todo el mundo pueden utilizar Power Automate, ha aparecido en el iniciador de aplicaciones para ellos.

Si desea quitar el icono de Power Automate del iniciador de aplicaciones de forma predeterminada, consulte la sección siguiente.

### <a name="how-do-i-remove-power-automate-from-the-app-launcher-for-my-organization"></a>¿Cómo quito Power Automate del iniciador de aplicaciones para mi organización?
Si se asignó una licencia de Flow Plan 1 o 2 a un usuario, puede realizar los pasos siguientes para quitar la licencia de Power Automate para ese usuario, con lo que se quitará el icono de Power Automate del iniciador de aplicaciones:

1. Vaya al [Portal de administración de Office 365](https://portal.microsoftonline.com/).
2. En la barra de navegación de la izquierda, seleccione **Usuarios**y, a continuación seleccione **Usuarios activos**.
3. Busque el usuario al que desea quitar la licencia y luego seleccione su nombre.
4. En el panel de detalles del usuario, en la sección **Licencias de productos**, seleccione **Editar**.
5. Busque la licencia **Power Automate Plan 1** o **Power Automate Plan 2**, establezca el control de alternancia en **Desactivado** y seleccione **Guardar**.
   
   ![](./media/organization-q-and-a/remove-license.png)

Si un usuario tiene acceso a Power Automate a través de su licencia de planes de Office 365 y Dynamics 365, puede deshabilitar su acceso a las características adicionales incluidas en este plan realizando los pasos siguientes:

1. Vaya al [Portal de administración de Office 365](https://portal.microsoftonline.com/).
2. En la barra de navegación de la izquierda, seleccione **Usuarios**y, a continuación seleccione **Usuarios activos**.
3. Busque el usuario al que desea quitar el acceso y luego seleccione su nombre.
4. En el panel de detalles del usuario, en la sección **Licencias de productos**, seleccione **Editar**.
5. Expanda la licencia de Office 365 o Dynamics 365 del usuario, deshabilite el acceso para el servicio **Flow para Office 365** o **Flow para Dynamics 365** y seleccione **Guardar**.
   
   ![](./media/organization-q-and-a/remove-service-plan.png)

La eliminación en masa de licencias también es posible a través de PowerShell. Vea [Quitar licencias de cuentas de usuario con Office 365 PowerShell](https://technet.microsoft.com/library/dn771774.aspx) para ver un ejemplo detallado.   Finalmente, encontrará instrucciones adicionales sobre la eliminación en masa de servicios en una licencia en [Deshabilitar acceso a servicios con Office 365 PowerShell](https://technet.microsoft.com/library/dn771769.aspx).

Al eliminar el servicio o la licencia de Power Automate para un usuario de su organización, se eliminará el icono de Power Automate de las siguientes ubicaciones para dicho usuario:

1. [Office.com](https://office.com)
   
   ![](./media/organization-q-and-a/office-home.png)
2. Iniciador de aplicaciones de Office 365
   
   ![](./media/organization-q-and-a/office-waffle.png)

Tenga en cuenta que esto solo eliminará el icono de Power Automate de forma predeterminada. Un usuario aún podrá utilizar Power Automate como usuario individual.

### <a name="why-did-10000-licenses-for-power-automate-show-up-in-my-office-365-tenant"></a>¿Por qué se mostraron 10.000 licencias para Power Automate en mi inquilino de Office 365?
Cualquier persona puede probar el plan 1 o 2 de Power Automate durante 90 días, y estas licencias de prueba representan la capacidad disponible de nuevos usuarios de Power Automate en el inquilino. No hay cargo por estas licencias. Concretamente, hay dos razones posibles para ver una capacidad de 10.000 licencias de prueba para Power Automate en el portal de administración de Office 365:

1. Si al menos un usuario del inquilino participó en la vista previa pública de Power Automate que se extendió desde abril de 2016 a octubre de 2016 verá 10.000 licencias etiquetadas como “Microsoft Power Apps y flujos lógicos”
   
    ![](./media/organization-q-and-a/licenses2.png)
2. Si al menos un usuario en el inquilino se suscribió a la prueba de Flow Plan 2 yendo a través de la suscripción de prueba **Opción 1**, que se describe en la sección sobre [cómo realizan los usuarios la suscripción a Power Apps](#how-do-people-sign-up-for-power-automate), verá 10 000 licencias con la etiqueta "Microsoft Power Apps & Flow".
   
    ![](./media/organization-q-and-a/licenses1.png)

Puede asignar licencias adicionales a los usuarios mediante el portal de administración de Office 365, pero tenga en cuenta que se trata de licencias de prueba de Power Automate Plan 2 y caducarán después de 90 días de la asignación.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>¿Esto es gratis? ¿Se me cobrarán estas licencias?
Ningún usuario puede incurrir en ningún gasto para su organización sin su consentimiento expreso, por lo que ninguna licencia gratuita ni de prueba puede causar ningún cargo a su organización. Además, tampoco utilizan ninguna cuota, como cuotas de ejecución.

### <a name="i-removed-the-power-automate-free-license-and-users-can-still-access-flow"></a>He eliminado la licencia gratuita de Power Automate y los usuarios ¿aún pueden acceder a Flow?
La licencia gratuita de Power Automate se incluye con fines de seguimiento. Tal como se explicó en la primera sección, no es posible impedir que otra persona use Power Automate para fines individuales. Por lo tanto, la presencia de una licencia gratuita de Power Automate no concede ni elimina ninguna funcionalidad.

### <a name="why-cant-i-see-all-power-automate-licenses-in-the-office-365-admin-portal"></a>¿Por qué no se ven todas las licencias de Power Automate en el Portal de administración de Office 365?
Los usuarios pueden utilizar Power Automate a nivel individual o como parte de su organización. Las licencias a nivel de organización siempre estarán visibles en el Portal de Office 365. Sin embargo, si un usuario se suscribe para una versión de evaluación, su administrador de Office 365 no la administrará y no se mostrará en el portal.

### <a name="how-does-an-individual-find-out-what-plan-they-are-on"></a>¿Cómo averigua un individuo en qué plan está?
Cualquier usuario puede ver su plan si visita la página de precios de Power Automate en [https://flow.microsoft.com/pricing](https://flow.microsoft.com/pricing). En dicha página se puede ver el plan o la versión de evaluación activos.

### <a name="will-power-automate-sign-up-impact-the-identities-in-my-organization"></a>¿La suscripción a Power Automate afectará a las identidades de mi organización?
Si su organización ya tiene un entorno de Office 365 existente y todos los usuarios de su organización tienen cuentas de Office 365, la administración de las identidades no se verá afectada.

Si su organización ya tiene un entorno de Office 365 existente pero no todos los usuarios de la organización tienen cuentas de Office 365, creamos un usuario en el inquilino y le asignamos licencias basadas en la dirección de correo electrónico del trabajo o el centro escolar del usuario. Esto significa que el número de usuarios que usted administra en cualquier momento específico crecerá cuando los usuarios de su organización se suscriban al servicio.

Si su organización no tiene un entorno de Office 365 conectado al dominio de correo electrónico, no hay cambios realizados en cómo administra la identidad. Se agregarán usuarios a un nuevo directorio de usuarios solo en la nube y usted tendrá la opción de asumir el control como administrador de inquilinos y administrarlos.

### <a name="a-new-tenant-was-created-by-power-automate-how-do-i-manage-this"></a>Power Automate ha creado un inquilino ¿cómo puedo administrarlo?
Si Power Automate ha creado un inquilino nuevo, puede reclamarlo y administrarlo mediante estos pasos:

1. Una al inquilino suscribiéndolo a Power Automate mediante un dominio de dirección de correo electrónico que coincida con el dominio de inquilino que desea administrar. Por ejemplo, si Microsoft creó el inquilino contoso.com, una el inquilino con una dirección de correo electrónico que termine en @contoso.com.
2. Solicite control de administración verificando la propiedad del dominio: una vez que esté en el inquilino, puede promocionarse a usted mismo al rol de administrador comprobando la propiedad del dominio. Para ello, siga estos pasos:    
   
   1. Vaya a [https://admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free).
   2. Seleccione el icono del iniciador de aplicaciones en la esquina superior izquierda y elija Administrador.
   3. Lea las instrucciones de la página **Convertirse en administrador** y, a continuación elija **Sí, quiero ser el administrador**.  
      
       **NOTA**: Si no aparece esta opción, significa que ya hay un administrador de Office 365 establecido.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Si tengo varios dominios, ¿puedo controlar el inquilino de Office 365 al que se agregan usuarios?
Si no hace nada, se creará un inquilino para cada dominio y subdominio de correo electrónico de usuario.

Si desea que todos los usuarios estén en el mismo inquilino sin importar las extensiones de la dirección de correo electrónico:  

* Cree un inquilinos de destino con antelación o use un inquilino existente. Agregue todos los dominios y subdominios existentes que desee consolidar en el inquilino. A continuación todos los usuarios con direcciones de correo electrónico que terminen en esos dominios y subdominios se unen automáticamente al inquilino de destino cuando se suscriben.

**IMPORTANTE**: No hay ningún mecanismo automático que permita mover usuarios entre inquilinos una vez que se han creado. Para obtener más información sobre agregar dominios a un inquilino individual de Office 365, consulte [Agregar los usuarios y dominios a Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-ffdb2216-330d-4d73-832b-3e31bcb5b2a7).

### <a name="how-can-i-restrict-my-users-ability-to-access-my-organizations-business-data"></a>¿Cómo puedo restringir la capacidad de mis usuarios para acceder a los datos empresariales de mi organización?
Power Automate permite crear las zonas de datos para datos profesionales y no profesionales, como se muestra a continuación. Una vez que se implementan estas directivas de prevención de pérdida de datos, se impide a los usuarios que diseñen o ejecuten Power Automate que combinen datos profesionales y no profesionales. Para obtener más información, consulte [Directivas de prevención de pérdida de datos (DLP)](prevent-data-loss.md).

  ![](./media/organization-q-and-a/data-loss-prevention-policy.png)

