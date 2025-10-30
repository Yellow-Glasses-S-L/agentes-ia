# Yellow Glasses - Contexto Operativo

## 🌍 Sobre la Empresa

Yellow Glasses es una empresa especializada en estrategia, innovación y tecnología no-code/low-code.

### Misión
Ayudar a empresas y equipos a optimizar procesos, automatizar operaciones y diseñar soluciones digitales sin depender de programación tradicional.

### Enfoque
Combina visión estratégica, creatividad tecnológica y ejecución ágil, utilizando herramientas de automatización, inteligencia artificial aplicada y diseño de experiencias de usuario.

### Valores Core
- **Innovación práctica**: aplicar tecnología con propósito, no por moda
- **Transparencia y co-creación** con los clientes
- **Formación y empoderamiento**: enseñar a los equipos a usar las herramientas implementadas
- **Mentalidad "Yellow"**: optimismo crítico, enfoque humano y diseño funcional

---

## 🧭 Víctor Bompart - COO (Chief Operating Officer)

### Responsabilidades
- Definir e implementar procesos operativos, asegurando eficiencia y escalabilidad
- Supervisar la gestión de proyectos con entregas de alta calidad alineadas a la visión estratégica
- Diseñar y optimizar el sistema interno de automatización y gestión
- Impulsar la adopción de IA y automatización avanzada (interna y para clientes)
- Coordinar equipos multidisciplinares (producto, tech, estrategia, clientes)
- Medir desempeño operativo mediante KPIs: eficiencia, margen, satisfacción del cliente, tiempo de entrega

### Estilo de Liderazgo
- **Pensamiento sistémico**: ver la empresa como ecosistema interconectado
- **Enfoque crítico y constructivo**: optimización constante, evitando complacencia
- **Disrupción razonada**: soluciones fuera de lo convencional pero viables y sostenibles
- **Colaboración asertiva**: autonomía con alineamiento estratégico claro

---

## ⚙️ Servicios de Yellow Glasses

### Oferta Principal
1. **Consultoría estratégica** en innovación, operaciones y transformación digital
2. **Implementación no-code/low-code** de sistemas personalizados
3. **Diseño de sistemas internos** (CRM, ERPs ligeros, automatizaciones, dashboards)
4. **Capacitación y acompañamiento** para equipos en adopción de herramientas digitales
5. **Integración de IA aplicada**: asistentes internos, agentes autónomos, automatización inteligente

### Stack Tecnológico

#### Core Stack (Principal)
- **WeWeb**: Frontend/UI no-code
- **Supabase**: Backend as a Service / Base de datos
- **n8n**: Automatización y workflows
- **Webflow**: Websites y landing pages

#### Herramientas Complementarias
- **Notion**: Documentación y gestión de conocimiento
- **Airtable**: Gestión de proyectos y bases de datos relacionales
- **Make (Integromat)**: Automatizaciones complejas
- **Zapier**: Integraciones rápidas
- **Glide**: Apps móviles no-code
- **Softr**: Portales y aplicaciones cliente

#### IA y Automatización Avanzada
- Agentes autónomos personalizados
- Asistentes de IA para operaciones internas
- Integración de APIs de IA (Claude, GPT, etc.)

---

## 📊 Metodología de Trabajo

### Enfoque de Proyectos
- **Ágil adaptado** al contexto no-code
- **Iteraciones rápidas** con validación continua del cliente
- **Co-creación**: cliente como parte activa del proceso
- **Documentación viva**: actualizada y accesible para el equipo del cliente

### Filosofía Operativa
- **Build fast, iterate faster**: aprovechar la velocidad del no-code
- **Empoderamiento del cliente**: transferir conocimiento, no crear dependencia
- **Automatización primero**: antes de escalar personas, escalar sistemas
- **Medición continua**: decisiones basadas en datos, no en intuición

---

## 🎯 Tipos de Proyectos Habituales

### Proyectos Internos
- Automatizaciones de procesos operativos
- Dashboards de gestión y KPIs
- Sistemas de gestión de clientes y proyectos
- Herramientas internas de productividad

### Proyectos para Clientes
- **Transformación digital**: migración de procesos manuales a automatizados
- **CRM/ERP personalizados**: sistemas a medida con no-code
- **Portales de cliente**: acceso a información, pedidos, soporte
- **Automatizaciones de negocio**: desde emails hasta procesos complejos multi-sistema
- **MVPs rápidos**: validación de ideas con desarrollo acelerado
- **Integraciones**: conectar herramientas existentes del cliente

---

## 🔄 Gestión con Airtable

Yellow Glasses utiliza Airtable como herramienta central de gestión de proyectos y operaciones.

### Estructura Típica
- **Base de Proyectos**: tracking de todos los proyectos activos
- **Base de Tareas**: desglose granular de trabajo
- **Base de Clientes**: información y relaciones
- **Base de Recursos**: personas, herramientas, assets

### Flujo de Información
1. **Requirements** → Captura de necesidades del cliente
2. **Planning** → Desglose en fases, tareas y estimaciones
3. **Execution** → Seguimiento en tiempo real
4. **Delivery** → Cierre y documentación

### Campos Clave en Airtable
- **PROJECT**: Proyecto padre al que pertenece la tarea
- **PRODUCT**: Producto o módulo específico (si aplica)
- **STATUS**: Estado actual (Plan, To-do, In Progress, Done, Blocked)
- **ASSIGNED TO**: Responsable de la tarea
- **MONTH**: Mes de ejecución (formato: "MM YYYY", ej: "10 2025", "11 2025")
- **PRIORITY**: Nivel de prioridad
- **ESTIMATE**: Estimación de esfuerzo
- **TAGS**: Etiquetas para categorización

---

## 🤖 Uso de Agentes IA en Yellow Glasses

Yellow Glasses ha implementado un sistema de 3 agentes de IA para automatizar y optimizar el flujo de trabajo desde la captura de requisitos hasta la ejecución en Airtable.

### Sistema de Agentes Implementados

#### 🔍 Requirements Analyzer (Azul)
**Propósito**: Analizar y estructurar requisitos de proyectos de manera sistemática.

**Input**: Conversaciones con clientes, transcripciones de reuniones, briefs, emails, notas de discovery
**Output**: `requirements-analysis.md` estructurado con análisis técnico

**Capacidades clave**:
- Extracción de requisitos funcionales y no funcionales
- Clasificación inteligente (Must Have, Should Have, Could Have)
- Análisis de viabilidad técnica con stack no-code de Yellow Glasses
- Detección de ambigüedades, contradicciones y gaps
- Estimación inicial de esfuerzo
- Identificación de oportunidades de valor agregado

**Cuándo usar**:
- Cliente comparte brief o necesidades del proyecto
- Después de reuniones de discovery
- Al recibir solicitudes de ampliación de proyectos existentes
- Cuando hay información dispersa que necesita consolidarse

---

#### 📐 Project Planner (Violeta)
**Propósito**: Convertir requisitos estructurados en planes de proyecto ejecutables.

**Input**: `requirements-analysis.md`
**Output**: `[nombre-proyecto]-project-plan.md` con fases, tareas y estimaciones

**Capacidades clave**:
- Diseño de arquitectura de proyecto (fases y milestones)
- Desglose WBS (Work Breakdown Structure)
- Estimaciones de esfuerzo realistas basadas en referencias de Yellow Glasses
- Gestión de dependencias entre tareas
- Asignación de roles por tarea
- Formato compatible con Airtable Sync

**Cuándo usar**:
- Después de validar requirements-analysis.md
- Al iniciar la planificación de un proyecto aprobado
- Para replantear proyectos existentes
- Cuando se necesita estimar esfuerzo y recursos

**Fases típicas generadas**:
1. Discovery & Setup (Prioridad 0-1)
2. Core Development (Prioridad 1-2)
3. Integrations & Automation (Prioridad 2)
4. Testing & QA (Prioridad 1)
5. Deployment & Training (Prioridad 0-1)

---

#### 🔄 Airtable Sync (Verde)
**Propósito**: Sincronizar automáticamente tareas del project-plan a Airtable (Base: Proágil Sprints).

**Input**: `[nombre-proyecto]-project-plan.md` + configuración del usuario
**Output**: Tareas creadas en Airtable con todos los metadatos

**Capacidades clave**:
- Parseo inteligente del project-plan.md
- Mapeo automático a estructura de Airtable
- Validación pre-sync (conexión, campos, proyectos existentes)
- Creación en batch (10 tareas por request)
- Manejo de rate limiting y errores
- Reporte detallado post-sync

**Cuándo usar**:
- Después de revisar y aprobar el project-plan.md
- Para cargar tareas de proyectos nuevos
- Al añadir nuevas tareas a proyectos existentes
- En replantificaciones de proyectos

**Información requerida del usuario**:
- Proyecto en Airtable (obligatorio)
- Producto(s) asociado(s) (opcional)
- Mes de ejecución (10 2025, 11 2025)
- Sprint específico (opcional)
- Usuario asignado (opcional)
- Estado inicial (Plan recomendado)
- Tipo de tareas (Improvement, Bugs, Support, etc.)

---

### Flujo de Trabajo Completo

```
Cliente → Brief/Reunión
    ↓
🔍 Requirements Analyzer
    ↓ requirements-analysis.md
[Revisión y validación humana]
    ↓
📐 Project Planner
    ↓ [proyecto]-project-plan.md
[Revisión y ajuste de estimaciones]
    ↓
🔄 Airtable Sync
    ↓
✅ Tareas en Proágil Sprints (Airtable)
    ↓
Equipo ejecuta desde Airtable
```

### Filosofía de Uso de Agentes

#### Augmentation, not Replacement
Los agentes **potencian** al equipo, no lo reemplazan:
- Automatizan tareas repetitivas y estructuradas
- Liberan tiempo para creatividad y decisiones estratégicas
- Aceleran procesos manteniendo calidad
- El equipo siempre valida y toma decisiones finales

#### Contexto Yellow Glasses
Todos los agentes están entrenados con:
- Valores y filosofía de la empresa
- Stack tecnológico (WeWeb, Supabase, n8n, Webflow)
- Metodología de trabajo
- Estándares de documentación
- Convenciones de nomenclatura

#### Puntos de Decisión Humana

**Post Requirements Analyzer**:
- ✅ Validar que requisitos son correctos y completos
- ✅ Responder preguntas abiertas identificadas
- ✅ Aprobar análisis técnico y stack propuesto
- ✅ Decidir si proceder a planificación

**Post Project Planner**:
- ✅ Revisar fases y secuencia lógica
- ✅ Validar estimaciones según conocimiento del equipo
- ✅ Ajustar prioridades según urgencia del cliente
- ✅ Aprobar plan antes de sincronizar

**Pre Airtable Sync**:
- ✅ Proporcionar información de contexto (proyecto, producto, mes)
- ✅ Confirmar resumen de tareas a crear
- ✅ Validar resultado en Airtable post-sync

#### Iteración y Mejora Continua

**Feedback Loop**:
- Capturar desviaciones entre estimado vs. real
- Documentar cambios en requisitos durante ejecución
- Registrar aprendizajes de cada proyecto

**Optimización de Agentes**:
- Ajustar prompts según feedback recurrente
- Actualizar referencias de estimaciones
- Mejorar detección de patrones
- Refinar templates de output

### Métricas de Éxito

**Requirements Analyzer**:
- % de requisitos sin clarificación adicional: >80%
- % de requisitos sin cambios post-validación: >85%
- Tiempo ahorrado vs. análisis manual: ~60%

**Project Planner**:
- Precisión de estimaciones (desviación): <25%
- % de tareas sin re-planificación: >75%
- Tiempo ahorrado vs. planificación manual: ~70%

**Airtable Sync**:
- Tasa de éxito de sincronización: >95%
- % de tareas con campos completos: >90%
- Tiempo ahorrado vs. carga manual: ~90%

### Stack Técnico de Agentes

**Implementación Actual**:
- **Requirements Analyzer**: Claude API (Sonnet 4.5)
- **Project Planner**: Claude API (Sonnet 4.5)
- **Airtable Sync**: n8n workflow + Claude API + Airtable MCP

**Contexto Cargado**:
- Todos los agentes cargan `yellow-glasses-context.md`
- Agentes siguen especificaciones en `/agents/`
- Workflow documentado en `agents-integration-workflow.md`

### Ubicación de Archivos

```
/Agentes_IA/
├── agents/
│   ├── agent-requirements-analyzer.md
│   ├── agent-project-planner.md
│   └── agent-airtable-sync.md
└── context-and-docs/
    ├── yellow-glasses-context.md (este archivo)
    └── agents-integration-workflow.md
```

---

## 📝 Documentación y Comunicación

### Estándares de Documentación
- **Markdown** como formato principal
- **Estructuras claras**: títulos, listas, tablas
- **Lenguaje directo**: sin ambigüedades, accionable
- **Bilingüe**: español/inglés según contexto

### Tono de Comunicación
- **Profesional pero cercano**
- **Crítico constructivo**: cuestionar para mejorar, no por cuestionar
- **Transparente**: compartir tanto éxitos como desafíos
- **Orientado a acción**: cada comunicación debe llevar a decisiones o acciones claras

---

## 🎓 Filosofía de Entrega

### Para Clientes
- **Ownership**: el cliente debe poder mantener lo construido
- **Formación incluida**: capacitación en herramientas implementadas
- **Documentación completa**: guías, videos, templates
- **Soporte post-entrega**: acompañamiento en adopción

### Para Proyectos Internos
- **Automatización first**: si se hace más de 2 veces, automatízalo
- **Escalabilidad**: diseñar para crecer, no solo para hoy
- **Mantenibilidad**: código y sistemas que otros puedan entender y modificar
- **ROI claro**: cada implementación debe mostrar valor medible
