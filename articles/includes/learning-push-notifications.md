Para este flujo, va a crear una lista de **SharePoint**, en la que el equipo de marketing de **Contoso Flooring** almacena sus **publicaciones en Twitter** y las fechas de publicación. Después, creará un flujo que publicará automáticamente tweets con su contenido. 

## <a name="connect-power-automate-services"></a>Conectar los servicios de Power Automate
En este tema va a usar los servicios **SharePoint** y **Twitter**. Si usas algún servicio por primera vez, primero tendrá que conectarse a él. 

1. En Power Automate, seleccione el **icono del engranaje** y, después, **Conexiones**.
   
    ![Obtención de una conexión](./media/learning-push-notifications/2-get-connection.png) 
2. Seleccione **Crear conexión**.
   
    ![Creación de una conexión](./media/learning-push-notifications/3-create-connection.png) 
3. Desplácese hacia abajo por la lista, busque Twitter y seleccione **+**.
   
    ![Haga clic en el signo más](./media/learning-push-notifications/4-click-plus.png)
4. Para autorizar una cuenta de Twitter, escriba su nombre de usuario o correo electrónico, y la contraseña y seleccione **Autorizar aplicación**.
   
    ![Creación de identificador y contraseña](./media/learning-push-notifications/5-create-id-pswd.png)
5. Para comprobar las conexiones, seleccione el **icono del engranaje** y **Conexiones**.
   
    ![Mis conexiones](./media/learning-push-notifications/6-my-connections.png)
   
    Debería ver la nueva conexión de Twitter y cualquier otra conexión que haya creado. 
   
    ![Conexión a Twitter](./media/learning-push-notifications/7-twitter-connection.png)

## <a name="build-a-sharepoint-list"></a>Creación de una lista de SharePoint
Lo primero que debe hacer es crear una nueva lista de SharePoint Online para Contoso Flooring. 

1. En SharePoint Online, seleccione **Nuevo** y, después, **Lista**.
   
    ![Crear una lista nueva](./media/learning-push-notifications/1-new-list.png)
2. Asigne a la lista el nombre **Contoso Tweets**. 
3. Desactive la casilla **Show in site navigation** (Mostrar en navegación del sitio) y seleccione **Crear**.
   
    ![Crear lista](./media/learning-push-notifications/2-name-create-list.png)
   
    Al seleccionar **Crear**, SharePoint le lleva a la nueva lista.
4. De forma predeterminada, la lista tiene una sola columna, **Título**. Agregue otra columna y asígnele el nombre **Tweet Contents**. En ella se almacenará el contenido de los tweets. 
   
   1. Seleccione el signo más y, después, seleccione **Más...**
      
       ![Crear lista](./media/learning-push-notifications/3-add-more-column-types.png)
   2. Seleccione **Varias líneas de texto** y, después, seleccione **Aceptar**.
      
       ![Crear lista](./media/learning-push-notifications/4-add-column.png)
5. Agregue una columna para la fecha y hora de los tweets y asígnele el nombre **Tweet Date**.
   
   1. Al igual que en**Tweet Content**, seleccione el signo más y, después, seleccione **Más...**
      
       ![Columna de fecha y hora](./media/learning-push-notifications/5-date-time-col.png)
   2. Desplácese hacia abajo hasta **Formato de fecha y hora**. Seleccione **Fecha y hora**, con el fin de que se incluyan ambos.
      
       ![Fecha y hora](./media/learning-push-notifications/6-date-time-must-do.png)
   3. Seleccione **Aceptar**. La lista **Contoso Tweets** aparece en el sitio de SharePoint y puede agregarle nuevos elementos a la lista.

## <a name="build-the-flow"></a>Crear un flujo
La lista ya está creada, así que ahora se puede crear el flujo.

### <a name="choose-a-trigger"></a>Elección de un desencadenador
1. En Power Automate, vaya a **Mis flujos** y, después, seleccione **Crear desde cero**.
   
    ![Crear desde cero](./media/learning-push-notifications/8-create-from-blank.png)
2. Seleccione **Cuando se crea un elemento**.
   
    ![Incorporación de un desencadenador](./media/learning-push-notifications/9-add-trigger.png)
   
    El objetivo es que el desencadenador se active cuando se agregue una nueva fila con contenido de tweet.
3. Seleccione el sitio de SharePoint y, después, seleccione la lista que configuró anteriormente, **Contoso Tweets**.
   
    ![Nuevo elemento creado](./media/learning-push-notifications/11-set-trigger.png)

Todo esto es para el desencadenador.

### <a name="add-an-action-to-delay-posting"></a>Adición de una acción para retrasar la publicación
1. Seleccione **Nuevo paso** y, luego, **Agregar una acción**. 
   
    ![Adición de un paso y una acción](./media/learning-push-notifications/12-add-step-and-action.png)
2. En el servicio **Programación**, seleccione **Retraso hasta**. 
   
    ![Retraso hasta](./media/learning-push-notifications/13-delay-until-schedule.png)  
3. Establezca el valor de retraso.
   
   1. Pulse o haga clic en el campo **Marca de tiempo**. 
   2. Cuando se abra el cuadro de contenido dinámico, desplácese hasta la parte inferior y verá las tres columnas de la lista de SharePoint: **Título**, **Tweet Date** y **Tweet Content**.
   3. Seleccione **Tweet Date**. 
      
       ![Retrasar hasta la marca de tiempo](./media/learning-push-notifications/14-delay-until-timestamp.png)
      
       Ahora, cuando alguien agrega algo a la lista de SharePoint, todas las acciones se retrasarán hasta la fecha y hora que se establecen en la columna **Tweet Date**.
      
       ![Marca de tiempo dinámica](./media/learning-push-notifications/15-dynamic-timestamp.png)

### <a name="add-an-action-to-post-a-tweet"></a>Adición de una acción para publicar un tweet
Ahora, agregará otra acción que el flujo puede tomar a la fecha y hora especificadas en la columna **Tweet Date**.

1. Seleccione **Nuevo paso**, **Agregar una acción** y busque **Twitter**.
   
    ![Agregar un tweet](./media/learning-push-notifications/16-add-tweet.png) 
2. Elija la acción **Twitter - Publicar un tweet**.
   
    ![Publicar un tweet](./media/learning-push-notifications/17-post-tweet.png) 
3. Pulse o haga clic en el campo **Texto del tweet** y, en el cuadro de contenido dinámico, seleccione **Tweet Contents**. Esta es la secuencia que ha creado. 
   
    ![Contenido de fecha de tweet](./media/learning-push-notifications/18-tweet-date-content.png)
4. Seleccione **Crear flujo...**
   
    ![Crear flujo](./media/learning-push-notifications/19-tiny-create.png) 
5. Seleccione **Listo**.
   
    ![Haga clic en listo](./media/learning-push-notifications/19-click-done.png)
   
    El flujo ya está terminado.
   
    ![El flujo está terminado](./media/learning-push-notifications/20-flow-is-done.png)
   
    Cuando se crea un nuevo elemento en la lista de SharePoint, el flujo retrasará la publicación hasta la fecha establecida previamente. Cuando se cumpla esa fecha, el flujo se realizará la publicación en Twitter con el texto de la columna **Tweet Content** de la lista.

## <a name="next-lesson"></a>Siguiente lección
En la siguiente lección, aprenderá a **ejecutar flujos según una programación** mediante un desencadenador denominado **Periodicidad**.

