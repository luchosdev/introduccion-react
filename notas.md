CLASE 13.
PERSISTENCIA DE DATOS CON LOCAL STORAGE.

Podemos hacer esta persistencia sin necesidad del back-end, usando la API de almacenamiento web llamada LOCAL STORAGE, que nos permite almacenar datos localmente en el navegador y se mantendrán aún si el recargamos la página o cerramos el navegador.

LocalStorage tiene varios métodos, como:

1. Guardar datos: setItem(nombre, dato)
2. Acceder a datos: getItem(nombre)
3. Borrar un dato: removeItem(nombre)
4. Eliminar todos los datos: clear(nombre)

LocalStorage solo puede guardar textos (solo strings), y no objetos, arreglos ni números; pero se puede utilizar los siguientes métodos JSON:

1. Convertir a texto: JSON.stringify()
2. Convertir a JavaScript: JSON.parse()

CLASE 14.
CUSTOM HOOK PARA LOCAL STORAGE.

Podemos crear hooks personalizados para, en este caso, guardar toda la lógica del localStorage.

Iniciando por que los custom hooks deben comenzar por "use", y debe tener parámetros, en este caso un nombre para el item en nuestro localStorage y un estado inicial.

También tenemos que regresar algunos datos para que nuestro hook sea funcional:

Los datos actuales de nuestro ítem en el localStorage.
Una función para actualizar los datos de este ítem.

CLASE 15.
MANEJO DE EFECTOS.

El hook de efecto en react nos permite ejecutar un pedazo de código cada vez que necesitemos, a lo largo de la vida de nuestro componente, también cuando se cumplan ciertas condiciones.

Ahora, el código dentro de nuestro hook de efecto no se ejecuta como el resto del código, se ejecutará inicialmente justo antes de hacer el renderizado del HTML que resulte de nuestro código de React.

El useEffect puede recibir dos argumentos:

1. Función que se ejecutará en cada fase del ciclo de vida de nuestro componente.
2. Las condiciones de cuándo debe ejecutarse esta función dentro de un arreglo, cada que se actualice cualquier dato que le pasemos a este arreglo, se volverá a ejecutar nuestra función.

El hook de efecto nos permite saber cuándo ya renderizó nuestra aplicación, y así mostrar un mensaje de cargando o alguna animación en lo que se completa la petición, esto lo hacemos con try y catch, mostrando si está cargando o hubo algún error.

CLASE 16.
REACT CONTEXT: ESTADO COMPARTIDO.

D
