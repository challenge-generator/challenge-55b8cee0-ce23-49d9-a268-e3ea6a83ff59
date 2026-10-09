# Análisis de Métricas de Producto

El equipo de diseño de soluciones necesita entender mejor cómo las métricas de producto informan las decisiones de diseño. El objetivo es rastrear y analizar KPIs básicos como usuarios activos y tasa de rebote, y comprender su relación con las funcionalidades del producto.

## Informacion General

| Campo | Valor |
|-------|-------|
| **Tema** | Identificación de métricas básicas de producto |
| **Nivel** | junior-l1 |
| **Tipo** | practical |
| **Tiempo estimado** | 3 horas |

## Fases del Reto

### Fase 0: Configuración del Proyecto

**Objetivo:** Obtener el proyecto base funcional enviando el Código Base a un asistente de IA, que lo analizará, corregirá errores y generará un ZIP listo para usar.

**Tiempo estimado:** 15-30 minutos

**Instrucciones:**

- Asegúrate de tener instalado para ejecutar el proyecto: Un IDE o editor de código.
- Copia todo el contenido del campo **Código Base** de este reto — incluyendo el texto de instrucciones que aparece al inicio.
- Abre un asistente de IA (Claude en claude.ai, ChatGPT o Gemini — se recomienda Claude), pega el contenido copiado en el chat y envíalo.
- El asistente analizará los archivos, corregirá errores y generará un archivo ZIP descargable. Descárgalo y extráelo en la carpeta donde quieras trabajar.
- Verifica que el proyecto arranca sin errores.

**Entregable:** El proyecto compila/arranca sin errores.

<details>
<summary>Pistas de conocimiento</summary>

- Copia el Código Base completo incluyendo el texto de instrucciones al inicio — esas instrucciones le indican al asistente exactamente qué hacer con los archivos.
- Si el asistente no genera el ZIP automáticamente al terminar el análisis, escríbele: "genera el ZIP ahora".
- Si el proyecto tiene errores al arrancar, comparte el mensaje de error con el mismo asistente para que lo corrija.

</details>

### Fase 1: Recopilación de Datos

**Objetivo:** Identificar y recopilar datos relevantes de métricas de producto.

**Tiempo estimado:** 1 hora

**Instrucciones:**

- Identifica las fuentes de datos disponibles para las métricas de producto.
- Recopila datos para los KPIs de usuarios activos y tasa de rebote.

**Entregable:** Documento con datos recopilados de usuarios activos y tasa de rebote.

<details>
<summary>Pistas de conocimiento</summary>

- Considera las diferentes fuentes de datos y cómo se relacionan con las métricas.
- Analiza la consistencia y la frecuencia de los datos.

</details>

### Fase 2: Análisis de Métricas

**Objetivo:** Analizar los datos recopilados y extraer insights relevantes.

**Tiempo estimado:** 1 hora

**Instrucciones:**

- Analiza los datos de usuarios activos y tasa de rebote.
- Identifica patrones y tendencias en los datos.

**Entregable:** Informe de análisis de métricas con insights y tendencias identificadas.

<details>
<summary>Pistas de conocimiento</summary>

- Utiliza herramientas de análisis para identificar patrones y tendencias.
- Considera cómo los datos pueden informar decisiones de diseño.

</details>

### Fase 3: Recomendaciones de Diseño

**Objetivo:** Proponer recomendaciones de diseño basadas en el análisis de métricas.

**Tiempo estimado:** 1 hora

**Instrucciones:**

- Basándote en el análisis de métricas, propone recomendaciones de diseño.
- Justifica tus recomendaciones con los insights extraídos.

**Entregable:** Documento con recomendaciones de diseño basadas en el análisis de métricas.

<details>
<summary>Pistas de conocimiento</summary>

- Considera cómo las métricas pueden impactar en la experiencia del usuario.
- Proporciona justificaciones claras para tus recomendaciones.

</details>

## Dimensiones Evaluadas

- **queEs**: ¿Qué son las métricas de producto y por qué son importantes?
- **paraQueSirve**: ¿Cómo informan las métricas de producto las decisiones de diseño?
- **comoSeUsa**: ¿Cómo se analizan y extraen insights de las métricas de producto?
- **erroresComunes**: ¿Cuáles son los errores comunes al analizar métricas de producto?
- **queDecisionesImplica**: ¿Qué decisiones de diseño pueden surgir del análisis de métricas de producto?

## Criterios de Evaluacion

- Recopilación de datos relevantes de métricas de producto.
- Análisis de datos y extracción de insights.
- Propuesta de recomendaciones de diseño basadas en el análisis de métricas.

## Como trabajar con un asistente de IA

Hay dos caminos, elegi uno:

- **AGENTS.md** (recomendado) — instrucciones nativas del repo. Abri esta carpeta con tu agente local (Claude Code, Cursor, Codex, Copilot, Gemini) y las carga solo. Sabe que archivos faltan y con que comando se verifica, y completa el scaffold escribiendo en disco.
- **PROMPT_MEJORA.md** — para copiar y pegar en un chat (claude.ai, ChatGPT). Devuelve un ZIP con el proyecto. Sirve si no tenes un agente en el IDE.

Ninguno de los dos resuelve las fases del reto: eso es tu trabajo.

## Verificacion

El proyecto esta listo para trabajar cuando este comando corre sin errores:

```bash
python3 -c "import json; json.load(open('design-tokens.json'))"
```

---

*Reto generado automaticamente por Challenge Generator - Pragma*
