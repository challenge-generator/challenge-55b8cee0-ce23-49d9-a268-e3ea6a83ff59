# AGENTS.md

Instrucciones para el agente de IA que abra este repositorio (Claude Code, Cursor, Codex, Copilot, Gemini). Se cargan solas: no hay que pegar nada en ningun chat.

## Que es este repositorio

Es el codigo base de un reto de aprendizaje de Pragma: **Análisis de Métricas de Producto**.

| | |
|---|---|
| Tema | Identificación de métricas básicas de producto |
| Nivel | junior-l1 |
| Chapter | Diseño de Soluciones |
| Especialidad | Product Design |
| Stack | Markdown / Metodología de Diseño Centrado en Métricas |
| Patron arquitectonico | Estructura de Análisis de Producto con Enfoque en Diseño |
| Tiempo estimado | 3 horas |

## Receta del stack

Esqueleto obligatorio:

- `investigacion.md`
- `flujos/*.mmd`
- `especificacion-de-componentes.md`
- `design-tokens.json`

Dependencias:

- Plantilla de Markdown para análisis de métricas n/a
- Ejemplo de dataset de métricas de producto (CSV/JSON) n/a
- Guía de WCAG 2.2 para accesibilidad en documentación n/a

## Tu tarea

Dejar este conjunto de artefactos en estado **verificable**: que el comando de verificacion corra sin errores. Escribi los archivos en disco, en este repositorio. No generes ZIPs ni archivos adjuntos.

En orden:

1. Corre `python3 -c "import json; json.load(open('design-tokens.json'))"` y mira que falla.
2. Completa lo que falte de la lista de abajo: manifiesto de dependencias, punto de entrada, capa de interfaz y las capas del patron declarado.
3. Arregla SOLO los errores que impiden compilar o arrancar.
4. Volve a correr `python3 -c "import json; json.load(open('design-tokens.json'))"` hasta que pase.
5. Pará ahí.

## Regla dura: las fases son trabajo del humano

**PROHIBIDO implementar los entregables de las fases.** El valor del reto esta en que la persona los resuelva. Tu trabajo es que tenga un proyecto que arranca; el hueco pedagogico se queda como esta.

No resuelvas nada de esto:

- **Fase 1 — Recopilación de Datos**: Documento con datos recopilados de usuarios activos y tasa de rebote.
- **Fase 2 — Análisis de Métricas**: Informe de análisis de métricas con insights y tendencias identificadas.
- **Fase 3 — Recomendaciones de Diseño**: Documento con recomendaciones de diseño basadas en el análisis de métricas.

Distincion operativa:

- **Arreglar** (si): import faltante, tipo que no existe, dependencia sin declarar, error de sintaxis, archivo referenciado que no existe.
- **No tocar** (no): logica de negocio incompleta, validaciones ausentes, secretos hardcodeados, APIs deprecadas que funcionan, concurrencia insegura, patrones mejorables. Eso es lo que la persona tiene que encontrar.

## Lo que falta y tenes que completar

No se detectaron huecos: estan los archivos declarados, el boilerplate del stack y ninguna referencia quedo colgando. Igual corre el comando de verificacion — que los archivos existan no garantiza que compilen.

### Presentes (11)

- `datos/recopilacion-datos.md`
- `datos/fuentes-de-datos.md`
- `analisis/informe-analisis.md`
- `analisis/patrones-tendencias.md`
- `investigacion.md`
- `especificacion-de-componentes.md`
- `design-tokens.json`
- `README.md`
- `flujos/principal.mmd`
- `recomendaciones/recomendaciones-diseno.md`
- `recomendaciones/justificaciones.md`

### Capas del patron declarado

Cada una tiene que existir como directorio real con al menos un archivo. Codigo plano en la raiz no satisface el patron.

- `datos`
- `analisis`
- `recomendaciones`

## Verificacion

```bash
python3 -c "import json; json.load(open('design-tokens.json'))"
```

Ese comando pasando es la definicion de "terminado" para vos.

## Convenciones que tenes que respetar

- Un solo ecosistema: no declares librerias de otro lenguaje ni mezcles gestores de paquetes.
- Toda libreria que uses tiene que estar declarada en el manifiesto de dependencias.
- Todo import declarado tiene que usarse; todo tipo usado tiene que existir o venir de una dependencia declarada.
- El patron es **Estructura de Análisis de Producto con Enfoque en Diseño**: los contratos (interfaces, puertos) los define la capa interna y los implementa la externa, nunca al revés.
- Los archivos que crees llevan implementacion real, no stubs: sin `TODO`, sin cuerpos vacios, sin `// getters y setters`.

## Contexto del candidato

Sirve para calibrar el nivel del codigo, no para resolver las fases.

- Perfil: Chapter Diseño de soluciones, Especialidad Product Designer, Seniority Junior
- Brecha que el reto ataca: Comprende y ha rastreado KPIs básicos de producto (ej. usuarios activos, tasa de rebote) e identifica su relación con las funcionalidades.
- Mision: Candidata con formación en diseño de soluciones, enfocada en entender cómo los datos de producto informan decisiones de diseño.

---

*Generado por Challenge Generator — Pragma. `README.md` tiene el enunciado completo del reto para la persona. `PROMPT_MEJORA.md` es la variante para pegar en un chat, si se prefiere ese flujo.*
