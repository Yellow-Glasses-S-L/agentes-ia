# ⚡ Quick Start - Agentes IA Yellow Glasses

Guía rápida para empezar a usar los agentes en 5 minutos.

---

## 🎯 ¿Qué son estos agentes?

3 agentes de IA que automatizan el flujo de trabajo de proyectos en Yellow Glasses:

1. **Requirements Analyzer** 🔍: Analiza requisitos de clientes
2. **Project Planner** 📐: Crea plan de proyecto con tareas
3. **Airtable Sync** 🔄: Sube tareas a Airtable automáticamente

---

## 📖 Lectura Recomendada (15 min)

### Empieza aquí:
1. **[README.md](README.md)** (5 min) - Visión general del proyecto
2. **[yellow-glasses-context.md](context-and-docs/yellow-glasses-context.md)** (7 min) - Contexto de la empresa
3. **[ESTRUCTURA.md](ESTRUCTURA.md)** (3 min) - Navegación del proyecto

### Profundiza en los agentes:
4. **[agents/README.md](agents/README.md)** (2 min) - Índice de agentes
5. **Agente específico que necesites** (10 min cada uno)

---

## 🚀 Uso Rápido

### Opción 1: Usar un Agente Individual

#### Requirements Analyzer
```bash
1. Lee: agents/agent-requirements-analyzer.md
2. Carga contexto: context-and-docs/yellow-glasses-context.md
3. Proporciona input: Brief del cliente
4. Output: requirements-analysis.md
```

#### Project Planner
```bash
1. Lee: agents/agent-project-planner.md
2. Carga contexto: context-and-docs/yellow-glasses-context.md
3. Proporciona input: requirements-analysis.md
4. Output: [proyecto]-project-plan.md
```

#### Airtable Sync
```bash
1. Lee: agents/agent-airtable-sync.md
2. Carga contexto: context-and-docs/yellow-glasses-context.md
3. Proporciona input: [proyecto]-project-plan.md
4. Configura: PROJECT, PRODUCT, MES, etc.
5. Output: Tareas en Airtable (Proágil Sprints)
```

---

### Opción 2: Workflow Completo

```bash
┌─────────────────────────────────────────────────┐
│ 1. REQUIREMENTS ANALYZER                        │
│    Input: Brief del cliente                     │
│    Output: requirements-analysis.md             │
└──────────────────┬──────────────────────────────┘
                   ↓ [Revisar y validar]
┌─────────────────────────────────────────────────┐
│ 2. PROJECT PLANNER                              │
│    Input: requirements-analysis.md              │
│    Output: [proyecto]-project-plan.md           │
└──────────────────┬──────────────────────────────┘
                   ↓ [Revisar y ajustar]
┌─────────────────────────────────────────────────┐
│ 3. AIRTABLE SYNC                                │
│    Input: [proyecto]-project-plan.md            │
│    Output: Tareas en Airtable                   │
└─────────────────────────────────────────────────┘
```

---

## 🔑 Información Clave

### Stack de Yellow Glasses
- **Core**: WeWeb, Supabase, n8n, Webflow
- **Complementario**: Airtable, Make, Notion, Zapier

### Airtable (Proágil Sprints)
- **Base ID**: `app4qWRtlOzRXV7eY`
- **Tabla Tasks**: `tbltzD7GBLnWvVojk`
- **Campos clave**: Nombre, Status, Priority, Estimación, Projects, Products, Mes

### Formato de Tareas
```markdown
- [ ] **TASK-001**: Nombre de la tarea
  - **Description**: Descripción detallada
  - **Estimated Effort**: 4 hours
  - **Assigned Role**: Frontend Developer
  - **Dependencies**: None
  - **Acceptance Criteria**:
    - [ ] Criterio 1
    - [ ] Criterio 2
```

---

## 📂 Estructura de Carpetas

```
Agentes_IA/
├── README.md                 # 🏠 Inicio aquí
├── QUICK-START.md           # ⚡ Esta guía
├── ESTRUCTURA.md            # 🗺️  Navegación
│
├── agents/                  # 🤖 Especificaciones de agentes
│   ├── agent-requirements-analyzer.md
│   ├── agent-project-planner.md
│   └── agent-airtable-sync.md
│
└── context-and-docs/        # 📚 Contexto y documentación
    ├── yellow-glasses-context.md
    └── agents-integration-workflow.md
```

---

## 🎓 Casos de Uso Comunes

### Caso 1: Nuevo Proyecto de Cliente
```
1. Cliente envía brief por email
2. Usar Requirements Analyzer → genera requirements-analysis.md
3. Validar requisitos con el cliente
4. Usar Project Planner → genera [proyecto]-project-plan.md
5. Revisar estimaciones
6. Usar Airtable Sync → crea tareas en Proágil Sprints
7. Equipo empieza a trabajar desde Airtable
```

### Caso 2: Ampliar Proyecto Existente
```
1. Cliente solicita nuevas funcionalidades
2. Usar Requirements Analyzer con contexto del proyecto actual
3. Usar Project Planner para nuevas tareas
4. Usar Airtable Sync → añade tareas al proyecto existente
```

### Caso 3: Replantear un Proyecto
```
1. Usar Requirements Analyzer para re-analizar necesidades
2. Usar Project Planner para nuevo plan
3. Usar Airtable Sync → crea nuevas tareas o actualiza existentes
```

---

## ⚙️ Configuración Mínima

### Para Requirements Analyzer
- ✅ Acceso a Claude API (Sonnet 4.5 recomendado)
- ✅ Contexto de Yellow Glasses cargado

### Para Project Planner
- ✅ Acceso a Claude API
- ✅ Contexto de Yellow Glasses cargado
- ✅ Output del Requirements Analyzer

### Para Airtable Sync
- ✅ Personal Access Token de Airtable
- ✅ Base ID: `app4qWRtlOzRXV7eY`
- ✅ Acceso de escritura a tabla Tasks
- ✅ Output del Project Planner

---

## 🐛 Troubleshooting

### "No encuentro un archivo"
→ Revisa [ESTRUCTURA.md](ESTRUCTURA.md) para ver dónde está cada archivo

### "El agente no entiende el contexto de Yellow Glasses"
→ Asegúrate de cargar `yellow-glasses-context.md` en el system prompt

### "Las tareas no se crean en Airtable"
→ Verifica que tengas el Personal Access Token configurado
→ Confirma que el Project y Products existan en Airtable

### "El formato de tareas no es compatible"
→ Verifica que el Project Planner use el formato especificado
→ Revisa la sección "Consideraciones para Airtable Sync" en agent-project-planner.md

---

## 📞 Recursos Adicionales

### Documentación Completa
- **[README.md](README.md)**: Documentación completa del proyecto
- **[agents-integration-workflow.md](context-and-docs/agents-integration-workflow.md)**: Workflow integrado

### Contexto de Empresa
- **[yellow-glasses-context.md](context-and-docs/yellow-glasses-context.md)**: Todo sobre Yellow Glasses

### Navegación
- **[ESTRUCTURA.md](ESTRUCTURA.md)**: Mapa del proyecto y navegación

---

## ✅ Checklist de Inicio

Antes de usar los agentes, asegúrate de:

- [ ] He leído el README.md principal
- [ ] He leído yellow-glasses-context.md
- [ ] Entiendo el flujo de trabajo completo
- [ ] Tengo acceso a Claude API (si aplica)
- [ ] Tengo acceso a Airtable API (si aplica)
- [ ] He revisado la especificación del agente que voy a usar

---

## 🎯 Próximos Pasos

### Si eres nuevo:
1. ✅ Lee esta guía (ya lo estás haciendo)
2. 📖 Lee [README.md](README.md)
3. 🌍 Lee [yellow-glasses-context.md](context-and-docs/yellow-glasses-context.md)
4. 🤖 Explora el agente que necesites en `/agents/`

### Si vas a implementar:
1. 📋 Elige qué agente implementar primero
2. 📄 Lee su especificación completa
3. ⚙️ Configura las herramientas necesarias
4. 🧪 Prueba con un caso de uso real
5. 🔄 Itera y mejora según feedback

### Si tienes preguntas:
1. 🔍 Busca en la documentación
2. 📖 Revisa casos de uso en cada agente
3. 💬 Consulta con el equipo de Yellow Glasses

---

**¡Listo para empezar!** 🚀

Comienza con el [README.md](README.md) para una visión completa del proyecto.

---

**Última actualización**: 30 de Octubre, 2025
**Versión**: 1.0
**Mantenido por**: Yellow Glasses - COO (Víctor Bompart)
