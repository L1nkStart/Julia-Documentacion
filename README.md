# Introducción a Julia

**Julia** es un lenguaje de programación de alto rendimiento diseñado para computación científica y numérica.  
Es fácil de usar, tiene una sintaxis similar a Python y ofrece una velocidad comparable a C o Fortran.  

**Características principales de Julia**:
- Sintaxis simple y amigable.
- Alto rendimiento (similar a C o Fortran).
- Soporte para computación paralela y distribuida.
- Interoperabilidad con Python, R y C.
- Tipado dinámico y estático.
- Biblioteca estándar rica y ecosistema en crecimiento.
  


#  Variables y Tipos de Datos

**Julia** es un lenguaje de tipado dinámico, aunque también permite definir tipos de datos explícitamente.

- Tipos de Datos Principales
- Números: Int, Float64, BigInt, Rational.
- Cadenas: String, con soporte Unicode.
- Booleanos: Bool, solo acepta true y false.
- Arreglos: Array, permite manipulación eficiente de datos.
- Diccionarios: Dict, estructura clave-valor.
- Tuplas: Tuple, colecciones inmutables.


```julia
x = 42           # Entero
y = 3.14         # Float
nombre = "Julia" # String
es_activo = true # Booleano
```




    true



# Estructuras de Control
Condicionales (if, else, elseif)



```julia
edad = 20
if edad >= 18
    println("Es mayor de edad")
else
    println("Es menor de edad")
end

```

    Es mayor de edad
    

# Bucles 
(for, while)


```julia
# Bucle for
for i in 1:5
    println("Iteración ", i)
end

# Bucle while
contador = 1
while contador <= 3
    println("Contador: ", contador)
    contador += 1
end
```

    Iteración 1
    Iteración 2
    Iteración 3
    Iteración 4
    Iteración 5
    Contador: 1
    Contador: 2
    Contador: 3
    

# Funciones
Las funciones en Julia pueden declararse de distintas maneras


```julia
# Definir una función tradicional
function suma(a, b)
    return a + b
end

# Definir una función en una sola línea
multiplica(a, b) = a * b

println(suma(5, 3))       # 8
println(multiplica(4, 2)) # 8

```

    8
    8
    

# Funciones Anónimas


```julia
potencia = (x, y) -> x^y
println(potencia(2, 3))  # 8
```

    8
    

# Arreglos y Matrices
Los arreglos en Julia son eficientes y permiten manipulación avanzada.

- Ejemplo de Arreglos



```julia
numeros = [1, 2, 3, 4, 5]
println(numeros[2])  # Accede al segundo elemento
push!(numeros, 6)   # Agrega un elemento al final

```

    2
    




    6-element Vector{Int64}:
     1
     2
     3
     4
     5
     6



- Ejemplo de Matrices


```julia
matriz = [1 2 3; 4 5 6; 7 8 9]
println(matriz[2,3])  # Elemento fila 2, columna 3

```

    6
    

# Estructuras de Datos
Julia tiene estructuras avanzadas como diccionarios y conjuntos.

- Diccionarios


```julia
diccionario = Dict("nombre" => "Juan", "edad" => 25)
println(diccionario["nombre"])  # Juan

```

    Juan
    

- Conjuntos


```julia
conjunto = Set([1, 2, 3, 3, 4])
println(conjunto)  # {1, 2, 3, 4}

```

    Set([4, 2, 3, 1])
    

# Módulos y Paquetes
Julia permite organizar código en módulos y usar paquetes externos.

- Ejemplo de Módulo



```julia
module Matematicas
export suma

function suma(a, b)
    return a + b
end
end
```

- Gestión de Paquetes

using Pkg
Pkg.add("Plots")  # Instalar paquete de gráficos


# Entrada y Salida (I/O)
Julia permite leer y escribir datos fácilmente.

- Entrada de Usuario



```julia
nombre = readline()
println("Hola, ", nombre)

```

- Lectura y Escritura de Archivos


```julia
# Escribir en un archivo
open("archivo.txt", "w") do archivo
    write(archivo, "Hola desde Julia!")
end

# Leer un archivo
contenido = read("archivo.txt", String)
println(contenido)

```

# Programación Orientada a Objetos (POO)
Julia no usa clases como Python, sino tipos de datos personalizados.

- Ejemplo de Tipos Personalizados


```julia
struct Persona
    nombre::String
    edad::Int
end

p = Persona("Ana", 30)
println(p.nombre)  # Ana

```

# Computación Paralela y en GPU
Julia tiene un fuerte soporte para ejecución paralela.

- Ejecución en múltiples núcleos


```julia
using Distributed
addprocs(4)  # Agregar 4 procesos

@distributed for i in 1:10
    println("Proceso $i ejecutado en $(myid())")
end

```

- Cálculo en GPU


```julia
using CUDA
a = CUDA.randn(10,10)  # Matriz en la GPU

```

# Machine Learning con Julia
Julia se usa en aprendizaje automático con Flux.jl.

- Ejemplo de Red Neuronal Simple


```julia
using Flux
modelo = Chain(Dense(2, 5, relu), Dense(5, 1, sigmoid))

```

# Conclusión
Julia es un lenguaje moderno, rápido y con múltiples aplicaciones.
Es ideal para cálculo numérico, inteligencia artificial y computación paralela.

--Fin
