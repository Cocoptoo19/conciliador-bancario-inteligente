# Conciliador bancario inteligente

Proyecto de automatización financiera desarrollado en Excel y Power Query para conciliar movimientos bancarios con registros contables, detectar excepciones y mantener una trazabilidad clara de cada revisión.

> Todos los datos incluidos son ficticios y se utilizan únicamente con fines formativos y de portfolio.

## Objetivo

Reducir el trabajo manual de conciliación mediante reglas reproducibles y auditables que clasifican cada movimiento como conciliado o excepcional.

El proyecto está orientado a tareas de tesorería y contabilidad, con una arquitectura preparada para incorporar asistencia de IA en el análisis de excepciones.

## Funcionalidades

- Importación de movimientos bancarios y contables desde archivos CSV.
- Normalización de referencias, descripciones, fechas e importes con Power Query.
- Conciliación por referencia e importe.
- Detección de diferencias de fecha.
- Identificación de operaciones pendientes, duplicadas y con importe distinto.
- Nivel de confianza basado en reglas.
- Acción inicial recomendada para cada excepción.
- Registro de responsable y resolución humana.
- Hoja específica para revisar excepciones.
- Configuración preparada para una futura integración de IA.

## Proceso

```text
CSV Banco + CSV Contabilidad
            ↓
      Power Query
            ↓
 Normalización de datos
            ↓
 Reglas de conciliación en Excel
            ↓
 Conciliados y excepciones
            ↓
 Revisión y resolución humana
```

## Resultados de la prueba

| Indicador | Resultado |
|---|---:|
| Movimientos bancarios analizados | 18 |
| Movimientos conciliados | 13 |
| Pendientes de banco | 2 |
| Duplicados detectados | 2 |
| Diferencias de importe | 1 |
| Excepciones totales | 5 |

## Reglas de conciliación

| Situación | Estado | Acción inicial |
|---|---|---|
| Referencia única e importe coincidente | Conciliado | Sin acción |
| Sin coincidencia de referencia | Pendiente banco | Solicitar soporte y registrar o reclasificar tras validación |
| Referencia duplicada en banco | Duplicado banco | Verificar extracto y autorización |
| Importe distinto | Diferencia importe | Comparar factura, banco y asiento |

## Estructura del libro

| Hoja | Finalidad |
|---|---|
| README | Guía de uso y descripción del proyecto |
| Banco | Movimientos bancarios normalizados |
| Contabilidad | Movimientos contables normalizados |
| Base_PQ | Resultado intermedio de Power Query |
| Conciliacion | Resultado operativo de la conciliación |
| Excepciones_IA | Operaciones que requieren revisión |
| Configuracion_IA | Parámetros de la futura integración de IA |
| Panel | Espacio para indicadores y seguimiento |

## Asistencia de IA

La versión publicada deja preparada la estructura para incorporar un modelo de IA en las excepciones no conciliadas.

Las columnas `Análisis IA`, `Confianza IA` y `Siguiente comprobación IA` están reservadas para esta futura integración.

Actualmente no hay un modelo de IA activo ni se presentan resultados simulados como respuestas reales de IA. La validación final corresponde siempre a una persona responsable.

## Uso

1. Actualizar los archivos CSV de Banco y Contabilidad.
2. Abrir el libro Excel.
3. Ir a **Datos → Actualizar todo**.
4. Revisar los movimientos no conciliados en `Excepciones_IA`.
5. Contrastar la evidencia disponible.
6. Registrar la decisión en `Resolución humana`.

## Tecnologías

- Microsoft Excel
- Power Query
- Lenguaje M
- Fórmulas de Excel
- CSV
- Diseño de arquitectura preparada para IA

## Capturas

![Conciliación bancaria](./01_conciliacion.png)

![Excepciones](./02_excepciones.png)

![Configuración de IA](./03_configuracion_ia.png)

## Autor

Proyecto desarrollado como parte de un itinerario de especialización en IA aplicada a Finanzas.
