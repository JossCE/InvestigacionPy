# INVESTIGACION INTRODUCCION A PYTHON

## PEP8
### ¿Qué es PEP8?

La PEP8 es una guía de las convenciones estilísticas a seguir para escribir código Python. Se trata de un conjunto de recomendaciones cuyo objetivo es ayudar a escribir código más legible y abarca desde cómo nombrar variables, al número máximo de caracteres que una línea debe tener.

**La guia PEP8 menciona algunas de las siguientes recomendaciones para el diseño de código:**
 - **Reglas de indentación:** Se recomienda indentar usando 4 espacios, dado que los espacios ocupan el mismo tamaño en casi todos los tipos de fuente y 4 es un número aceptable para la separación visual de los bloques.

    *Ejemplo*
    ~~~
     # Usando 4 espacios
        def es_par(num):
            if num % 2 == 0:
                return True
            return False
    ~~~

 - **Longitud de líneas:**
    - 79 caracteres por línea por defecto y para la librería estandar.
    - 72 caracteres por línea de comentarios o documentación.
    - 99 caracteres para equipos que acuerden utilizar líneas más largas pero la limitación de comentarios y documentación sigue siendo 72.
    - Cuando se pretenda hacer un salto de línea se utiliza el carácter \

 -  **Posición de los operadores:** Cuando se tienen muchos operadores en nuevas líneas, las líneas deben de comenzar con el operador.
   
    *Ejemplo*
    ~~~
     ejemplo # Mal
        patas_totales = (num_patas_gato +
                        num_patas_pato +
                        num_patas_perro)              
        # Bien
        patas_totales = (num_patas_gato
                        + num_patas_pato
                        + num_patas_perro)
    ~~~

 - **Posición de líneas en blanco:** Cuando se definen conceptos y lógica en Python, es relevante el uso de líneas en blanco a añadir.
    - **2 líneas en blanco:** rodeando a funciones de nivel principal y definición de clases.
    - **1 línea en blanco:** definición de métodos dentro de una clase.
    - **1 línea extra:** entre bloques lógicos de código diferentes.
    - **1 línea en blanco al final del fichero:** todos los módulos en Python deben de terminar con una línea en blanco al final de cada módulo si tienen contenido.

 - **Importaciones de código:**
    - El uso de import debe de ser en líneas separadas.
    - El orden de importación es: librería estándar, librerías de terceros, librerías propias o locales.
    - Las importaciones absolutas son los recomendados.
    - Los importaciones relativas solo pueden ser explícitas y preferiblemente simples y cortas.
    - Importaciones usando * (wildcard) deben de ser evitadas.
  
    *Ejemplo*
    ~~~
    # Mal
    import json, sys

    # Bien
    import json
    import sys

    # Bien
    from json import dump, load

    # importacion absoluta
    import pkg.funciones
    from pkg import funciones
    from pkg.funciones import mi_funcion

    # importacion relativa
    from . import funciones
    from .funciones import mi_funcion

    # evitar!
    from pkg import *
    ~~~

 - **Cadenas de caracteres:** Python soporta diferentes tipos de caracteres para crear cadenas de caracteres siendo simples o triples, comillas simples o dobles.
    - **Comillas simples o dobles:** para cadenas de caracteres de una línea o varias.
    - **Triples comillas dobles:** para cadenas de documentación y bloques de cadenas de caracteres.

    *Ejemplo*
    ~~~
    def mi_funcion():
    """Sección de documentación con triples comillas dobles"""
    pass

    a = "Ander's car"  # escapando ' al usar "
    cita = 'Iba por "la acera" con el coche'  # escapando " al usar '
    ~~~

 - **Espacios en blanco:** Los espacios en blanco en Python se utilizan para aclarar o remarcar partes del código.
    - **Añadir espacios:** entre elementos separados por comas, en los lados de una evaluación operacional, en una asignación o separando bloques de operaciones.
    - **Evitar espacios:** en slicings, entre los nombres de funciones y la llamada, entre las variables y el acceso interno usando [], operaciones logicamente unidas o en parentesis vacios.
    - **Comas finales:** El uso de comas al final de una variable debe de hacerse en una nueva línea, las comas al final de una variable crean tuplas, por tanto hacerlas explícitamente es mejor.

    *Ejemplo*
    ~~~~
    # Bien
    variable = ('123',)
    mi_funcion(param1,
            param2,
            )

    # Mal
    variable = '123',  # creará una tupla de forma implicita
    mi_funcion(param1, param2,)  # la ultima coma sobra
    ~~~~

  - **Convenciones de nombres:**
    - **Caracteres a evitar:** o, O, l y L (letra O y letra L) dado que se pueden confundir con un 0 o un 1 dependiendo del tipo de fuente usada.
    - **Caracteres ASCII:** se utilizan en la librería estándar siempre.
    - **Nombre de modulos y paquetes:** se escriben en minúsculas y se desaconseja el uso de barras bajas, manteniendo los nombres lo más cortos posibles.
    - **Nombrado de clases:** se usan el FormatoCapital, donde la primera letra de cada palabra es mayúscula.
    - **Nombres de tipos de variables:** en FormatoCapital.
    - **Excepciones:** igual que el de clases pero con el sufijo «Error».
    - **Nombres de variables y funciones:** se usan palabras en minúscula separadas por barras bajas.
    - **Métodos en clases:** el primer parámetro para métodos de instancia es self y para métodos de clase cls.
    - **Constantes:** en mayúsculas.

### ¿Para qué sirve?

Ayuda a escribir código en python correctamente, debido a que dos mismos códigos pueden realizar lo mismo funcionalmente, pero si no se siguen unas directrices estilísticas, se puede acabar teniendo un código muy difícil de leer. Los problemas más frecuentes suelen ser:
 - Líneas demasiado largas.
 - Nombres de variables poco explicativos.
 - Código mal comentado.
 - Uso incorrecto de espacios y líneas en blanco.
 - Código mal identado.

---

# Modulos y Paquetes

## Modulos

### ¿Qué son los Módulos en Python?

Un módulo es un archivo de Python cuyos objetos (funciones, clases, excepciones, etc.) pueden ser accedidos desde otro archivo. Se trata simplemente de una forma de organizar grandes códigos.

Podemos hacer que un módulo esté visible para cualquier archivo ubicándolo en la carpeta Lib dentro del directorio de instalación de Python (p. ej. C:\Python310\Lib).

*Ejemplo*

Un archivo aritmetica.py que contenga las siguientes definiciones.

    ~~~
    def sumar(a, b):
    return a + b

    def restar(a, b):
        return a - b

    def mult(a, b):
        return a * b

    def div(a, b):
        return a / b
    ~~~

Podemos acceder a ellas desde otro archivo de Python ubicado en la misma ruta importando el módulo.

~~~
from aritmetica import sumar

print(sumar(7, 5))
~~~

## Paquetes

### ¿Que son los Paquetes en Python?

Un paquete es una carpeta que contiene varios módulos. Permite acceder a diferentes modulos contenidos en la carpeta desde otro archivo.

Debe contener siempre un archivo * __init__.py* para que Python entienda que se trata de un paquete y no de una simple carpeta.

 *Ejemplo*

 ~~~
    matematica/
        |-- __init__.py
        |-- aritmetica.py
        |-- geometria.py
    
    from matematica import aritmetica

    print(aritmetica.sumar(7, 5))
 ~~~ 

### Diferencias entre Modulos y Paquetes
 - Un módulo en Python es un archivo que contiene definiciones y declaraciones de Python.
 - Un modulo debe contener funciones, variables y clases, así como declaraciones ejecutables.
 - Los módulos permiten organizar el código relacionado en un solo archivo,
 - Los paquetes permiten organizar los módulos en una estructura de directorios, lo que facilita la gestión y la importación del código.
 - Los paquetes se utilizan para estructurar proyectos grandes en módulos más pequeños y manejables.

---

## Entornos Virtuales en Python 

### ¿Qué son y para qué sirven los Entornos Virtuales en Python?

Un entorno virtual es un árbol de directorios que contiene archivos ejecutables de Python y otros archivos que indican que es un entorno virtual.
Los entornos virtuales se pueden describir como directorios de instalación aislados. Este aislamiento permite localizar la instalación de las dependencias de un proyecto.

### ¿Para que funcionan?

Permite tener para un proyecto determinado un conjunto de paquetes/librerías aislados de la instalación principal de Python en un sistema.

### Virtualenv

*virtualenv* es una herramienta que se utiliza para crear entornos Python aislados. 

### Lista de comandos en windows
 - Crear entorno virtual nuevo :

 ~~~
 C:\>python -m venv c:\ruta\al\entorno\virtual
 ~~~

 - Activar entorno virtual:

 ~~~
 C:\>c:\ruta\al\entorno\virtual\scripts\activate.bat
 ~~~

 - Desactivar entorno virtual: 

 ~~~
 $ deactivate
 ~~~

 - Eliminar entorno virtual:

 ~~~
 C:\>rmdir c:\ruta\al\entorno\virtual /s
 ~~~

 - Instalar nuevo paquete:

 ~~~
 $ pip install paquete
 ~~~

 - Eliminar un paquete:

 ~~~
 $ pip uninstall paquete
 ~~~

 - Listar paquetes instalados:

 ~~~
 $ pip list
 ~~~
 
 - Lista los paquetes en formato del archivo requirements.txt:

 ~~~
 $ pip freeze > requirements.txt
 ~~~

 - Instalar los paquetes del fichero requerements.txt:

 ~~~
 $ pip install -r requirements.txt
 ~~~

*Ejemplo* 

~~~
# Nos situamos en nuestro home o donde queramos tener el entorno virtual
cd ~

# Creamos el entorno de ejemplo
python3 -m venv entorno-ejemplo

# Limpiamos la variable de entorno $PYTHONPATH para no depender de paquetes globales
export PYTHONPATH=.

# Nos situamos en nuestro home o donde tengamos el entorno virtual
cd ~

# Activamos el entorno con un script que se genera dentro del entorno
source entorno-ejemplo/bin/activate

python --version

# Instalar paquetes con pip cuando tienes el entorno virtual activo
pip install numpy

deactivate
~~~

### PyPi

**py.pi** o *the Python Package Index* es una herramientas de Python que funciona como un repositorio de software para el lenguaje de programación. En esta plataforma se encuentran paquetes de dependencias y otras herramientas.

En esta plataforma, al igual que cualquier otro repositorio de código, te permite crear una cuenta de usuario para poder agregar nuevos paquetes, buscarlos o guardarlos para utilizarlos después en la escritura de códigos.

Un *ejemplo* de ello es el paquete de instalación de **pip**. El cual se puede buscar sin haberse registrado o ingresado a una cuenta.






