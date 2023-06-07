# Agente-basado-en-utilidad-juegaDomin-
El agente toma decisiones de juego basándose en una función de utilidad, que incluye una estrategia básica para maximizar la puntuación en función de las fichas disponibles y la configuración actual del tablero. 

# El código proporcionado implementa un juego de dominó entre un jugador y un agente. Aquí se muestra cómo funciona:

-Se importan los módulos necesarios: random para barajar las fichas y itertools para generar todas las combinaciones posibles de fichas de dominó.

-Se define la función seleccionar_ficha_utilidad que evalúa la utilidad de cada ficha disponible para la computadora en función de su capacidad para encajar en el extremo derecho o izquierdo de la serpiente (estado actual del tablero). La función devuelve el índice de la ficha con la puntuación más alta.

-Se define la función turno que maneja los movimientos de fichas del jugador y del agente
.
-Se definen las listas de fichas, se barajan y se dividen entre el stock, las fichas del jugador y las fichas de la computadora.

-Se encuentra la ficha inicial de la serpiente (estado actual del tablero), esta debe ser la  ficha doble de mayor valor, ya sea (6,6) o la siguiente  y se la remueve de las fichas del jugador o del agente, dependiendo de quién la tenga.

-Se determina quién juega primero basándose en la cantidad de fichas de cada jugador, pues ya uno de ellos habrá puesto una ficha con el paso anterior.

-Se inicia el bucle principal del juego.

-En cada iteración del bucle, se muestra el estado actual del juego, incluyendo el stock, las fichas del jugador, las fichas del agente y las fichas ya jugadas en el tablero.

-Se comprueba si se cumple alguna de las condiciones de victoria: el jugador o el agente se quedan sin fichas o la serpiente cumple con las condiciones de serpiente ganadora.

-Se definen los extremos de la serpiente (los números en los extremos de las fichas de dominó).

-Si es el turno del jugador, se le solicita ingresar un comando. El jugador puede pasar su turno escribiendo "pass", robar una ficha del stock escribiendo "robar" o colocar una ficha escribiendo el número correspondiente a la ficha en su mano.

-Si el jugador coloca una ficha, se comprueba si es válida según los extremos de la serpiente (estado actual del juego) y se actualiza la serpiente y las fichas del jugador en consecuencia.

-Si es el turno del agente, se verifica si tiene fichas válidas para colocar. Si es así, se utiliza la función seleccionar_ficha_utilidad para seleccionar la mejor ficha según su utilidad. Luego, se comprueba si la ficha se puede colocar a la derecha o a la izquierda de la serpiente y se actualiza la serpiente y las fichas de la computadora en consecuencia.

-El juego continúa hasta que se cumpla una condición de victoria o empate.

# FUNCIÓN DE EVALUACIÓN 

Función de Evaluación: seleccionar_ficha_utilidad

# Entradas:

fichas_computadora: Conjunto de fichas disponibles para la computadora.
Serpiente: Matriz que representa el estado actual del tablero
Ubicación: Ubicación donde se debe colocar la ficha (derecha o izquierda).

# Salida:

índice max puntuacion: Índice de la ficha con la puntuación más alta. Si no hay fichas disponibles, devuelve None.

# Pasos:

Inicializar una lista puntuaciones para almacenar las puntuaciones de cada ficha disponible.

# Calcular la puntuación de cada ficha disponible:

Para cada ficha en fichas_computadora:

Verificar la ubicación requerida:

Si ubicacion == "derecha":

Obtener el extremo derecho de la serpiente.

Si ubicacion == "izquierda":

Obtener el extremo izquierdo de la serpiente.

Si la ubicación no es válida, agregar 0 a puntuaciones y continuar con la siguiente ficha.

Verificar si la ficha es compatible con el extremo:

Si el extremo está presente en la ficha o si el extremo es igual a la ficha invertida:

Calcular la puntuación de la ficha sumando los valores de la ficha.

Agregar la puntuación a puntuaciones.

De lo contrario, agregar 0 a  puntuaciones.

# Verificar si hay fichas disponibles:

Si la longitud de puntuaciones es mayor que 0:

Obtener el índice de la ficha con la puntuación más alta (indice_max_puntuacion).

Devolver indice_max_puntuacion.

De lo contrario, devolver None.

La función de evaluación seleccionar_ficha_utilidad toma como entrada las fichas disponibles, el estado actual de la serpiente y la ubicación requerida. Calcula la puntuación de cada ficha según su compatibilidad con el extremo correspondiente y devuelve el índice de la ficha con la puntuación más alta. Si no hay fichas disponibles, devuelve None.



