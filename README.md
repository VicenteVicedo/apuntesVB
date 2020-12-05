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

Podremos llamar a las variables como queramos, pero siempre debemos escoger nombres descriptivos, de forma que si cualquier otra persona lee nuestro código, pueda entenderlo sin especial complicación.
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
Actualmente, Visual Basic nos ofrece varias formas para inicializar una variable, siempre empleando la palabra reservada ```vb Dim```.
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
*Nota: en caso de que la opción Option Strict esté deshabilitada nos dejará usar una variable sin que haya sido previamente declarada. Aunque esto puede parecer más cómodo, se suele evitar este tipo de prácticas ya que complican la legilibidad del código. Esta opción se establece en la primera línea del código y toma el valor On/Off (Option Strict On/ Option Strict Off). Si no ponemos nada, la opción por defecto será Option Strict Off.
#### Ámbito de una variable
A veces es posible que obtengamos un error del tipo *"uso de un variable que no ha sido declarada"*, sin embargo, sí que la hemos declarado. Esto se debe a que solo podemos acceder a la variable desde el mismo **ámbito** (o región) o un ámbito interior. Esto se entenderá mejor cuando se vean las partes de módulos, bucles, bloques condicionales... ya que son estos los que definen un nuevo ámbito.
## Operadores
Los operadores nos ayudarán a modificar el valor de las variables según nos convenga y a tomar decisiones según su valor. Los operadores básicos de Visual Basic son:
- ``` + ```: Suma dos números enteros o concatena dos cadenas.
```vb 
Dim suma = 3 + 5
'Suma vale 8
Dim cad1 = "cad" + "ena"
'cad1 almacena el valor "cadena"
```
- ``` += ```: Simplifica la sintaxis cuando uno de los operandos de la suma es la misma variable donde se almacena el resultado.
```vb
Dim suma = 3
suma = suma + 5
'suma vale 8
```
Es equivalente a
```vb
Dim suma = 3
suma += 5
'suma vale 8
```
- ``` & ```: Es empleado para concatenar dos cadenas, por lo tanto, es equivalente al operador + (aunque lógicamente, no suma dos números).
```vb 
Dim cad2 = "cad" + "ena"
'cad2 almacena el valor "cadena"
```
- ``` +& ```: Análogo a +=.
```vb 
Dim cad2 = "cad"
cad2 &= "ena"
'cad2 almacena el valor "cadena"
```
El resto de operadores aritméticos se usan de igual forma: resta (-), multiplicación (\*), exponenciación (^), división (/), división de resultado entero (descartando resto) (\\). Al igual que pueden ser empleados junto al símbolo =: -=, \*=, =^, =\\.
Los operadores de comparación los veremos en la parte de condicionales.
## Condicionales
Los bloques condidicionales son los que nos permiten ejecutar una parte del código u otra, en función de las condiciones que establezcamos. Las sentencias condicionales fundamentales de Visual Basic son: If ... Then y Select (conocido en otros lenguajes de programación como Switch).
Las condiciones se estableceran mediante expresiones Booleanas, es decir, cualquier variable de tipo Booleano o una expresión lógica que podremos formar con operadores lógicos de comparación.
Los operadores de comparación básicos son:
* Igualdad (=)
```vb
Dim TrueSiSonIguales as Boolean
TrueSiSonIguales = 5 = 5
'La variable TrueSiSonIguales almacena el valor True
```
*Nota: en otros lenguajes este operador se expresa como ```==```, para ser diferenciado del operador de asignación que utilizamos al dar valor a una variable (```vb Dim valor = 288```). En Visual Basic estos dos operadores (asignación y comparación) se diferencian a partir del contexto donde se utilicen. Así, el código de antes habría quedado más claro y legible de la siguiente forma:*
```vb
Dim TrueSiSonIguales as Boolean
TrueSiSonIguales = (5 = 5)
'La variable TrueSiSonIguales almacena el valor True
```
*Así diferenciamos mejor el operador de asignación (primer =) del operador de comparación (segundo =).*
* Mayor que, mayor o igual que (>), (>=), menor que, menor o igual que (<), (>=):
```vb
Dim booleano1 = 3 < 3  'False
Dim booleano2 = 3 <= 3 'True
Dim booleano3 = 5 > 4  'True
Dim booleano4 = 6 >= 7 'False
```
Operadores lógicos And y Or
* And: se resuelve como True si las dos expresiones booleanas son True.
* Or: se resuelve como True si al menos una expresión booleana es True.
Ahora que ya sabemos qué es una expresión (o condición) lógica veremos como se aplican a los bloques condicionales.
* ```If (condición lógica) Then```: Se ejecutará solo si la condición lógica se evalua a **True**. En caso contrario se ejecutarán las sentencias del bloque **Else** (si lo hubiese) o Else If (si lo hubiese y además se cumpliese su condición):
```vb
If edad >= 67 Then
 Console.WriteLine("Está en la edad de jubilación")
Else If edad >= 18 Then
 Console.WriteLine("No está en la edad de jubilación pero sí que es mayor de edad")
Else
 Console.WriteLine("Ni está en la edad de jubilación, ni es mayor de edad")
End If
```
En cuanto una sentencia If o Else If se cumpla, el resto del bloque condicional dejará de ejecutarse. Si ningún bloque If o Else if se ejecuta, se ejecutará el bucle Else, en caso de que lo hubiese.
* ```Select Case (condición lógica) ```: si tenemos una sentencia If con muchos Else if anidados, esta puede ser simplificada sustituyéndola por un bloque Select Case:

```vb
Dim numDias As Integer
Select Case (numeroDeMes)
  Case 1, 3, 5, 7, 8, 10, 12
     numDias = 31
  Case 2
     numDias = 28
  Case Else
     numDias = 30
 End Select
```
*Nota: en este caso obviamos los años bisiestos y asumimos que la variable numeroDeMes siempre tendrá un valor correcto (entre 1 y 12).
## Bucles

## Arrays

#### Inicialización de un array

#### Cómo recorrer un array

## Funciones y subrutinas
```vb
Dim numDias As Integer
Select Case (numeroDeMes)
  Case 1, 3, 5, 7, 8, 10, 12
     numDias = 31
  Case 2
     numDias = 28
  Case Else
     numDias = 30
 End Select
```
#### Paso por referencia y valor

