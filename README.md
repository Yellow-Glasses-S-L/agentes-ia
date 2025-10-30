# Agentes IA - Yellow Glasses

Sistema de agentes de IA para optimizar el flujo de trabajo de Yellow Glasses, desde la captura de requisitos hasta la sincronización con Airtable.

---

## 📁 Estructura de Archivos

```
Agentes_IA/
├── README.md                      # Este archivo
├── agents/                        # 🤖 Especificaciones de los agentes
│   ├── agent-requirements-analyzer.md
│   ├── agent-project-planner.md
│   └── agent-airtable-sync.md
└── context-and-docs/              # 📚 Contexto y documentación
    ├── yellow-glasses-context.md
    └── agents-integration-workflow.md
```

---

## 🤖 Agentes Disponibles

### 1. Requirements Analyzer
**Archivo**: [agents/agent-requirements-analyzer.md](agents/agent-requirements-analyzer.md)

**Propósito**: Analizar y estructurar requisitos de proyectos de manera sistemática.

**Input**: Conversaciones con clientes, transcripciones de reuniones, briefs, emails
**Output**: `requirements-analysis.md` con análisis técnico y recomendaciones

**Características clave**:
- Extracción de requisitos funcionales y no funcionales
- Análisis técnico con stack no-code de Yellow Glasses
- Detección de ambigüedades y gaps
- Estimación inicial de esfuerzo

---

### 2. Project Planner
**Archivo**: [agents/agent-project-planner.md](agents/agent-project-planner.md)

**Propósito**: Convertir requisitos en plan de proyecto ejecutable con tareas detalladas.

**Input**: `requirements-analysis.md`
**Output**: `[nombre-proyecto]-project-plan.md` con fases, tareas y estimaciones

**Características clave**:
- Desglose WBS (Work Breakdown Structure)
- Estimaciones de esfuerzo realistas
- Gestión de dependencias entre tareas
- Compatible con estructura de Airtable

---

### 3. Airtable Sync
**Archivo**: [agents/agent-airtable-sync.md](agents/agent-airtable-sync.md)

**Propósito**: Sincronizar tareas del project-plan a Airtable (Base: Proágil Sprints).

**Input**: `[nombre-proyecto]-project-plan.md`
**Output**: Tareas creadas en Airtable

**Características clave**:
- Parseo inteligente del project-plan
- Mapeo a estructura real de Airtable
- Validación pre-sync con usuario
- Creación en batch (10 tareas por request)
- Manejo de errores y rate limiting

---

## 📚 Documentación y Contexto

### Yellow Glasses Context
**Archivo**: [context-and-docs/yellow-glasses-context.md](context-and-docs/yellow-glasses-context.md)

Contexto completo de la empresa:
- Misión, valores y filosofía
- Stack tecnológico (WeWeb, Supabase, n8n, Webflow)
- Metodología de trabajo
- Tipos de proyectos
- Uso de Airtable

**Todos los agentes deben cargar este contexto antes de ejecutarse.**

---

### Agents Integration Workflow
**Archivo**: [context-and-docs/agents-integration-workflow.md](context-and-docs/agents-integration-workflow.md)

Documentación del flujo integrado:
- Workflow completo de los 3 agentes
- Puntos de decisión humana
- Métricas de éxito
- Roadmap de evolución
- Stack técnico recomendado

---

## 🔄 Flujo de Trabajo

```
1️⃣ REQUIREMENTS ANALYZER
   📥 Input: Brief del cliente, notas de reunión
   📤 Output: requirements-analysis.md
   ↓
   [Revisión humana y validación]
   ↓

2️⃣ PROJECT PLANNER
   📥 Input: requirements-analysis.md
   📤 Output: [proyecto]-project-plan.md
   ↓
   [Revisión humana y ajustes]
   ↓

3️⃣ AIRTABLE SYNC
   📥 Input: [proyecto]-project-plan.md + configuración
   📤 Output: Tareas en Airtable Proágil Sprints
   ↓
   ✅ Tareas listas para ejecución
```

---

## 🚀 Cómo Usar los Agentes

### Opción 1: Claude API (Recomendado para Requirements y Planning)
1. Leer el archivo del agente específico
2. Cargar `yellow-glasses-context.md` como contexto
3. Crear system prompt con la especificación del agente
4. Ejecutar con el input correspondiente
5. Validar output generado

### Opción 2: n8n (Recomendado para Airtable Sync)
1. Crear workflow en n8n
2. Usar nodos de AI con Claude
3. Integrar con Airtable directamente
4. Configurar manejo de errores y retry logic

### Opción 3: Hybrid (Mejor práctica)
- **Requirements Analyzer**: Script con Claude API
- **Project Planner**: Script con Claude API
- **Airtable Sync**: Workflow de n8n con integración nativa a Airtable

---

## 📊 Estructura de Airtable (Proágil Sprints)

### Base ID
`app4qWRtlOzRXV7eY`

### Tablas Principales
- **Tasks** (`tbltzD7GBLnWvVojk`): Tareas de proyectos
- **Projects** (`tblaYBmcxJ2Kp9QY6`): Proyectos principales
- **Products** (`tblNUTxi4IzicjKD3`): Productos por proyecto
- **Sprint** (`tblngSGp8HV3TUNht`): Sprints semanales

### Campos Clave en Tasks
- **Nombre**: Título de la tarea
- **Status**: Plan, To-do, In progress, Waiting, Review, Done
- **Priority**: 0 (crítico), 1 (alto), 2 (medio), 3 (bajo)
- **Estimación**: Duración en formato h:mm
- **Projects**: Link a proyecto
- **Products**: Link a producto(s)
- **Assignee**: Colaborador asignado
- **Sprint**: Link a sprint
- **Mes**: 10 2025, 11 2025
- **Tipo**: Bugs, Improvement, Sync, Support, Proposal

---

## ⚙️ Configuración Requerida

### Variables de Entorno
```bash
# Airtable
AIRTABLE_API_KEY=your_personal_access_token
AIRTABLE_BASE_ID=app4qWRtlOzRXV7eY

# Claude API (si se usa)
ANTHROPIC_API_KEY=your_api_key
```

---

## 🎯 Mejores Prácticas

### Requirements Analyzer
- Proporcionar máximo contexto posible del cliente
- Incluir transcripciones completas de reuniones
- Especificar objetivos de negocio claramente

### Project Planner
- Validar que requirements-analysis.md esté completo
- Revisar estimaciones generadas vs. referencias de Yellow Glasses
- Ajustar prioridades según urgencia del cliente

### Airtable Sync
- Verificar que Project y Products existan en Airtable antes de sincronizar
- Confirmar resumen de tareas antes de crear
- Validar resultado en Airtable post-sync

---

## 📈 Métricas de Éxito

### Requirements Analyzer
- **Completitud**: % de requisitos sin clarificación adicional
- **Precisión**: % de requisitos sin cambios post-validación
- **Tiempo ahorrado**: vs. análisis manual

### Project Planner
- **Precisión de estimaciones**: Desviación % estimado vs. real
- **Completitud del plan**: % de tareas sin re-planificación
- **Tiempo ahorrado**: vs. planificación manual

### Airtable Sync
- **Tasa de éxito**: % de sincronizaciones sin errores
- **Precisión de mapeo**: % de tareas correctamente mapeadas
- **Tiempo ahorrado**: vs. carga manual

---

## 🛠️ Roadmap

### Fase 1: MVP (Actual)
- ✅ Agentes funcionando individualmente
- ✅ Estructura de Airtable mapeada
- ✅ Documentación completa

### Fase 2: Automatización
- ⏳ Workflow automatizado en n8n
- ⏳ Notificaciones automáticas
- ⏳ Dashboard de seguimiento

### Fase 3: Inteligencia
- ⏳ Aprendizaje de estimaciones históricas
- ⏳ Detección de patrones en requisitos
- ⏳ Sugerencias proactivas

### Fase 4: Escalabilidad
- ⏳ Multi-proyecto en paralelo
- ⏳ Templates inteligentes por tipo
- ⏳ Integración bidireccional con Airtable

---

## 💡 Soporte

Para dudas o mejoras sobre los agentes:
1. Revisar la documentación en `context-and-docs/`
2. Consultar casos de uso en cada archivo de agente
3. Verificar estructura de Airtable en `agent-airtable-sync.md`

---

## 📝 Changelog

### 2025-10-30
- ✅ Creación inicial de los 3 agentes
- ✅ Adaptación a estructura real de Airtable Proágil Sprints
- ✅ Documentación completa del contexto de Yellow Glasses
- ✅ Workflow de integración definido
- ✅ Organización en carpetas (agents/ y context-and-docs/)

---

**Última actualización**: 30 de Octubre, 2025
**Versión**: 1.0
**Mantenido por**: Yellow Glasses - COO (Víctor Bompart)
