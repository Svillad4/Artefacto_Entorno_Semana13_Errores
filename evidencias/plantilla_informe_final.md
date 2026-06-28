# Informe final del artefacto

## 1. Nombre del proyecto

Artefacto del entorno: reporte rural automatico.

## 2. Problema contextual

Una comunidad rural necesita procesar miles de registros de producción agrícola en un archivo CSV que contiene información sobre leche, maíz, yuca, huevos y queso. El proyecto genera un reporte automatizado que calcula totales de producción por producto, ingresos estimados, identifica la finca con mayor ingreso y detecta registros con problemas de calidad. Este artefacto demuestra cómo utilizar un entorno de programación para resolver un problema real de análisis de datos rurales.

## 3. Entorno utilizado

- IDE o editor: Visual Studio Code
- Version de Python: 3.14.6
- Sistema operativo: Windows

## 4. Comandos ejecutados

```bash
python src/00_verificar_entorno.py
python src/01_explorar_datos.py
python src/02_reporte_rural_CON_ERRORES.py
python src/03_pruebas_reporte.py
```

## 5. Resultado obtenido

Se generó el archivo `output/reporte_rural.txt` que contiene un reporte completo con:

- **Resumen por producto**: muestra cantidad total e ingreso estimado para cada producto:
  - Huevo: 170,673 unidades, $90,090,821.00
  - Yuca: 231,078.41 kilos, $287,974,698.94
  - Maíz: 340,034.29 kilos, $525,637,563.97
  - Leche: 43,764.88 unidades, $101,568,372.66
  - Queso: 35,334.42 kilos, $285,393,394.47

- **Finca con mayor ingreso**: La Esperanza ($223,746,671.36)
- **Registros procesados**: 8,200 registros válidos, 5 registros inválidos

## 6. Errores corregidos

Se corrigieron 10 errores intencionales en el archivo `src/02_reporte_rural_CON_ERRORES.py`:

1. **Ruta del archivo CSV**: cambié "produccion.csv" a "produccion_rural.csv" (línea 27)
2. **Variable retornada**: cambié "return registros" a "return filas" (línea 42)
3. **Manejo de valores vacíos**: agregué try/except en convertir_a_numero (línea 48-50)
4. **Formato de fecha**: cambié "%d/%m/%Y" a "%Y-%m-%d" (línea 65)
5. **Nombre de columna**: cambié "cantida" a "cantidad" (línea 82)
6. **Validación de None**: agregué verificación "if cantidad is None or precio is None" (línea 82)
7. **Lógica de validación**: cambié cantidad negativa de válida a inválida (línea 85)
8. **Acumulación**: cambié "=" a "+=" en cantidad_total (línea 112)
9. **Variable en retorno**: cambié "finca_mas_alta" a "finca_mayor" (línea 135)
10. **Ruta y creación de carpeta**: cambié "outputs" a "output" y agregué mkdir() (línea 30 y 159)

## 7. Comparacion tecnica del entorno

| Criterio | Valoracion | Justificacion |
|---|---|---|
| Funcionalidad | 5/5 | El entorno permitió abrir el proyecto, editar código Python, ejecutar scripts, leer archivos CSV con 8,205 registros y generar reportes completos sin limitaciones. |
| Compatibilidad | 5/5 | Funcionó perfectamente en Windows con Python 3.14.6 usando solo librerías estándar (pathlib, csv, datetime). Sin dependencias externas. |
| Costo | 5/5 | Trabajé completamente con herramientas gratuitas: VS Code, Python oficial y Windows. Cero costos de licencia. |
| Facilidad de uso | 4/5 | VS Code proporciona terminal integrada, resaltado de sintaxis y mensajes de error claros. La terminal PowerShell integrada fue fácil de usar. |
| Rendimiento | 5/5 | El entorno procesó 8,205 registros, generó análisis de 5 productos y salida de reportes sin bloqueos ni demoras. |
| Depuracion | 5/5 | Los Traceback mostraban exactamente archivo, línea y tipo de error. Los tipos de error (FileNotFoundError, KeyError, NameError) fueron informativos y permitieron corregir rápidamente. |
| Organizacion | 5/5 | La estructura de carpetas (/data, /src, /output, /docs, /evidencias) fue clara e intuitiva. Facilitó encontrar archivos y comprender el flujo. |
| Recomendacion final | Sí | Este entorno es excelente para proyectos de análisis de datos rurales. Ofrece todo lo necesario: acceso a archivos, procesamiento de datos, generación de reportes, documentación y costo cero. |

## 8. Conclusion

| Criterio | Valoracion | Justificacion |
|---|---|---|
| Funcionalidad | 5/5 | El entorno permitió abrir el proyecto, editar código Python, ejecutar scripts, leer archivos CSV con 8,205 registros y generar reportes completos sin limitaciones. |
| Compatibilidad | 5/5 | Funcionó perfectamente en Windows con Python 3.14.6 usando solo librerías estándar (pathlib, csv, datetime). Sin dependencias externas. |
| Costo | 5/5 | Trabajé completamente con herramientas gratuitas: VS Code, Python oficial y Windows. Cero costos de licencia. |
| Facilidad de uso | 4/5 | VS Code proporciona terminal integrada, resaltado de sintaxis y mensajes de error claros. La terminal PowerShell integrada fue fácil de usar. |
| Rendimiento | 5/5 | El entorno procesó 8,205 registros, generó análisis de 5 productos y salida de reportes sin bloqueos ni demoras. |
| Depuracion | 5/5 | Los Traceback mostraban exactamente archivo, línea y tipo de error. Los tipos de error (FileNotFoundError, KeyError, NameError) fueron informativos y permitieron corregir rápidamente. |
| Organizacion | 5/5 | La estructura de carpetas (/data, /src, /output, /docs, /evidencias) fue clara e intuitiva. Facilitó encontrar archivos y comprender el flujo. |
| Recomendacion final | Sí | Este entorno es excelente para proyectos de análisis de datos rurales. Ofrece todo lo necesario: acceso a archivos, procesamiento de datos, generación de reportes, documentación y costo cero. |

## 8. Conclusion

Recomiendo ampliamente este entorno (VS Code + Python + Windows) para proyectos de análisis de datos rurales porque es funcional, gratuito, fácil de usar y capaz de procesar grandes volúmenes de datos. El ciclo de desarrollo es rápido: editar código, ejecutar en terminal, ver errores y corregir. Las pruebas automatizadas (como las 20 pruebas que pasaron) permiten verificar que todo funciona correctamente. Aprendí que los errores de programación son normales y que saber interpretarlos es más importante que evitarlos. Este artefacto demuestra que con las herramientas correctas es posible resolver problemas reales de análisis de datos sin invertir en software caro.

