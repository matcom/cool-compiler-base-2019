# COOL: Proyecto de Compilación

> Proyecto base para el compilador de 4to año en Ciencia de la Computación.

## Contenido

- [Generalidades](#generalidades)
- [Sobre el Lenguaje COOL](#sobre-el-lenguaje-cool)
- [Sobre el Compilador de COOL](#sobre-el-compilador-de-cool)
- [Sobre la Implementación del Compilador de COOL](#sobre-la-implementaci%C3%B3n-del-compilador-de-cool)
- [Sobre los Equipos de Desarrollo](#sobre-los-equipos-de-desarrollo)
- [Sobre los Materiales a Entregar](#sobre-los-materiales-a-entregar)
- [Sobre la Fecha de Entrega](#sobre-la-fecha-de-entrega)

## Generalidades

La evaluación de la asignatura Complementos de Compilación, inscrita en el programa del 4to año de la Licenciatura en Ciencia de la Computación de la Facultad de Matemática y Computación de la
Universidad de La Habana, consiste este curso en la implementación de un compilador completamente
funcional para el lenguaje _COOL_.

_COOL (Classroom Object-Oriented Language)_ es un pequeño lenguaje que puede ser implementado con un esfuerzo razonable en un semestre del curso. Aun así, _COOL_ mantiene muchas de las características de los lenguajes de programación modernos, incluyendo orientación a objetos, tipado estático y manejo automático de memoria.

### Sobre el Lenguaje COOL

Ud. podrá encontrar la especificación formal del lenguaje COOL en el documento _"COOL Language Reference Manual"_, que se distribuye junto con el presente texto.

### Sobre el Compilador de COOL

El compilador de COOL debe ser un archivo ejecutable de consola de nombre **coolc** (con la extensión
apropiada, por ejemplo: **.exe**) que reciba como primer y único argumento la ruta –relativa o absoluta–
a un archivo de texto plano con extensión **.cl**, el cual contendrá el código del programa a compilar.
En caso de que ocurran errores durante la operación del compilador, **coolc** deberá terminar con código
de salida (exit code) 1 y reportar a la salida estándar (standard output stream) lo que sigue...

    <línea_con_nombre_y_versión_del_compilador>
    <línea_con_copyright_para_el_compilador>
    <línea_de_error>_1
    ...
    <línea_de_error>_n

... donde `<línea_de_error>_i` tiene el siguiente formato:

    (<línea>,<columna>) - <tipo_de_error>: <texto_del_error>

Los campos `<línea>` y `<columna>` indican la ubicación del error en el fichero **.cl** procesado. En caso
de que la naturaleza del error sea tal que no pueda asociárselo a una línea y columna en el archivo de
código fuente, el valor de dichos campos debe ser 0.

El campo `<tipo_de_error>` será alguno entre:

- `CompilerError`: se reporta al detectar alguna anomalía con la entrada del compilador. Por ejemplo, si el fichero a compilar no existe.
- `LexicographicError`: errores detectados por el lexer.
- `SyntacticError`: errores detectados por el parser.
- `NameError`: se reporta al referenciar un `identificador` en un ámbito en el que no es visible.
- `TypeError`: se reporta al detectar un problema de tipos. Incluye:
    - incompatibilidad de tipos entre `rvalue` y `lvalue`,
    - operación no definida entre objetos de ciertos tipos, y
    - tipo referenciado pero no definido.
- `AttributeError`: se reporta cuando un atributo o método se referencia pero no está definido.
- `SemanticError`: cualquier otro error semántico.

En caso de que no ocurran errores durante la operación del compilador, **coolc** deberá terminar con código de salida 0, generar (o sobrescribir si ya existe) en la misma carpeta del archivo **.cl** procesado, y con el mismo nombre que éste, un archivo con extension **.MIPS** que pueda ser ejecutado con **spim**. Además, reportar a la salida estándar solamente lo siguiente:

    <línea_con_nombre_y_versión_del_compilador>
    <línea_con_copyright_para_el_compilador>

### Sobre la Implementación del Compilador de COOL

Para la implementación del compilador Ud. debe utilizar una herramienta generadora de analizadores
lexicográficos y sintácticos. Puede utilizar la que sea de su preferencia.

### Sobre los Equipos de Desarrollo

Para desarrollar el compilador del lenguaje COOL se trabajará en equipos de 2 o 3 integrantes.

### Sobre los Materiales a Entregar

Para la evaluación del proyecto Ud. debe entregar un informe en formato PDF que resuma de manera organizada y comprensible la arquitectura e implementación de su compilador.
El documento **NO** debe exceder las 5 cuartillas.
En él explicará en más detalle su solución a los problemas que, durante la implementación de cada una de las fases del proceso de compilación, hayan requerido de Ud. especial atención.

El informe debe incluir además una dirección a un repositorio git público con el código fuente de su compilador. Para la evaluación del proyecto, se clonará el repositorio y se procederá a su revisión. El proyecto debe contener un fichero `README.md` con las indicaciones para ejecutar su compilador, y los mecanismos pertinentes para garantizar su correcto funcionamiento en la máquina del revisor (instalación de dependencias, etc.).

### Sobre la Fecha de Entrega

Usted deberá entregar todos los materiales de su proyecto antes de la fecha siguiente:

> viernes, 31 de mayo de 2019
