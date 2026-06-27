# Matriz de comparacion tecnica del entorno

Completa esta tabla despues de terminar el artefacto.

| Criterio | Pregunta guia | Valoracion 1 a 5 | Justificacion tecnica |
|---|---|---:|---|
| Funcionalidad | ¿El entorno permitio abrir el proyecto, editar codigo, ejecutar scripts, leer CSV y generar reportes? | 5 | VS Code abrió el proyecto completo, permitió editar código Python con colores de sintaxis, ejecutar scripts desde terminal integrada, leyó exitosamente 8,205 registros del CSV y generó un reporte de texto estructurado sin limitaciones. |
| Compatibilidad | ¿Funciono con el equipo disponible, el sistema operativo y Python? | 5 | Funcionó perfectamente en Windows con Python 3.14.6 usando solo la librería estándar (pathlib, csv, datetime). No requirió instalación de paquetes externos ni tuvo problemas de compatibilidad. |
| Costo | ¿Se pudo trabajar con herramientas gratuitas o de bajo costo? | 5 | VS Code es gratuito y de código abierto, Python oficial es gratuito, Windows es el SO disponible. Costo total del proyecto: $0. Ningún software de pago fue necesario. |
| Facilidad de uso | ¿Fue facil encontrar terminal, archivos, errores y resultados? | 4 | VS Code integra todo: explorador de archivos en el lateral, editor en el centro, terminal integrada abajo. Los errores aparecer con Traceback exacto. Los resultados se generaban en output/. Único punto mejorable: requiere conocer comandos básicos de terminal. |
| Rendimiento | ¿El entorno pudo procesar miles de registros sin bloquearse? | 5 | Procesó 8,205 registros sin cualquier pausa, bloqueo o consumo excesivo de memoria. Generó análisis de 5 productos con cálculos de ingreso total instantáneamente. El programa completó en menos de 1 segundo. |
| Depuracion | ¿Los mensajes de error ayudaron a corregir el programa? | 5 | Cada error mostró tipo específico (FileNotFoundError, KeyError, NameError, ValueError, TypeError), línea exacta donde ocurrió, archivo involucrado y contexto. Los 10 errores fueron corregidos usando solo la información del Traceback. |
| Organizacion | ¿La estructura de carpetas facilito comprender el proyecto? | 5 | Las carpetas /data, /src, /output, /docs, /evidencias, /solo_docente están bien nombradas y separadas por función. Un nuevo usuario entiende inmediatamente dónde están datos, código, resultados y documentación. |
| Recomendacion final | ¿Recomendarias este entorno para proyectos similares? | 5 | Absolutamente sí. Para análisis de datos rurales o cualquier proyecto pequeño-mediano de procesamiento de CSV: VS Code + Python + Windows es la combinación ideal de funcionalidad, costo cero y facilidad de uso. Permite enfocarse en la lógica del programa sin luchas con herramientas. |
