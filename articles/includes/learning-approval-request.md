En un tema anterior, se ha explicado cómo crear un proceso de aprobación de tweets que se almacenan en una lista de SharePoint.  En este tema, podrá ver lo que sucede cuando un aprobador recibe una nueva solicitud de aprobación. 

## <a name="create-and-process-a-request"></a>Creación y proceso de una solicitud
Primero es preciso agregar un elemento a nuestra lista de SharePoint y, después, se puede procesar una solicitud de aprobación de dicho elemento.

1. Abra la lista de SharePoint **ContosoTweets**, que se configuró en un tema anterior.  Seleccione **Nuevo** para crear un tweet nuevo. 
   
    ![Lista SharePoint](./media/learning-approval-request/sharepoint-list-home.png)
2. Agregue los siguientes valores a los campos y seleccione **Guardar**.
   
   * **Title**: promociones
   * **TweetContent**: modificar la nueva línea de Contoso Flooring #ohsocontoso
   * **TweetDate**: fecha de hoy
     
     ![Nuevo elemento de SharePoint](./media/learning-approval-request/sharepoint-new-tweet.png)
3. En **Power Automate**, seleccione **Mis flujos**. 
4. Seleccione el flujo **Publicar elementos de lista en Twitter después de su aprobación** que se configuró en el tema anterior y, después, seleccione el flujo de ejecución en **Historial de ejecución**.
   
    ![Historial de ejecución](./media/learning-approval-request/run-history.png)
5. Seleccione el desencadenador **Cuando se crea un elemento**. Compruebe que se muestra la información del elemento de lista que acaba de crear.
   
    ![Desencadenador de flujo](./media/learning-approval-request/approval-flow.png)
6. En **Outlook**, abra el correo de aprobación automática de la bandeja de entrada y seleccione **Aprobar**. 
   
    ![Solicitud de Outlook](./media/learning-approval-request/outlook-mail.png)
7. En el **Centro de aprobación**, vea los detalles de la solicitud, agregue un comentario y seleccione **Confirmar**. 
   
    ![Centro de aprobación](./media/learning-approval-request/approval-center.png)
8. En **SharePoint**, actualice la lista de**ContosoTweets** y compruebe que el valor de **ApprovalStatus** es **Sí** y que se muestra el comentario que ha escrito. 
   
    ![Actualizar lista en SharePoint](./media/learning-approval-request/sharepoint-list-approved.png)

En este tema, ha visto la experiencia desde punto de vista del aprobador (desde el momento en que recibe un correo electrónico de solicitud de aprobación hasta el procesamiento de la solicitud en el Centro de aprobación).

