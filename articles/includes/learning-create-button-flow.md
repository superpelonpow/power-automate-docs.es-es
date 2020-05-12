En este tema, aprenderá a **crear un flujo de botón** para la empresa Contoso Flooring. 

Los flujos de botón se pueden usar para **enviar correo electrónico** a un equipo para **alertarles de las tareas** que se deben realizar. La **propiedad** de los flujos se **puede asignar a un** trabajador o la pueden **compartir varios** miembros de un equipo.  

1. En primer lugar, vaya al [sitio web de Power Automate](https://ms.flow.microsoft.com) e inicie sesión.
2. Una vez que haya iniciado sesión, seleccione **Mis flujos** y, después, **Crear desde cero**.
   
    ![Crear desde cero](./media/learning-create-button-flow/2-create-from-blank.png)
   
    Lo primero que necesitará es un desencadenador. Puede usar el flujo de botón. 
3. Si no está en la lista, seleccione **Buscar entre cientos de conectores y desencadenadores** en la parte inferior de la página, escriba **botón**, y aparecerá automáticamente. 
4. Seleccione **Botón de flujo para móviles**.
   
    ![Botón Buscar](./media/learning-create-button-flow/3-button-flow.png) 
5. Seleccione **Botón de flujo para móvil - Desencadenar un flujo manualmente**.
   
    ![Seleccionar desencadenador manual](./media/learning-create-button-flow/4-press-it.png)
6. En la pantalla de entrada, seleccione **Agregar texto de entrada**,
   
    ![Agregar entrada](./media/learning-create-button-flow/5-add-input.png)
7. Escriba **Contoso Flooring** en el primer cuadro de texto y **Warehouse delivery email** en el segundo.
   
    ![Agregar entrada](./media/learning-create-button-flow/6-text-for-flow.png)
8. Seleccione **Nuevo paso**. 
   
    ![Texto de entrada](./media/learning-create-button-flow/7-input-description.png)
9. Seleccione **Agregar una acción**. 
   
    ![Agregar acción](./media/learning-create-button-flow/8-add-an-action.png)
10. Seleccione el conector **Office 365 Outlook**. Si no está, busque **outlook**.
    
     ![Buscar outlook](./media/learning-create-button-flow/9-search-outlook.png)
11. Seleccione **Office 365 Outlook: Enviar un correo electrónico**.
    
     ![Enviar correo electrónico](./media/learning-create-button-flow/10-send-email.png)
    
     Cuando se presiona el botón, se envía un correo electrónico a todos los miembros del equipo de Contoso Warehouse, independientemente del lugar en que se encuentren en el edificio, en el que se les informa de que la entrega ha llegado.
12. Expanda los campos y personalice el correo electrónico para Contoso Flooring.
    
    1. En el campo **Para**, escriba una dirección de correo electrónico que sea válida en su organización.
    2. En el campo **Asunto**, escriba **Delivery Arrived**. 
    3. A la derecha, observe que ha aparecido un cuadro **Contenido dinámico**. Para mostrar en la línea de asunto, la fecha y hora exactas en que se presionó el botón, seleccione **Fecha** y **Marca de tiempo**. 
       
        ![Fecha y hora de correo electrónico](./media/learning-create-button-flow/11-email-date-time.png)
13. Ahora, escriba el **cuerpo** del correo electrónico, que diga algo así como, **Warehouse Team, please come to the unload bay as todays delivery has arrived**.
14. Seleccione **Crear flujo** para guardar el flujo.
    
     ![Crear flujo](./media/learning-create-button-flow/12-create-flow.png)

## <a name="create-a-team-flow"></a>Creación de un flujo de equipo
Este flujo de botón se puede usar como ejemplo de cómo crear un flujo de equipo. ¿Qué pasa si el creador del flujo está de baja por enfermedad? ¿Qué pasa si esa persona deja la empresa? Para asegurarse de que el flujo no deja de ejecutarse, agregue copropietarios.

1. Seleccione el **icono del equipo** en el flujo para agregar un copropietario.
   
    ![Crear flujo de equipo](./media/learning-create-button-flow/13-create-team-flow.png) 
2. Escriba los nombres, direcciones de correo electrónico o grupos de usuarios para agregar a los copropietarios.
   
    ![Agregar copropietarios](./media/learning-create-button-flow/14-add-co-owners.png)
3. Para quitar copropietarios, haga clic en la papelera que hay a la derecha de su nombre.
   
    ![Quitar copropietarios](./media/learning-create-button-flow/15-remove-co-owners.png)
4. Para finalizar la eliminación, seleccione **Quitar este propietario**.
   
    ![Quitar copropietarios](./media/learning-create-button-flow/16-agree-to-remove.png)

## <a name="summary"></a>Resumen
En esta lección, ha visto cómo **crear un flujo de botón**. 

En cuestión de minutos, el flujo dio a una trabajadora del almacén la capacidad de **alertar al equipo** ante la **llegada de una entrega**, con el fin de que el equipo no tuviera que estar esperando y perdieran un tiempo valioso que podrían emplear en realizar otras tareas. 

Luego, la trabajadora ha compartido dicho botón con el equipo para que otros puedan desencadenar el mismo flujo cuando ella no esté.

## <a name="next-lesson"></a>Siguiente lección
En la siguiente lección se explicará cómo crear un flujo que usa **notificaciones push**.

