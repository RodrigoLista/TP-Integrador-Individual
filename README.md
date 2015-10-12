# TP-Integrador-Individual
Rodrigo Lista k2051


•	Análisis Léxico

En 1994 se agrego al  estándar de C, incluida en C99, en donde se consideró que los dígrafos podían ser una alternativa más comprensible para 5 de los 9 trígrafos que ya existían. Los dígrafos se siguen utilizando en el lenguaje de C junto con los 4 trigrafos restantes.

Secuencia de Lexemas
Int    printf    (    const    char    *    ,    .    .     .     )     ;     int     main    (    void     )    {    int   _    [     :>    =    <%   -   !    .   0   }    ;    printf     (   “   %  d     %   d  “   ,   sizeof      _      -    sizeof   _   [    0     ]    ,    sizeof   (   char    )    +    0   [  _    ]    )    ;     }   

  Secuencia de tokens
Palabra reservada, identificador, carácter de puntuación,  palabra resevada, palabra reservada, operador, carácter de puntuación, carácter de puntuación, carácter de puntuación, carácter de puntuación, carácter de puntuación, carácter de puntuación ,palabra reservada, identificador, carácter de puntuación, palabra reservada, carácter de puntuación, carácter de puntuación, palabra reservada, identificador, operador, operador, carácter de puntuación, operador, operador, constante flotante, carácter de puntuación, carácter de puntuación, identificador, carácter de puntuación, carácter de puntuación, operador, carácter de conversión, operador, carácter de conversión, carácter de puntuación, carácter de puntuación, palabra reservada, identificador, operador, palabra reservada, identificador, operador constante entera, carácter de puntuación, palabra reservada, operador, palabra reservada, operador, constante entera, operador, identificador, carácter de puntuación, carácter de puntuación, carácter de puntuación

La UT es lexicamente correcta ya que todos los caracteres individualmente o combinados con otros, forman tokens.


•	Análisis Sintáctico

BNF de UT
-Declaración externa: definición de función
-Definición de función: especificador-de-declaración  declarador  lista de declaraciones
-Declarador-init:   declarador = Inicializador: expresión asignación    {lista-de-inicializadores}




Es sintácticamente correcta.
La primer linea contiene un prototipo de una función. Tiene el tipo que va a devolver que es una palabra reservada, después tiene el nombre de la función la cual esta correctamente escrita (empieza con una letra en minúscula). Después siguen los paréntesis, que me indican que argumentos va a recibir. Dentro de los paréntesis tengo el tipo char indicada con la palabra const como posfijo y el operador *. Const y char son palabras reservadas. Conts me indica que el tipo char no va a ser modificado. El operador * como sufijo de char me va a indicar que puede ser recursiva. Luego sigue un operador , (coma) y tres puntos (…) que me indican que la función puede llamarse con mas argumentos que parametros. Para poder utilizar los “…”, se necesita que al menos un parámetro este nombrado en la definición. La expresión finaliza con el carácter de puntuacion “;” (punto y coma).
En la segunda línea hay una función con el nombre main. Esta función debe estar si o si. Esta bien declarada, contiene el tipo del dato  que va a retornar la función, que es un int, una palabra reserva. Luego tengo el  operador () que me indica que argumentos va a recibir  y dentro de mismo, la palabra reservada void, que indica que no recibe ninguno. Y luego aparece el carácter de puntuación { que me va a indicar las sentencias que pertenecen a la función.
La tercera línea es la declaración de la variable _ como un arreglo de int al contener []. En este caso un [ y el dígrafo :> que se traduce como ]. Luego se lo inicializa asignándole -!.0 (operador aditivo, operador de negación y constante flotante). Esta sola asignación le da un tamaño al arreglo de una sola posición. Y por último el carácter de puntuación  punto y coma (;) que finaliza la línea.
La cuarta línea es la llamada a la función printf seguida de sus argumentos encerrados entre (). Los cuales comienzan con dos especificaciones de conversión %d%d y luego dos argumentos para imprimir. El primero es una resta entre la expresión sizeof_ que me devuelve el tamaño del arreglo y la expresión sizeof_[0] me devuelve el tamaño  del índice 0 del arreglo. Las dos expresiones me devuelven 4 que es el tamaño en Bytes del tipo de dato Int. Por lo que el resultante de la resta me da el valor 0. El segundo argumento es una suma entre la expresión sizeof (char), la que siempre devuelve 1, y la expresión 0[_] que me devuelve el valor -1. Por lo tanto el resultado que se imprime, es 0. Se cierra la línea con el carácter de puntuacion punto y coma (;)
Por ultimo el carácter de puntuación } que me indica el cierre de las sentencias pertenecientes a la función.


•	Análisis semántico

En la primer línea tengo la declaración del prototipo de la función printf con sus parámetros.
En la segunda línea tengo la llamada a la función main() la cual es buscada por el compilador para dar inicio a la ejecución del programa. Luego comienza sus proposiciones encerradas entre {}.
La tercer línea posee la declaración del identificador _ como un arreglo de int y posteriormente su inicialización con el valor 0, producto del operador ! que transforma .0 (tipo de dato float) en 0. Junto con la inicialización, le asigna su tamaño, que al tener un solo elemento, es 1.
En la cuarta línea esta el llamado a la función printf, la cual coincide con su prototipo indicado anteriormente. Esta imprime dos valores, resultantes uno de una resta y el otro de una suma. El primero es la resta de sizeof _ que devuelve el tamaño del identificador _ y sizeof _[0] que me devuelve el tamaño del vector en esa celda. Como el arreglo es de una celda, el minuendo y el sustraendo van a tener el mismo valor, dando como resultado el 0. El segundo valor que se imprime es la suma entre la expresión size(char), que me devuelve la constante entera 1, con la expresión 0[_], que me devuelve el valor -1, dando como resultado de la suma, la constante entera 0.
La salida del programa entonces seria dos dígitos 0.
