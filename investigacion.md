# Investigación de Métricas de Producto

## Introducción
Este documento recopila y presenta los hallazgos obtenidos tras investigar las métricas clave del producto "FinanApp", una aplicación de gestión financiera personal. La investigación se enfocó en identificar datos relevantes sobre usuarios activos y tasa de rebote, así como en comprender cómo estas métricas impactan en las decisiones de diseño.

## Fuentes de Datos
Los datos fueron recopilados de las siguientes fuentes, con su respectiva metodología y período de análisis:

1. **Google Analytics**
   - **Período de análisis**: 1 de enero de 2023 al 31 de diciembre de 2023.
   - **Métricas extraídas**:
     - Usuarios activos mensuales (MAU).
     - Tasa de rebote.
     - Duración promedio de la sesión.
   - **Metodología**: Se utilizaron informes estándar de Google Analytics, filtrando por el dominio de FinanApp.

2. **Encuestas a usuarios**
   - **Período de ejecución**: Febrero y agosto de 2023.
   - **Tamaño de la muestra**: 500 usuarios en cada encuesta.
   - **Preguntas clave**:
     - "¿Qué funcionalidad de FinanApp utilizas con más frecuencia?"
     - "¿Qué te motivó a dejar de usar la aplicación?"
   - **Metodología**: Encuestas enviadas vía correo electrónico a usuarios registrados.

3. **Datos internos de la aplicación**
   - **Período de análisis**: 1 de enero de 2023 al 31 de diciembre de 2023.
   - **Métricas extraídas**:
     - Número de transacciones registradas por usuario.
     - Frecuencia de uso de funcionalidades clave (ej. registro de gastos, visualización de informes).
   - **Metodología**: Consultas directas a la base de datos de la aplicación.

## Hallazgos Clave

### Usuarios Activos Mensuales (MAU)
Los usuarios activos mensuales muestran una tendencia creciente durante el primer semestre del año, alcanzando un pico en junio con **12,500 usuarios**. Sin embargo, a partir de julio, se observa una disminución progresiva, cerrando el año con **9,800 usuarios** en diciembre.

| Mes       | Usuarios Activos |
|-----------|------------------|
| Enero     | 10,200           |
| Febrero   | 10,800           |
| Marzo     | 11,500           |
| Abril     | 11,900           |
| Mayo      | 12,300           |
| Junio     | 12,500           |
| Julio     | 12,100           |
| Agosto    | 11,800           |
| Septiembre| 11,200           |
| Octubre   | 10,500           |
| Noviembre | 10,100           |
| Diciembre | 9,800            |

**Insight**: La disminución en la segunda mitad del año coincide con la falta de actualizaciones significativas en la aplicación y con comentarios de usuarios que mencionan "falta de novedades" o "funcionalidades repetitivas".

### Tasa de Rebote
La tasa de rebote promedio durante el año fue del **45%**, con variaciones significativas según el dispositivo utilizado:

| Dispositivo | Tasa de Rebote |
|-------------|----------------|
| Móvil       | 52%            |
| Tablet      | 38%            |
| Desktop     | 30%            |

**Insight**: La alta tasa de rebote en dispositivos móviles sugiere problemas de usabilidad o rendimiento en la versión móvil de la aplicación. Los usuarios en dispositivos móviles tienden a abandonar la aplicación en los primeros 10 segundos si no encuentran rápidamente lo que buscan.

### Duración Promedio de la Sesión
La duración promedio de la sesión fue de **3 minutos y 45 segundos**, con las siguientes diferencias por funcionalidad:

| Funcionalidad          | Duración Promedio |
|------------------------|-------------------|
| Registro de Gastos     | 2:30              |
| Visualización de Informes | 4:15           |
| Configuración de Presupuestos | 1:45        |

**Insight**: Los usuarios pasan más tiempo en la visualización de informes, lo que indica que esta funcionalidad es percibida como valiosa. Sin embargo, la baja duración en la configuración de presupuestos podría señalar una experiencia de usuario confusa o poco intuitiva.

### Resultados de Encuestas
Las encuestas revelaron los siguientes patrones:

1. **Funcionalidades más utilizadas**:
   - Registro de gastos (78% de los encuestados).
   - Visualización de informes mensuales (65% de los encuestados).
   - Configuración de alertas de gastos (42% de los encuestados).

2. **Razones para dejar de usar la aplicación**:
   - "Es difícil navegar entre las pantallas" (35% de los encuestados).
   - "No encuentro las funcionalidades que necesito" (28% de los encuestados).
   - "La aplicación es lenta" (22% de los encuestados).

**Insight**: Los problemas de navegación y la dificultad para encontrar funcionalidades clave son barreras significativas para la retención de usuarios.

## Conclusiones
Los hallazgos sugieren que, aunque FinanApp tiene un núcleo de usuarios activos, existen oportunidades claras para mejorar la retención y la experiencia del usuario. Las métricas de tasa de rebote y duración de la sesión indican que los usuarios enfrentan fricciones en la navegación y en el acceso a funcionalidades clave, especialmente en dispositivos móviles. Además, la disminución de usuarios activos en la segunda mitad del año sugiere que la falta de novedades o mejoras en la aplicación puede estar contribuyendo a la pérdida de interés.

Estos insights serán la base para el análisis de métricas y las recomendaciones de diseño que se desarrollarán en las siguientes fases.