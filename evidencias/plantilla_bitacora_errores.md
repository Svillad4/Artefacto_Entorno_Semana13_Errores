# Bitacora tecnica de errores

## Datos del estudiante

Nombre:
Grupo:
Fecha: 2026-06-25
Entorno utilizado: Visual Studio Code
Sistema operativo: Windows

## Registro de errores corregidos

| Nº | Error encontrado | Mensaje mostrado por Python | Linea o bloque | Causa identificada | Solucion aplicada | Como verifique que funciono |
|---:|---|---|---|---|---|---|
| 1 | Ruta de salida incorrecta (`outputs`) | FileNotFoundError al intentar escribir (si la carpeta no existe) | Bloque 1 (definición de OUTPUT_FILE) | Carpeta nombrada `outputs` pero la carpeta del repo es `output` | Cambié `OUTPUT_FILE` para usar `output` | Ejecuté el script y se creó `output/reporte_rural.txt` |
| 2 | Formato de fecha incorrecto | Error de parseo de fecha si se usa formato equivocado | Bloque 4 (`fecha_valida`) | Validación usaba `%d/%m/%Y`, el CSV usa `YYYY-MM-DD` | Ajusté `fecha_valida` a `%Y-%m-%d` | La validación de fechas pasó y no marcaron fechas válidas como inválidas |
| 3 | Limpieza de registros incompleta | TypeError: '<' not supported between instances of 'NoneType' and 'int' | Bloque 5 (`limpiar_registros`) | Conversiones a número devolvían `None` y luego se comparaban con enteros | Reescribí la lógica: usar `registro.get()`, convertir valores, validar `None` y negativos, separar `validos` e `invalidos` | Ejecuté el script; ya no aparece el TypeError y los conteos tienen sentido |
| 4 | Acumulación por producto incorrecta | Resultados numéricos incorrectos (lógica) | Bloque 6 (`analizar_por_producto`) | Se sobrescribía `cantidad_total` en vez de acumular | Cambié `resumen[producto]["cantidad_total"] = cantidad` por `+= cantidad` | Revisé `output/reporte_rural.txt` y los totales coinciden con la suma por producto |
| 5 | Variable mal nombrada en retorno | NameError potencial o retorno incorrecto | Bloque 7 (`calcular_finca_mayor_ingreso`) | Se retornaba `finca_mas_alta` en vez de `finca_mayor` | Corregí el nombre en el `return` | La función devolvió la finca correcta y el ingreso asociado |
| 6 | Carpeta de salida no creada antes de escribir | FileNotFoundError si la carpeta no existe | Bloque 8 (`generar_reporte`) | No se verificaba la existencia del directorio antes de escribir | Añadí `OUTPUT_FILE.parent.mkdir(parents=True, exist_ok=True)` antes de abrir el archivo | El archivo `output/reporte_rural.txt` se creó correctamente |

## Reflexion tecnica

1. ¿Cual fue el error mas dificil de corregir?

Pude identificar que el error más difícil fue la limpieza de registros, porque involucraba conversiones a número, valores nulos y varias validaciones encadenadas.

2. ¿Que aprendiste sobre lectura de errores en la terminal?

Aprendí que leer el traceback completo ayuda a encontrar el archivo y la línea exacta; eso facilita corregir el problema sin cambiar código innecesario.

3. ¿Por que es importante probar despues de cada cambio?

Entendí que probar después de cada cambio evita que un ajuste introduzca otros errores y confirma que la solución funciona.

4. ¿Que ventaja tiene organizar el proyecto en carpetas?

Comprendí que una estructura con `data`, `src`, `output`, `docs` y `evidencias` facilita ubicar archivos, ejecutar pruebas y recopilar evidencias.
