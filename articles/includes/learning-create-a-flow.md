Le damos la bienvenida de nuevo al aprendizaje guiado de Power Automate. En esta lección, recibirá más información acerca del entorno de Power Automate y podrá **crear su primer flujo**.

Es fácil empezar a usar Power Automate, ya que hay un ingente número de **plantillas para elegir**, que le ayudarán a conectarse a los servicios que ya usa de formas más significativas.  

## <a name="power-automate-templates"></a>Plantillas de Power Automate
Eche un vistazo al [sitio web de Power Automate](https://ms.flow.microsoft.com) y abra el menú **Plantillas**. A medida que se desplace por la lista, verá que Power Automate le permite conectarse a numerosos servicios.

![Sitio web de Flujo -> Lista de plantillas](./media/learning-create-a-flow/template-list.png)

## <a name="choose-a-template"></a>Elegir una plantilla
La **búsqueda de datos adjuntos** en el correo electrónico puede ser una tarea larga y tediosa, y este flujo ahorra tiempo, ya que **almacena todos los datos adjuntos de los correos electrónico** en una carpeta de OneDrive.

Seleccione la plantilla **Guardar archivos adjuntos de correo electrónico de Office 365 en OneDrive para la Empresa**.

![Correo electrónico de Office 365](./media/learning-create-a-flow/office-365-email.png)

## <a name="create-and-administer-a-flow"></a>Crear y administrar flujos
Esta es uno de las plantillas de **un solo clic**, en las que solo debe responder preguntas relevantes **necesarias para crear el flujo**.

En el gráfico de la plantilla, hay una **descripción** de lo que hace plantilla **y de lo que necesita** para que funcione correctamente.

Se le pide que **especifique las credenciales** de los servicios **Office 365 Outlook** y **SharePoint**. Si utiliza ambos servicios con regularidad, ya habrá iniciado sesión en ellos.

![Guardar correo electrónico de Office 365](./media/learning-create-a-flow/save-flow-office-description.png)

1. Seleccione **Crear flujo**.
   
    ![Hacer clic en crear flujo](./media/learning-create-a-flow/click-create-flow.png)
   
    A continuación, verá los resultados. 
   
    ![Creación correcta](./media/learning-create-a-flow/create-successful.png)
   
    Flow ha **creado una carpeta** en OneDrive, en la que colocará automáticamente **todos los archivos adjuntos** que lleguen al correo electrónico del trabajo.
2. Abra **Mis flujos**.
   
    ![Abrir Mis flujos](./media/learning-create-a-flow/click-my-flows.png)
3. Seleccione el **flujo que acaba de crear** para ver cómo funciona.
   
    ![Selección del flujo](./media/learning-create-a-flow/click-the-flow.png)
4. Verá un **marca de verificación verde**, lo que indica que la **flujo funciona correctamente**. Seleccione **Correcto** para ver el historial de ejecución y los resultados.
   
    ![Flujo correcto](./media/learning-create-a-flow/flow-successful.png)
   
    **Todas las partes del flujo** funcionaban correctamente. 
   
    ![Historial de ejecución](./media/learning-create-a-flow/run-history.png)

## <a name="important-concepts-in-power-automate"></a>Conceptos importantes en Power Automate
Algunas cosas que deben saberse al crear flujos. Todos los flujos tiene dos partes principales: un **desencadenador** y **una o varias acciones**. 

El **desencadenador** es la acción inicial del flujo, que puede ser cosas como **Al llegar un correo electrónico nuevo** que tiene aquí, o bien **cuando se agrega un nuevo elemento**, si da la casualidad de que está usando SharePoint. También puede ser una programación fija, si usa un desencadenador denominado **Periodicidad**, que se explicara más adelante.

Las **acciones son las actividades** que desea que ocurran cuando **se invoca un desencadenador**. Por ejemplo, **Crear archivo** volverá a crear el archivo en OneDrive.

![Acciones en el correo electrónico nuevo](./media/learning-create-a-flow/trigger-or-action.png)

Otras acciones pueden ser: enviar un **correo electrónico**, publicar un **tweet**, iniciar un **aprobación**, etc.
Todas ellas entrarán en juego más adelante, cuando cree sus propios flujos desde cero. 

## <a name="next-lesson"></a>Siguiente lección
En la siguiente lección, echaremos un vistazo a la aplicación móvil Power Automate y sus capacidades. 

