En este tema, verá cómo ejecutar flujos programados previamente mediante un desencadenador denominado **Periodicidad**.  Creará un flujo para el equipo de marketing de Contoso que extrae automáticamente las direcciones de correo electrónico de los clientes de una tabla de Excel en OneDrive. Configurará el flujo de forma que, una vez al día, las nuevas direcciones de correo electrónico que se hayan agregado a la hoja de cálculo se agreguen a una lista de clientes de MailChimp. 

## <a name="create-a-scheduled-flow"></a>Creación de un flujo programado
1. Abra **Power Automate**, seleccione **Mis flujos** y después **Crear desde cero**. 
   
    ![](./media/learning-recurrence/flow-create-blank.png)
2. Seleccione **Buscar entre cientos de conectores y desencadenadores**.
3. Busque el servicio **Programación**, selecciónelo y, después, seleccione el desencadenador **Programación - Periodicidad**.
   
    ![](./media/learning-recurrence/flow-recurrence-trigger.png)
4. En **Frecuencia**, elija **Día** y en **Intervalo** escriba **1**. Seleccione **Nuevo paso** y, luego, **Agregar una acción**. 
   
    ![](./media/learning-recurrence/frequency-interval.png)
5. Busque **Excel**, seleccione el servicio **Excel** y seleccione la acción **Excel - Obtener filas**. 
   
    ![](./media/learning-recurrence/excel-get-rows.png)
   
    **Nota**: Asegúrese de seleccionar **Obtener filas**, no **Obtener fila**. 
6. Seleccione **Nombre de archivo** y navegue hasta la ubicación del archivo. Seleccione **Nombre de la tabla** y seleccione la tabla deseada en la hoja de cálculo. 
   
    ![](./media/learning-recurrence/excel-get-file.png)
7. Agregue una nueva acción. 
   
    ![](./media/learning-recurrence/new-step.png)
8. Busque el servicio **MailChimp** y seleccione la acción **MailChimp - Agregar un miembro a una lista**.
   
    ![](./media/learning-recurrence/select-mailchimp.png)
   
    **Nota:** MailChimp es un conector *premium*. En función de su licencia de Power Automate, es posible que tenga que registrarse para obtener una versión de prueba del conector.
9. Agregue los campos **List Id** (Identificador de lista) y **Status** (Estado) en los menús desplegables:
   
   * **List Id** (Identificador de lista): seleccione la lista de distribución de correo de MailChimp que desee
   * **Status** (Estado): seleccione **Subscribed** (Suscrito) 
     
     ![](./media/learning-recurrence/mailchimp-id-status.png)
10. En **Email Address** (Dirección de correo electrónico), use la característica de contenido dinámica para agregar el campo **ContactEmail**. 
    
     ![](./media/learning-recurrence/mailchimp-address.png)
    
     Observe que el flujo crea automáticamente un paso adicional. Flujo detecta que se va a establecer una acción que requiere una acción adicional. Cada vez que el flujo lea una nueva dirección de correo electrónico, también creará una nueva acción para cada fila. 
    
     ![](./media/learning-recurrence/mailchimp-for-each.png)
11. Usar el contenido dinámico para rellenar los campos **Nombre** y **Apellidos**:
    
    * **Nombre**: FirstName
    * **Apellidos**: LastName
      
      ![](./media/learning-recurrence/mailchimp-names.png)

Este flujo se ejecutará una vez al día y obtendrá nuevas filas de esta tabla de Excel, captará la dirección de correo electrónico y el nombre, y los usará para rellenar la lista de correo electrónico de Contoso de MailChimp, lo que le ahorra tiempo y dinero. 

