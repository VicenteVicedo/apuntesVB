# ApuntesVB
Apuntes Visual Basic desde cero.
## Índice
- [Variables y tipos de datos](#variables-y-tipos-de-datos)
  * [Ámbito de una variable](#-mbito-de-una-variable)
- [Operadores](#operadores)
- [Condicionales](#condicionales)
- [Bucles](#bucles)
- [Arrays](#arrays)
  * [Inicialización de un array](#inicializaci-n-de-un-array)
  * [Cómo recorrer un array](#c-mo-recorrer-un-array)
- [Funciones y subrutinas](#funciones-y-subrutinas)
  * [Paso por referencia y valor](#paso-por-referencia-y-valor)

## Variables y tipos de datos
Llamamos variables a un espacio de memoria que reservamos para almacenar un valor, y al que nos podremos referir mediante un nombre o etiqueta.
De esta forma podremos almacenar valores y trabajar con ellos, modificándolos, manipulándolos y realizando operaciones sobre ellos.
#### Tipos de datos
Dependiendo del dato que queramos almacenar, elegiremos el tipo de variable más adecuado para ello. Los básicos y más frecuentes en Visual Basic son los siguientes:
 - **Integer** (entero): Podremos almacenar valores numéricos enteros. Por ejemplo una edad o un año.
 - **Single** (decimal): Nos servirá para almacenar valores con parte decimal. Calificaciones, alturas...
 - **Booleano**: Con los tipos booleanos podremos representar las variables que solamente puedan tomar los valores verdadero o falso. Si un valor existe en un conjunto concreto, si una persona es mayor de edad, si posee carnet de conducir...
 - **Char** (caracter): Empleado para almacenar una única letra (por ejemplo, la letra de un DNI).
 - **String** (cadena de caracteres): Empleado para almacenar varias letras que forman una palabra o frase, por ejemplo lo que ponemos en un cuadro de búsqueda de cualquier web.
 
En caso de ser necesario algún otro tipo de dato, se puede consultar de la documentación oficial.
https://docs.microsoft.com/en-us/dotnet/visual-basic/language-reference/data-types/
#### Cómo inicializar una variable
Actualmente, Visual Basic nos ofrece varias formas para inicializar una variable.
- Especificando el tipo:
```vb
Dim edad As Integer
edad = 18

Dim esMayorDeEdad As Boolean
esMayorDeEdad = True

Dim nota, altura as Single, nombre as String
altura = 1.83
nombre = "Jon García"
```
Se puede observar que para cada variable, decimos de qué tipo es (As Integer, As Boolean...).
- Por inferencia de tipo
```vb
Dim edad = 18
Dim esMayorDeEdad = True
Dim nota = 9.7, altura = 1.83, nombre = "Jon García"
```
En este caso no especificamos de qué tipo es cada variable ya que se puede **inferir** a partir del valor al cual son inicializadas.
#### Ámbito de una variable
A veces es posible que obtengamos un error del tipo *"uso de un variable que no ha sido declarada"*, sin embargo, sí que la hemos declarado. Esto se debe a que solo podemos acceder a la variable desde el mismo **ámbito** (o región) o un ámbito interior. Esto se entenderá mejor cuando se vean las partes de módulos, bucles, bloques condicionales... ya que son estos los que definen un nuevo ámbito.
## Operadores
Los operadores nos ayudarán a modificar el valor de las variables según nos convenga y a tomar decisiones según su valor. Los operadores básicos de Visual Basic son:
- ``` + ```: Suma dos números enteros o concatena dos cadenas.
```vb 
dim suma = 3 + 5
'Suma vale 8
dim cad1 = "cad" + "ena"
dim cad2 = "cad" & "ena"
'Tanto cad1 como cad2 almacenan el valor "cadena"
```
## Condicionales

## Bucles

## Arrays

#### Inicialización de un array

#### Cómo recorrer un array

## Funciones y subrutinas

#### Paso por referencia y valor

