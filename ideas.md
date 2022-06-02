# Ideas


* Cita Libro: Estructuras de Datos en C++ trata sobre el estudio de las estructuras de datos dentro del marco de trabajo de los tipos abstractos de datos (TAD) y objetos, bajo la óptica del análisis, diseño de algoritmos y programación, realizando las implementaciones de los algoritmos en C++.

* Hay que empezar hablando de la abstracción: El exceso de detalles hace más difícil tratar con los problemas.Para concentrarnos en lo realmente importante,abstraemos el problema, eliminando todos los detalles innecesarios.
	* Tipos de abstracción: 
		* Funcional: abstrae una operación. Programación estructurada y modular. Uso de funciones. especificación e implementación. **Añadimos operaciones**.
		* De datos: Abstrae un tipo de dato. El uso que se puede hacer de este tipo. **Añadimos tipos de datos**. 

* ¿Cómo podemos modelar la abstracción de datos? Usando un modelo matemático: los TAD.
	* TAD: un modelo matemático para definir tipos de datos. Se define un tipo de datos que queremos que se comporte de una manera concreta. En ningún momento se dice la estructura de datos que se tiene que usar para la implementación. Tampoco se índica cómo debe ser los algoritmos que implementan las acciones que puede realizar el tipo. Dependiendo de la estructura de datos elegida para implementar los TAD los algoritmos pueden ser más o menos eficientes. 
		* Propiedad: Independencia. Cuando definimos una ADT,hay independencia de su implementación, tu podrías implementar esa Pila, con arrays, con listas ligadas,... dependiendo de cómo lo hagas tendrá un coste u otro coste.


* No es lo mismo tipo de datos, estructura de datos y TAD: http://informatica.uv.es/iiguia/AED/oldwww/2001_02/Teoria/Tema_10.pdf

	* Los datos son las propiedades o atributos (cualidades o cantidades) sobre hechos u objetos que procesa el ordenador. Un dato El tipo de datos, en un lenguaje de programación, define el conjunto de valores que una determinada variable puede tomar, así como las operaciones básicas sobre dicho conjunto. Definen cómo se representa la información y cómo se interpreta. Los tipos de datos constituyen un primer nivel de abstracción, ya que no se tiene en cuenta cómo se representa realmente la información sobre la memoria de la máquina, ni cómo se manipula. 

		Dos tipos: predefinidos en el lenguaje y definidos por el usuario.
		Dos tipos: Simples y cpmplejos. 

		A los tipos de datos le falta las operaciones.
	* Las estructuras de datos son agrupaciones de datos, quizás de distinta naturaleza(tipo), relacionados (conectados) entre sí de diversas formas y las operaciones definidas sobre esa agrupación. Las estructuras de datos se caracterizan por el tipo de los elementos de la estructura, las relaciones definidas sobre los elementos y las operaciones permitidas sobre la estructura. Operaciones típicas sobre estructuras de datos suelen ser: buscar y acceder a los elementos (por la posición que ocupan en la estructura o por la información que contienen), insertar o borrar elementos, modificar las relaciones entre los elementos, etc.
	* En el nivel más alto de abstracción estarían los tipos abstractos de datos, éstos se pueden ver como modelos matemáticos sobre los que se definen una serie de operaciones. En realidad son una formalización del concepto de dato que el programador considera adecuado para resolver el problema.El tipo abstracto de datos, al igual que las estructuras de datos, es independiente del lenguaje de programación, ya que un tipo abstracto de datos (en adelante TAD) es una colección de valores y de operaciones  que  se  definen  mediante  una  especificación  que  es  independiente  de  cualquier representación.

![](img/datos.png)

### Tipos Abstractos de Datos en C++: Clases

Una clase, en C++, es una estructura de datos que contiene, además de la información propia de un cierto elemento (igual que un registro), los procedimientos y funciones propias para manipular‘correctamente’ la información contenida en el registro.

Se definen dos apartados: apartado público, y apartado privado.
La declaración de una clase en un fichero .h (por ejemplo,fecha.h), y su implementación en un fichero .cpp asociado(por ejemplo, fecha.cpp).

----

Sacado de (1)

A la hora de crear un Tipo Abstracto de Datos, la ecuación a seguir es, es decir, determinar como es la **estructura de datos** y cuales son los **algoritmos de control** para manera los datos, en otras palabras, las **operaciones sobre los datos** que se pueden hacer, o interesa hacer, sobre la mencionada estructura de datos.

Cuando ya se tiene bien diseñado un Tipo Abstracto de Dato, el siguiente paso es decidir una implantación. Esto supone elegir algunas de las estructuras de datos que nos proporcione el lenguaje de programación utilizado para representar cada uno de los objetos abstractos y, por otro lado, escribir una rutina (Procedimiento o función) en tal lenguaje que simule el funcionamiento de cada una de las operaciones especificadas para el TAD.

La selección de las estructuras de datos determina la complejidad del algoritmo que implanta una operación y su elección es, por esta razón, de gran importancia.

------

Sacado de (2)

Una estructura de datos es una estrategia de almacenamiento en memoria de la información que se desea guardar. Muchos TADs se implementan utilizando estructuras de datos. Por ejemplo, los TADS pilas y colas pueden implementarse usando la estructura de datos de las listas enlazadas.



----
Sacado de (3)

Para representar el modelo matemático básico de un TAD se emplean estructuras de datos y las operaciones definidas en el modelo se representan mediante procedimientos. Por ejemplo, se podría definir el TAD número complejo como un objeto con dos componentes que son números reales y sobre el que se define las operaciones suma y producto de números complejos. En una definición de este tipo no importa si en un programa concreto se utiliza una estructura tipo registro (record en Pascal, structure en otros lenguajes, p.ej. C) con dos campos para representar los datos o bien una estructura tipo array con dos elementos. Desde el punto de vista formal ese tipo de información es irrelevante.

Así mismo, no es necesario conocer cómo se realizan las operaciones definidas formalmente, sólo importa qué hacen para poder usarlas correctamente.


---
 
TAD Fecha (Sacado de (3))

Dominio: Cualquier fecha válida.
Operaciones:

* Iniciar (Fecha)
* Recuperar() -> Fecha
* Comparar (Fecha) -> Lógico
* Imprimir ()
* Distancia (Fecha) -> Entero //Devuelve los días que han pasado a la fecha dada
* diaSemana() 
* diaAnyo()
* Dia() -> Entero //Devuel el dia
* Mes() -> Entero
* Año() -> Entero


Implementación = ¿Qué estructura de datos podemos usar para representar el dominio? Tendríamos muchas opciones:

* 3 enteros (dia,mes,año)
* dia (entero) mes (string) año(entero)
* ida desde el 1 de enero, año (entero)
* número de segundos que ha pasado desde 1 de enero 1970
* ...

Según la estructura de datos puede ser más fácil o más difícil implementar algunas de las operaciones. Y lo más importante la estructura de datos elegida puede influir en la eficiencia de los algoritmos con los que vamos a implementar las operaciones.

Implementación con C++

Vamos a usar POO. Vamos a crear una clase.

* La **parte privada** de la clase determina la estructura de datos interna de los objetos del tipo, y es la que limita el dominio. 
* La **parte pública** corresponde a las operaciones que se pueden usar externamente, y es completamente independiente (desde el punto de vista del usuario) de la parte privada. Se suele llamar también API (Application Programming Interface).
* Si tras el análisis del problema necesitamos usar métodos auxiliares que faciliten la implementación de las operaciones principales, se pueden poner en la **parte privada**. Por ejemplo esBisiesto.

Algunas consideraciones:

* Podemos cambiar la estructura de datos y los algortimos que la manipulan. Pero al no cambiar el especificación de las operaciones, será trasparente para el usuario que usa la clase.
* Obtenemos **protección**  intentar acceder a partes privadas de la clase produce errores de compilación. 
* La característica de no acceder o modificar los valores de los atributos directamente y utilizar métodos para ello lo llamamos encapsulamiento.
* Concepto de módulo - un conjunto de datos y operaciones fuertemente relacionadas que, externamente, se pueden ver como una unidad, y a las cuales se accede mediante una interfaz bien definida. En C++ la **declaración** de una calse se escribe en el fichero `fecha.h` y su implementación en un fichero .cpp asociado(por ejemplo, `fecha.cpp`).
