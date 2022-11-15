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

Es una forma de tener acceso a datos a través del árbol de componentes sin tener que pasar props manualmente en cada nivel, usando datos globales.

Para esto tenemos un proveedor que envolverá a todos los componentes que serán los consumidores de nuestro contexto.

Fases:
1. Crear el contexto de nuestra aplicación.
2. Proveer nuestro contexto con los datos que queremos globales.
3. Consumir los datos desde cualquier parte de nuestra aplicación.

Es importante crear el contexto con createContext, ya que este nos regresará dos componentes: proveedor y consumidor.

Una vez ya tenemos nuestro proveedor envolviendo toda nuestra aplicación, ya podemos acceder a los datos desde cualquier componente hijo y olvidarnos de pasar props componente por componente.

Con esto evitas pasar props a todos los componentes. Puedes tener muchos componentes que consuman un solo contexto y también varios contextos.

Si el valor del contexto cambia, todos los componentes suscritos se re-renderizan y actualizarán su estado.

CLASE 17.
USECONTEXT.

El hook de contexto nos ayuda a acceder a datos globales de nuestro contexto, desde cualquier componente hijo, sin tener que pasar estos datos por props componente por componente.

Tiene la misma funcionalidad que el consumer de nuestro contexto, pero useContext también tiene una manera más sencilla de utilizar y una sintaxis mucho más clara.

Ahora solo nos queda utilizar este hook para acceder a nuestro contexto desde los componentes faltantes.

¿Cuándo se recomienda emplear React Context?
    Estado global.
    Tema.
    Configuración de la app.
    Autenticación de usuario.
    Configuración de usuario.
    Lenguaje preferido.
    Colección de servicios

CLASE 18.
PORTALES: TELETRANSPORTACION DE COMPONENTES.

Los portales nos permiten teletransportar componentes a otro nodo de HTML, y seguir comunicándose con otros componentes como si estuviera en el mismo nodo.

Se emplean en ocasiones donde los estilos CSS restringen los elementos. Por ejemplo, problemas de apilamiento z-index y desbordamiento overflow.

¿Para qué podemos usarlos?
    Modales
    Tooltips
    Menús flotantes
    Widgets

CLASE 19.
FORMULARIO PARA CREAR TO DO'S.

Algo muy importante al crear formularios es tener en cuenta que React funciona un poco diferente al HTML, ya que en HTML conservan naturalmente algún estado interno.

En React nosotros podemos mutar el estado de nuestros componentes con el hook de estado, un componente controlado es simplemente un componente en el que sus valores son controlados por React.


<!-- 
Esta es mi solución para el reto para cerrar el modal

en el css solo use un z-index: 999; para que el boton esté sobre cualquier otro elemento

En JS hice los siguiente

import React, { useContext } from 'react';
import { TodoContext } from '../../Context/TodoContext';
import './CreateTodoButton.css';

export const CreateTodoButton = () => {
  const { openModal, setOpenModal } = useContext(TodoContext);

  const handleClick = () => {
    setOpenModal(!openModal);
  };

  return (
    <>
      <button
        className="CreateTodoButton"
        type="submit"
        onClick={() => handleClick()}
      >
        {openModal ? 'x' : '+'}
      </button>
    </>
  );
};
 -->