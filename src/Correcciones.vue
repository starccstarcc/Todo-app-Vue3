- ¿Donda has visto que el orden de los componentes en VUE sea código JS y template? Normalmente es Template - Codigo - CSS
    - Configura eslint y prettier con la configuration de airbnb
    - Muy pocos commits, la idea es un commit por cada cosa nueva que hagamos o arreglemos.

App.vue:

- En la linea 18 items.completed === false. Cuando sea === false o === true tenemos una mejor forma de hacerlo.
=== CORREJIDO !! === - En el template, si el componente no tiene ningún slot, no hace falta que tenga etiqueta de apertura y cierre. Basta con <InputBar :items=“ítems” />
=== CORREJIDO !! === - El nombre items. ¿Que son los items? ¿Clientes, productos…?

Button.vue === CORREJIDO !! ===

- Busca que son los slots, lo puedes reemplazar por la prop msg.


Header.vue. === CORREJIDO !! ===

- El nombre es confuso, no veo que sea un Header si no toda la aplicación.
- Tienes una función que se llama handleSubmit que a su vez lo único que hacer es llamar a additems, ¿para que tenemos una función que solo llama a otra función?

TaskForm.vue


- === true o === false, tenemos mejores maneras de escribirlo
- Las clases que añades al button deberían ser parte del componente button y dependiendo de la prop que le pasaras que aplicara unos estilos u otros



Estilos: 

- El checkbutton y el texto de la tarea no están alineados
=== CORREJIDO !! === - El botón eliminar completados esta en un lugar muy aleatorio. O lo dejamos a la izquierda alineado con el listado o a la derecha o al centro pero no en un punto que no tenga sentido.
=== CORREJIDO !! === - El title de la pagina es ViteApp, podiamos cambiarlo por algo relacionado con la prueba

Funcionamiento: === CORREJIDO !! ===

- Si escribo una tarea, le doy a añadir y le vuelvo a dar añadir, aunque el texto esta en la barra de añadir tareas, se añade una tarea en blanco.
- Me permite añadir tareas en blanco.