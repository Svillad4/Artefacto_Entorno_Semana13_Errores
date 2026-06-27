# Bitacora tecnica de errores

## Datos del estudiante

Nombre: Santiago Villada
Grupo: 
Fecha: 2026-06-27
Entorno utilizado: Visual Studio Code
Sistema operativo: Windows

## Registro de errores corregidos

| Nº | Error encontrado | Mensaje mostrado por Python | Linea o bloque | Causa identificada | Solucion aplicada | Como verifique que funciono |
|---:|---|---|---|---|---|---|
| 1 | Ruta incorrecta del CSV | FileNotFoundError al abrir data/produccion.csv | Bloque de rutas | Se usaba el archivo equivocado | Cambié a data/produccion_rural.csv | El script leyó el CSV correctamente |
| 2 | Variable incorrecta en leer_csv | NameError o datos vacíos al retornar registros | Bloque de lectura | Devolvía variable inexistente | Retorné la lista `filas` | La función devolvió registros válidos |
| 3 | Nombre de columna incorrecto | KeyError `cantida` | Bloque de limpieza | Columna mal escrita en el CSV | Cambié a `cantidad` | Se procesó la columna sin error |
| 4 | Conversión numérica sin validación | ValueError al convertir valores vacíos o inválidos | Bloque de conversión | No se controlaba texto vació o no numérico | Añadí try/except y validé valores | La conversión se realizó sin excepción |
| 5 | Comparación con None | TypeError `None < 0` | Bloque de validación | Comparaba None antes de validar | Validé `None` antes de la comparación | Los registros inválidos se filtraron correctamente |
| 6 | Nombre de función incorrecto | NameError al llamar analizar_productos | Bloque principal | Llamada con nombre distinto | Cambié a `analizar_por_producto` | El flujo de ejecución avanzó correctamente |
| 7 | Multiplicación texto * número | TypeError al calcular ingreso total | Bloque de análisis | `precio` permanecía como cadena | Convertí precio a número antes de operar | El ingreso se calculó sin error |
| 8 | Carpeta de salida incorrecta | FileNotFoundError con outputs/ | Bloque de reporte | Ruta de salida mal escrita y carpeta faltante | Usé `output/` y creé la carpeta si no existía | El archivo se guardó en output exitosamente |

## Reflexion tecnica

1. ¿Cual fue el error mas dificil de corregir?

El error más difícil fue la ruta incorrecta del CSV, porque impedía que el programa iniciara y mostraba un fallo al abrir datos.

2. ¿Que aprendiste sobre lectura de errores en la terminal?

Aprendí que los mensajes de Python indican la línea y la causa del error, lo que ayuda a encontrar y corregir la falla rápido.

3. ¿Por que es importante probar despues de cada cambio?

Porque cada prueba confirma que la corrección funcionó y evita que aparezcan errores nuevos en otras partes.

4. ¿Que ventaja tiene organizar el proyecto en carpetas?

Organizar en carpetas facilita encontrar datos, código, informes y evidencias sin perder tiempo.
