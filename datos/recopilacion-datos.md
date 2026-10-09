# Recopilación de Datos de Métricas de Producto

## Introducción
Este documento detalla las fuentes de datos utilizadas para recopilar métricas clave del producto, específicamente **usuarios activos** y **tasa de rebote**. Los datos recopilados provienen de herramientas estándar de analítica web y registros internos del producto, y se presentan en formatos estructurados para facilitar su análisis posterior.

## Fuentes de Datos

### 1. Google Analytics
**Herramienta**: [Google Analytics 4](https://analytics.google.com)
**Métricas recopiladas**:
- **Usuarios activos**: Número de usuarios únicos que interactúan con el producto en un período de tiempo determinado.
- **Tasa de rebote**: Porcentaje de sesiones en las que el usuario abandonó el producto sin interactuar con ninguna otra página o funcionalidad.

**Datos recopilados**:
A continuación se presenta un extracto de datos históricos obtenidos de Google Analytics para el producto durante el último trimestre (enero - marzo 2024):

```csv
fecha,usuarios_activos,tasa_rebote
2024-01-01,1250,45.2%
2024-01-02,1320,42.1%
2024-01-03,1400,39.8%
2024-01-04,1380,40.5%
2024-01-05,1500,38.0%
2024-01-06,1600,35.5%
2024-01-07,1750,33.2%
2024-01-08,1800,32.0%
2024-01-09,1780,34.1%
2024-01-10,1900,31.5%
2024-02-01,2100,29.8%
2024-02-15,2300,28.5%
2024-03-01,2500,27.2%
2024-03-15,2700,25.9%
2024-03-31,2900,24.5%
```

**Notas**:
- Los datos de usuarios activos se obtuvieron utilizando el informe "Usuarios activos" en Google Analytics, filtrando por la propiedad del producto.
- La tasa de rebote se calculó como el porcentaje de sesiones con una sola interacción (sin eventos adicionales registrados).
- Se excluyeron las sesiones de bots y tráfico no humano utilizando filtros preconfigurados en Google Analytics.

### 2. Base de Datos Interna del Producto
**Herramienta**: PostgreSQL (tabla `user_sessions`)
**Métricas recopiladas**:
- **Sesiones activas**: Número de sesiones iniciadas por usuarios registrados.
- **Tiempo promedio en sesión**: Duración promedio de las sesiones de los usuarios.

**Datos recopilados**:
Se extrajo un conjunto de datos de la tabla `user_sessions` para el mismo período (enero - marzo 2024). La consulta SQL utilizada fue:

```sql
SELECT 
    DATE(created_at) AS fecha,
    COUNT(DISTINCT user_id) AS usuarios_activos,
    AVG(EXTRACT(EPOCH FROM (ended_at - created_at))) AS duracion_sesion_segundos
FROM 
    user_sessions
WHERE 
    created_at >= '2024-01-01' AND created_at <= '2024-03-31'
    AND ended_at IS NOT NULL
GROUP BY 
    DATE(created_at)
ORDER BY 
    fecha;
```

**Resultados**:

| Fecha       | Usuarios Activos | Duración Promedio de Sesión (segundos) |
|-------------|------------------|----------------------------------------|
| 2024-01-01  | 1200             | 120                                    |
| 2024-01-02  | 1300             | 135                                    |
| 2024-01-03  | 1400             | 150                                    |
| 2024-01-04  | 1350             | 140                                    |
| 2024-01-05  | 1500             | 160                                    |
| 2024-01-06  | 1600             | 180                                    |
| 2024-01-07  | 1750             | 200                                    |
| 2024-01-08  | 1800             | 210                                    |
| 2024-01-09  | 1780             | 195                                    |
| 2024-01-10  | 1900             | 220                                    |
| 2024-02-01  | 2100             | 240                                    |
| 2024-02-15  | 2300             | 260                                    |
| 2024-03-01  | 2500             | 280                                    |
| 2024-03-15  | 2700             | 300                                    |
| 2024-03-31  | 2900             | 320                                    |

**Notas**:
- Los datos de la base de datos interna solo incluyen usuarios registrados, por lo que el número de usuarios activos puede ser ligeramente inferior al reportado por Google Analytics.
- La duración promedio de la sesión se calculó excluyendo sesiones con duración cero (errores de registro).

### 3. Encuestas a Usuarios
**Herramienta**: Typeform
**Métricas recopiladas**:
- **Satisfacción del usuario**: Puntuación promedio en una escala del 1 al 5.
- **Razones de abandono**: Motivos declarados por los usuarios para abandonar el producto.

**Datos recopilados**:
Se realizaron encuestas a 500 usuarios activos durante el mes de marzo de 2024. A continuación se presentan los resultados resumidos:

```csv
pregunta,respuesta,porcentaje
"¿Cómo calificarías tu experiencia con el producto?",1,2%
"¿Cómo calificarías tu experiencia con el producto?",2,5%
"¿Cómo calificarías tu experiencia con el producto?",3,15%
"¿Cómo calificarías tu experiencia con el producto?",4,40%
"¿Cómo calificarías tu experiencia con el producto?",5,38%

"¿Cuál fue la razón principal para abandonar el producto?","Falta de funcionalidades",25%
"¿Cuál fue la razón principal para abandonar el producto?","Dificultad para navegar",35%
"¿Cuál fue la razón principal para abandonar el producto?","Problemas de rendimiento",20%
"¿Cuál fue la razón principal para abandonar el producto?","No encontré lo que buscaba",15%
"¿Cuál fue la razón principal para abandonar el producto?","Otra",5%
```

**Notas**:
- La encuesta se envió por correo electrónico a una muestra aleatoria de usuarios registrados.
- Las respuestas se agruparon por categorías para facilitar el análisis.

### 4. Herramientas de Monitoreo de Rendimiento
**Herramienta**: New Relic
**Métricas recopiladas**:
- **Tiempo de carga de página**: Tiempo promedio para que una página esté completamente cargada.
- **Errores por sesión**: Número promedio de errores registrados por sesión de usuario.

**Datos recopilados**:
Se monitoreó el rendimiento del producto durante el primer trimestre de 2024. Los datos clave son:

| Métrica                     | Valor Promedio |
|-----------------------------|----------------|
| Tiempo de carga de página   | 2.4 segundos   |
| Errores por sesión          | 0.3            |
| Disponibilidad del servicio | 99.95%         |

**Notas**:
- Los datos de rendimiento se recopilaron para las páginas más visitadas del producto.
- Se excluyeron los errores causados por problemas de red del usuario.

## Conclusiones Preliminares
- Los datos de **usuarios activos** muestran un crecimiento constante durante el trimestre, pasando de 1250 usuarios en enero a 2900 en marzo.
- La **tasa de rebote** ha disminuido progresivamente, lo que sugiere una mejora en la retención de usuarios.
- La **duración promedio de la sesión** ha aumentado, indicando que los usuarios pasan más tiempo interactuando con el producto.
- Las **encuestas a usuarios** revelan que la mayoría de los abandonos están relacionados con dificultades de navegación y falta de funcionalidades.

## Pasos Siguientes
1. **Validar los datos**: Cruzar las métricas de Google Analytics con los datos internos para asegurar consistencia.
2. **Identificar patrones**: Analizar los datos para identificar tendencias específicas en días o semanas con comportamientos atípicos.
3. **Correlacionar métricas**: Evaluar la relación entre la tasa de rebote y otras métricas como tiempo de carga de página y errores por sesión.

---
*Documento generado el 2024-04-05*