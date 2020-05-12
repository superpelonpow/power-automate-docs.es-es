En un tema anterior, ya se ha visto cómo alimentar una fuente de Twitter con una lista de SharePoint de una manera sencilla. En este tema, aprenderá a crear un escenario empresarial más favorable mediante aprobaciones. De esta forma, cualquier persona con acceso a la lista de SharePoint puede enviar tweets y el equipo de redes sociales puede aprobar o rechazar dichos tweets. El equipo mantiene el control de la cuenta y el contenido que se envía a los clientes. 

## <a name="create-an-approval-request-flow"></a>Crear un flujo de solicitud de aprobación
1. En la página principal de **Power Automate**, seleccione **Aprobaciones**, **Crear flujo de aprobación**, desplácese hacia abajo y seleccione la plantilla **Publicar elementos de lista en Twitter después de su aprobación**. 
   
    ![Seleccionar plantilla](./media/learning-approval-center/create-approval.png)
2. Compruebe las credenciales de su cuenta para **SharePoint**, **Aprobaciones** y **Twitter**, y seleccione **Continuar**. 
   
    ![Comprobar credenciales](./media/learning-approval-center/verify-credentials.png)

De forma predeterminada, esta plantilla inicia un proceso de aprobación cada vez que se crea un nuevo elemento en una lista concreta, y si el elemento se aprueba, publica un tweet a Twitter. En este tema, modificará este proceso mediante la adición de pasos que actualizan la lista de SharePoint con la respuesta de aprobación, indicará si se ha aprobado o no, y agregará cualquier comentario que pueda haber agregado el aprobador al tweet propuesto. 

1. En la lista de SharePoint **ContosoTweets** que ha creado, agregue dos columnas nuevas:
   
   1. Seleccione el signo más "**+**" y, después, **Sí/No**
   2. Escriba **ApprovalStatus** y seleccione **Crear**
   3. Seleccione el signo más “**+**” y, después, **Una línea de texto**
   4. Escriba **ApproverComments** y seleccione **Guardar**
      
      ![Agregar columnas](./media/learning-approval-center/new-columns.png)
2. Al regresar a **Power Automate**, en la acción **Cuando se crea un elemento**, escriba los valores siguientes:
   
   * **Dirección del sitio**: la dirección URL de SharePoint del equipo
   * **Nombre de lista**: ContosoTweets
     
     ![Sitio y lista](./media/learning-approval-center/site-address.png)
3. En la acción **Start an approval**, seleccione **Editar** para mostrar todos los campos. 
   
    ![Editar campos](./media/learning-approval-center/edit-all-fields.png)
4. En **Título**, escriba **New tweet for** y seleccione **Título** en la lista de contenido dinámico. 
   
    ![Título](./media/learning-approval-center/tweet-title.png)
5. En **Asignado a**, escriba y seleccione su nombre o un nombre de usuario de prueba. 
   
    ![Asignado a](./media/learning-approval-center/tweet-assigned-to.png)
6. En **Detalles**, elimine los elementos predeterminados y agregue **TweetContent**, **TweetDate** y **Created by DisplayName** desde la lista de contenido dinámico, conectados por las palabras **on** y **by**. 
   
    ![Detalles](./media/learning-approval-center/tweet-details.png)
7. En **Vínculo del elemento**, copie y pegue la dirección URL de la lista de SharePoint, y en **Descripción del vínculo del elemento**, escriba **Contoso Tweet List**. 
   
    ![Vínculo del elemento](./media/learning-approval-center/tweet-item-link.png)
8. En la acción **Condition**, mantenga el mouse sobre el cuadro **En caso positivo**, seleccione el signo más "**+**" y, después, **Agregar una acción**. 
   
    ![Agregar una acción](./media/learning-approval-center/add-an-action.png)
9. Busque un **elemento de actualización**, seleccione el conector de **SharePoint** y luego elija la acción **SharePoint: Actualizar elemento**.
   
    ![Actualizar elemento en SharePoint](./media/learning-approval-center/update-item.png)
10. En **Dirección del sitio** y **Nombre de lista**, vuelva a escribir la dirección URL del sitio y la lista **ContosoTweets**, y en **Identificador**, escriba un **identificador** de la lista de contenido dinámica. 
    
     ![Sitio, lista e identificador](./media/learning-approval-center/address-list-id.png)
11. Seleccione el campo **Título** y en la lista de contenido dinámica, busque **title**. Agregue el elemento **Título** desde la acción **Al crear un nuevo elemento**. 
    
     ![Nuevo título](./media/learning-approval-center/add-title.png)
12. Seleccione **ApprovalStatus** y establezca el valor en **Sí**, luego, seleccione **ApproverComments** y establezca el valor en **Comments** desde la lista de contenido dinámico. 
    
     ![Estado y comentarios](./media/learning-approval-center/approver-status.png)
13. Junto a la parte inferior del cuadro **EN CASO NEGATIVO, NO HACER NADA**, seleccione **Agregar una acción**.
    
     ![Agregar una acción No](./media/learning-approval-center/add-a-no-action.png)
14. Mediante los mismos pasos que utilizó para la configuración de **En caso positivo**, cree una acción **SharePoint – Actualizar elemento** y configure los campos con los mismos valores, salvo **ApprovalStatus**, donde debe elegir **No**. 
    
     ![Estado = no](./media/learning-approval-center/status-no.png)
15. Seleccione la acción **Publicar un tweet**, seleccione **Editar** y establezca **Texto del tweet** en **TweetContent** desde la lista de contenido dinámico.  En la parte superior de la página, seleccione **Crear flujo** para guardar el trabajo. 
    
     ![Publicar y guardar](./media/learning-approval-center/post-tweet.png)

Esta es una de las maneras en que Power Automate puede aumentar la productividad de su equipo. Aunque su equipo aporte ideas, noticias relevantes o instrucciones de productos, no perderá el control de los tweets que se envían a los clientes.

En el tema siguiente, veremos lo que sucede cuando un aprobador recibe una solicitud nueva para un tweet propuesto. 

