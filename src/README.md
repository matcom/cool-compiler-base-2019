# Código Fuente

Incluya en esta carpeta **todo** el código fuente que es necesario para compilar y/o ejecutar su compilador desde cero. 

**No incluya** archivos generados automáticamente, tales como binarios (e.g, `.exe`, `.pyc`), archivos auxiliares o archivos de logs, reportes, etc.

## Compilando su proyecto

Si es necesario compilar su proyecto, incluya todas las instrucciones necesarias en el archivo [`/src/makefile`](/src/makefile) que está en esta misma carpeta.
Durante la evaluación su proyecto se compilará ejecutando la siguiente secuencia:

```bash
$ cd source
$ make clean
$ make
```

## Ejecutando su proyecto

Incluya en el archivo [`/src/compile.sh`](/src/compile.sh) todas las instrucciones que hacen falta para lanzar su compilador. Recibirá como entrada un archivo con extensión `.cl` y debe generar como salida un archivo `.mips` cuyo nombre recibirá como argumento.

Para lanzar el compilador, se ejecutará la siguiente instrucción:

```bash
$ cd source
$ ./compile.sh <input.cl> <output.mips>
```
