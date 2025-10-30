# 📂 Estructura del Proyecto - Agentes IA Yellow Glasses

```
Agentes_IA/
│
├── 📄 README.md                                    # Índice principal del proyecto
├── 📄 ESTRUCTURA.md                                # Este archivo (guía visual)
│
├── 📁 agents/                                      # 🤖 AGENTES IA
│   ├── 📄 README.md                                # Índice de agentes
│   ├── 📄 agent-requirements-analyzer.md           # Agente 1: Análisis de requisitos
│   ├── 📄 agent-project-planner.md                 # Agente 2: Planificación de proyectos
│   └── 📄 agent-airtable-sync.md                   # Agente 3: Sincronización con Airtable
│
└── 📁 context-and-docs/                            # 📚 CONTEXTO Y DOCUMENTACIÓN
    ├── 📄 README.md                                # Índice de contexto
    ├── 📄 yellow-glasses-context.md                # Contexto de la empresa
    └── 📄 agents-integration-workflow.md           # Flujo integrado de agentes
```

---

## 🎯 Propósito de Cada Archivo

### 📁 Raíz del Proyecto

#### README.md
**Qué es**: Índice principal y guía de inicio rápido
**Para quién**: Cualquier persona que llegue al proyecto por primera vez
**Contenido clave**:
- Descripción general del proyecto
- Estructura de archivos
- Flujo de trabajo completo
- Cómo usar los agentes
- Configuración requerida
- Mejores prácticas

#### ESTRUCTURA.md (este archivo)
**Qué es**: Mapa visual y navegación del proyecto
**Para quién**: Usuarios que necesitan entender la organización
**Contenido clave**:
- Árbol de archivos
- Propósito de cada archivo
- Guía de navegación
- Orden de lectura recomendado

---

### 📁 agents/ - Especificaciones de Agentes

Esta carpeta contiene las **especificaciones completas** de cada agente.

#### agents/README.md
- Índice rápido de los 3 agentes
- Flujo de uso entre agentes
- Consideraciones de compatibilidad

#### agents/agent-requirements-analyzer.md
**Agente**: Requirements Analyzer
**Función**: Analizar y estructurar requisitos de proyectos
**Input**: Briefs, transcripciones, emails, notas
**Output**: `requirements-analysis.md`

#### agents/agent-project-planner.md
**Agente**: Project Planner
**Función**: Convertir requisitos en plan de proyecto ejecutable
**Input**: `requirements-analysis.md`
**Output**: `[proyecto]-project-plan.md`

#### agents/agent-airtable-sync.md
**Agente**: Airtable Sync
**Función**: Sincronizar tareas a Airtable (Proágil Sprints)
**Input**: `[proyecto]-project-plan.md`
**Output**: Tareas en Airtable

---

### 📁 context-and-docs/ - Contexto y Documentación

Esta carpeta contiene el **contexto de la empresa** y **documentación del workflow**.

#### context-and-docs/README.md
- Guía de uso de archivos de contexto
- Cuándo actualizar cada documento
- Integración con agentes

#### context-and-docs/yellow-glasses-context.md
**Qué es**: Contexto completo de Yellow Glasses
**Importancia**: **CRÍTICO** - Todos los agentes deben cargar este contexto
**Contenido clave**:
- Misión, valores, filosofía
- Stack tecnológico (WeWeb, Supabase, n8n, Webflow)
- Metodología de trabajo
- Gestión con Airtable
- Estándares de documentación

#### context-and-docs/agents-integration-workflow.md
**Qué es**: Documentación del flujo de trabajo integrado
**Importancia**: Guía para implementar el sistema completo
**Contenido clave**:
- Workflow de los 3 agentes
- Puntos de decisión humana
- Métricas de éxito
- Stack técnico recomendado
- Roadmap de evolución

---

## 🧭 Guías de Navegación

### Para Entender el Proyecto (Primera Vez)

1. **Empieza aquí** → `README.md` (raíz)
2. Lee el contexto → `context-and-docs/yellow-glasses-context.md`
3. Entiende el workflow → `context-and-docs/agents-integration-workflow.md`
4. Explora los agentes → `agents/README.md`

### Para Implementar un Agente Específico

1. Lee el contexto → `context-and-docs/yellow-glasses-context.md`
2. Lee el agente específico → `agents/agent-[nombre].md`
3. Revisa integración → `context-and-docs/agents-integration-workflow.md`
4. Implementa según especificación

### Para Actualizar Documentación

1. **Si cambia la empresa** → Actualizar `yellow-glasses-context.md`
2. **Si cambia el workflow** → Actualizar `agents-integration-workflow.md`
3. **Si cambia un agente** → Actualizar `agents/agent-[nombre].md`
4. **Si cambia la estructura** → Actualizar este archivo (ESTRUCTURA.md)

---

## 🔗 Relaciones entre Archivos

```
yellow-glasses-context.md
        ↓ (cargado por)
    ┌───┴────┬────────────┬───────────────┐
    ↓        ↓            ↓               ↓
Agente 1  Agente 2    Agente 3   Integration Workflow
    ↓        ↓            ↓
    └────────┴────────────┘
             ↓
     Workflow Completo
```

### Dependencias de Contexto

Todos los agentes **REQUIEREN**:
- ✅ `yellow-glasses-context.md` cargado en system prompt

Los agentes **SE COMUNICAN** entre sí:
- Requirements Analyzer → Project Planner (via `requirements-analysis.md`)
- Project Planner → Airtable Sync (via `[proyecto]-project-plan.md`)

El workflow completo **DOCUMENTA**:
- Integración de los 3 agentes
- Puntos de validación humana
- Métricas y mejoras

---

## 📊 Matriz de Responsabilidades

| Archivo | Crear Agente | Usar Agente | Entender Sistema | Actualizar Docs |
|---------|:------------:|:-----------:|:----------------:|:---------------:|
| `README.md` (raíz) | ✅ | ✅ | ✅ | ✅ |
| `ESTRUCTURA.md` | ✅ | ⚪ | ✅ | ⚪ |
| `agents/README.md` | ✅ | ✅ | ✅ | ⚪ |
| `agent-requirements-analyzer.md` | ✅ | ✅ | ✅ | ⚪ |
| `agent-project-planner.md` | ✅ | ✅ | ✅ | ⚪ |
| `agent-airtable-sync.md` | ✅ | ✅ | ✅ | ⚪ |
| `context-and-docs/README.md` | ✅ | ✅ | ✅ | ✅ |
| `yellow-glasses-context.md` | ✅ | ✅ | ✅ | ✅ |
| `agents-integration-workflow.md` | ✅ | ✅ | ✅ | ✅ |

**Leyenda**:
- ✅ = Archivo relevante para esta tarea
- ⚪ = Archivo no relevante para esta tarea

---

## 🎨 Convenciones de Organización

### Nombres de Archivos
- **Agentes**: `agent-[nombre-descriptivo].md`
- **Contexto**: `[nombre-descriptivo]-context.md`
- **Workflow**: `[nombre-descriptivo]-workflow.md`
- **Índices**: `README.md` en cada carpeta

### Estructura de Carpetas
- **`/agents/`**: Solo especificaciones de agentes
- **`/context-and-docs/`**: Contexto de empresa y documentación de workflow
- **Raíz**: Solo archivos de índice y estructura

### Formato de Documentación
- Markdown con GitHub Flavored Markdown
- Emojis para categorización visual
- Headers jerárquicos (H1 → H2 → H3)
- Code blocks con syntax highlighting
- Tablas para información estructurada

---

## 🔄 Flujo de Actualización

```
┌─────────────────────────────────────────────┐
│  Cambio en Yellow Glasses                   │
│  (stack, metodología, estructura)           │
└──────────────────┬──────────────────────────┘
                   ↓
        ┌──────────────────────┐
        │  Actualizar:         │
        │  yellow-glasses-     │
        │  context.md          │
        └──────────┬───────────┘
                   ↓
    ┌──────────────────────────────┐
    │  ¿Afecta a los agentes?      │
    └──────────┬───────────────────┘
         Sí ↙     ↘ No
           ↓       ↓
    ┌──────────┐  └─→ Fin
    │ Actualizar│
    │ agent-    │
    │ *.md      │
    └─────┬─────┘
          ↓
    ┌──────────────────┐
    │ ¿Afecta workflow?│
    └──────┬───────────┘
      Sí ↙   ↘ No
        ↓     ↓
  ┌──────────┐└─→ Fin
  │Actualizar│
  │workflow  │
  │.md       │
  └──────────┘
```

---

## 💾 Control de Versiones

Cada archivo de documentación debe incluir al final:

```markdown
---
**Última actualización**: DD de Mes, YYYY
**Versión**: X.Y
**Cambios**: Breve descripción
---
```

### Versionado Semántico
- **X** (Major): Cambios estructurales importantes
- **Y** (Minor): Actualizaciones de contenido, mejoras
- **Z** (Patch): Correcciones menores, typos

---

## 🚀 Próximos Pasos

### Si eres nuevo en el proyecto:
1. Lee `README.md` (raíz)
2. Lee `yellow-glasses-context.md`
3. Lee `agents-integration-workflow.md`
4. Explora los agentes específicos

### Si vas a implementar:
1. Lee el agente específico
2. Carga el contexto de Yellow Glasses
3. Sigue las especificaciones
4. Valida con casos de uso

### Si vas a mantener:
1. Revisa fechas de última actualización
2. Verifica que el contenido sigue vigente
3. Actualiza según cambios en la empresa
4. Documenta versiones

---

**Última actualización**: 30 de Octubre, 2025
**Versión**: 1.0
**Mantenido por**: Yellow Glasses - COO (Víctor Bompart)
