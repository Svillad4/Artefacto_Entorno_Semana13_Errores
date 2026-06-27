# Bitacora tecnica de errores

## Datos del estudiante
Nombre: Santiago Villada
Grupo: No especificado
Fecha: 2026-06-27
Entorno utilizado: Visual Studio Code
Sistema operativo: Windows

## Registro de errores corregidos

| Nº | Error encontrado | Mensaje mostrado por Python | Linea o bloque | Causa identificada | Solucion aplicada | Como verifique que funciono |
|---:|---|---|---|---|---|---|
| 1 | Archivo CSV no encontrado | FileNotFoundError: No such file or directory: '.../data/produccion.csv' | Línea 27 | El nombre del archivo era incorrecto (produccion.csv en lugar de produccion_rural.csv) | Cambié "produccion.csv" a "produccion_rural.csv" en la ruta DATA_FILE | El programa ejecutó sin error FileNotFoundError |
| 2 | Variable no definida en retorno | NameError: name 'registros' is not defined | Línea 42 | La función leer_csv retornaba una variable que no existía | Cambié "return registros" a "return filas" | La función leer_csv retornó correctamente los datos |
| 3 | Conversión numérica sin validación | ValueError: could not convert string to float: '' | Línea 48-50 | La función convertir_a_numero no manejaba valores vacíos ni inválidos | Agregué try/except para capturar ValueError y TypeError, retornando None en caso de error | Los registros con valores vacíos se marcaron como inválidos |
| 4 | Formato de fecha incorrecto | Todos los registros rechazados por fecha inválida | Línea 65 | El formato de fecha esperado era "%d/%m/%Y" pero el CSV tenía "%Y-%m-%d" | Cambié el formato en fecha_valida a "%Y-%m-%d" | La validación de fechas funcionó y se aceptaron registros válidos |
| 5 | Nombre de columna incorrecto | KeyError: 'cantida' | Línea 82 | Se intentaba acceder a "cantida" pero la columna real se llama "cantidad" | Cambié "cantida" a "cantidad" en el acceso al diccionario | Se leyó correctamente la columna cantidad |
| 6 | Comparación de NoneType con int | TypeError: '<' not supported between instances of 'NoneType' and 'int' | Línea 82-85 | Cuando cantidad era None, se intentaba comparar None < 0 | Agregué validación "if cantidad is None or precio is None: invalidos.append()" al inicio | Los registros con valores None se marcaron correctamente como inválidos |
| 7 | Lógica de validación incorrecta | AssertionError: la limpieza dejó muy pocos registros válidos | Línea 85 | La rama "elif cantidad < 0" marcaba registros con cantidad negativa como válidos | Cambié la rama para marcar cantidad negativa como inválida | El número de registros válidos aumentó a 8200 |
| 8 | Acumulación incorrecta de cantidad | ValueError: max() iterable argument is empty | Línea 112 | Se asignaba "cantidad_total = cantidad" en lugar de acumular "cantidad_total += cantidad" | Cambié el operador de asignación "=" al operador de suma "+=". | El diccionario resumen contiene valores correctos por producto |
| 9 | Variable incorrecta en retorno | NameError: name 'finca_mas_alta' is not defined | Línea 135 | Se retornaba "finca_mas_alta" pero la variable se llama "finca_mayor" | Cambié "finca_mas_alta" a "finca_mayor" en el return | La función calcular_finca_mayor_ingreso retornó correctamente la finca |
| 10 | Ruta de carpeta incorrecta y creación de directorio | FileNotFoundError: No such file or directory: '.../outputs/reporte_rural.txt' | Línea 30 y 159 | La carpeta se llamaba "output" no "outputs", y además no se creaba automáticamente | Cambié "outputs" a "output" y agregué "OUTPUT_FILE.parent.mkdir(parents=True, exist_ok=True)" | El reporte se generó correctamente en output/reporte_rural.txt |

## Reflexion tecnica

1. ¿Cual fue el error mas dificil de corregir?
Comprendí que el error más difícil fue el de la acumulación incorrecta en la función `analizar_por_producto`. El programa ejecutaba sin errores de Python, pero la lógica era incorrecta: asignaba en lugar de acumular, por lo que solo guardaba el último valor. Esto causó que no hubiera registros de finca en el análisis, lo que llevó al error "max() iterable argument is empty". Requirió razonamiento lógico además de conocer la sintaxis.

2. ¿Que aprendiste sobre lectura de errores en la terminal?

Aprendí que los mensajes de error de Python son muy específicos y útiles. El Traceback muestra exactamente dónde falló el programa (archivo, línea y función), y el tipo de error (FileNotFoundError, KeyError, TypeError, etc.) indica qué tipo de problema buscar. También comprendí que algunos errores lógicos no generan excepciones pero causan fallos silenciosos en los datos, por lo que las pruebas automatizadas son esenciales.

3. ¿Por que es importante probar despues de cada cambio?

Es importante porque permite identificar inmediatamente si la corrección funcionó o si introdujo nuevos errores. Si corregía múltiples errores sin probar, no sabría cuál corregí correctamente. Las pruebas después de cada cambio crean un ciclo de retroalimentación rápido que acelera el proceso de depuración.

4. ¿Que ventaja tiene organizar el proyecto en carpetas?

La organización en carpetas facilita encontrar archivos rápidamente: datos en /data, código en /src, resultados en /output, documentación en /docs. Esto es especialmente útil en proyectos grandes. Además, la estructura clara permite que otras personas entiendan el proyecto sin explicaciones. En este caso, fue fácil identificar que el archivo CSV debería estar en /data y el reporte en /output.
