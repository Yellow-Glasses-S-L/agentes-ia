# 🔗 Flujo Integrado de los 3 Agentes

Este documento describe cómo los tres agentes trabajan juntos en un workflow completo.

---

## Workflow Completo

```
1. REQUIREMENTS ANALYZER
   Input: Brief del cliente, notas de reunión, transcripciones
   Output: requirements-analysis.md
   ↓
   [Revisión humana y validación]
   ↓

2. PROJECT PLANNER
   Input: requirements-analysis.md
   Output: project-plan.md
   ↓
   [Revisión humana y ajustes]
   ↓

3. AIRTABLE SYNC
   Input: project-plan.md + configuración de usuario
   Output: Tareas en Airtable listas para ejecución
   ↓
   [Validación en Airtable]
```

---

## Puntos de Decisión Humana

### 1. Post Requirements Analyzer
**Acciones requeridas**:
- Revisar y validar requisitos extraídos
- Responder preguntas abiertas del análisis
- Aprobar análisis técnico y stack propuesto
- Decidir si pasar a planificación o solicitar re-análisis

**Preguntas clave**:
- ¿Los requisitos capturan correctamente lo que necesita el cliente?
- ¿Hay algo crítico que falta?
- ¿El stack propuesto es el adecuado?
- ¿Las estimaciones iniciales son realistas?

### 2. Post Project Planner
**Acciones requeridas**:
- Revisar plan generado (fases, tareas, estimaciones)
- Ajustar estimaciones según conocimiento del equipo
- Validar dependencias entre tareas
- Aprobar antes de sincronizar a Airtable

**Preguntas clave**:
- ¿Las fases están correctamente secuenciadas?
- ¿Las estimaciones son realistas?
- ¿Faltan tareas importantes?
- ¿Las dependencias están bien definidas?

### 3. Pre Airtable Sync
**Acciones requeridas**:
- Proporcionar información de contexto (PROJECT, PRODUCT, MONTH)
- Revisar resumen de tareas a crear
- Confirmar sincronización
- Validar resultado en Airtable después de la sync

**Preguntas clave**:
- ¿El proyecto existe en Airtable?
- ¿El mes de ejecución es correcto?
- ¿Las tareas deben asignarse desde el inicio?
- ¿El estado inicial es el adecuado?

---

## Iteración y Mejora Continua

### Feedback Loop

#### Durante el Proyecto
1. **Tracking de desviaciones**: Comparar estimaciones vs. tiempo real
2. **Captura de cambios**: Documentar cambios en requisitos o plan
3. **Aprendizajes**: Registrar qué funcionó y qué no

#### Post-Proyecto
1. **Retrospectiva de análisis**: ¿Qué requisitos fueron mal interpretados?
2. **Retrospectiva de planificación**: ¿Qué estimaciones fallaron y por qué?
3. **Retrospectiva de sync**: ¿Hubo problemas en la sincronización?

#### Mejora de Agentes
- Ajustar prompts según feedback recurrente
- Actualizar templates de output
- Refinar estimaciones típicas
- Documentar edge cases y cómo manejarlos

---

## Métricas de Éxito

### Requirements Analyzer
- **Completitud**: % de requisitos que no requieren clarificación adicional
- **Precisión**: % de requisitos que permanecen sin cambios post-validación
- **Tiempo ahorrado**: Tiempo de análisis manual vs. con agente
- **Detección de gaps**: Número de preguntas críticas identificadas

### Project Planner
- **Precisión de estimaciones**: Desviación % entre estimado vs. real
- **Completitud del plan**: % de tareas que no requieren re-planificación
- **Identificación de dependencias**: % de dependencias correctamente identificadas
- **Tiempo ahorrado**: Tiempo de planificación manual vs. con agente

### Airtable Sync
- **Tasa de éxito**: % de sincronizaciones sin errores
- **Precisión de mapeo**: % de tareas correctamente mapeadas
- **Tiempo ahorrado**: Tiempo de carga manual vs. sincronización automática
- **Integridad de datos**: % de tareas con todos los campos completos

---

## Consideraciones Técnicas de Implementación

### Stack Sugerido para Agentes

#### Opción 1: Claude API (Anthropic)
**Pros**:
- Control total sobre prompts y lógica
- Integración flexible con otros sistemas
- Fácil iteración y mejora

**Contras**:
- Requiere desarrollo de scripts/interfaces
- Mantenimiento de código

**Ideal para**: Equipos con capacidad de desarrollo

#### Opción 2: Agentes en n8n
**Pros**:
- Visual y fácil de mantener
- Integración nativa con Airtable
- No requiere código
- Fácil para equipo no-dev

**Contras**:
- Menos control granular sobre prompts
- Dependencia de conectores de n8n

**Ideal para**: Yellow Glasses (empresa no-code)

#### Opción 3: Hybrid (Recomendado)
**Implementación**:
- **Agentes 1 y 2**: Scripts de Claude API (Python/TypeScript)
  - Más control sobre análisis complejo
  - Output a archivos markdown
- **Agente 3**: Workflow de n8n
  - Aprovecha integración nativa con Airtable
  - Manejo visual de errores y retry logic

---

## Prompts Base

### Estructura de System Prompt (para todos los agentes)

```
Eres [NOMBRE DEL AGENTE] de Yellow Glasses.

## Contexto de Yellow Glasses
[Incluir resumen de yellow-glasses-context.md]

## Tu Rol
[Descripción específica del agente]

## Input Esperado
[Formato y estructura del input]

## Output Requerido
[Template exacto del output]

## Proceso de Trabajo
[Pasos que debe seguir el agente]

## Validaciones
[Checklist de calidad antes de entregar output]

## Tono y Estilo
- Profesional y directo
- Crítico constructivo
- Orientado a acción
- Perspectiva Yellow Glasses: optimismo crítico, innovación práctica
```

### Gestión de Contexto

#### Context Files a Incluir
- **Todos los agentes**: `yellow-glasses-context.md`
- **Requirements Analyzer**: Input del usuario (brief, transcripción, etc.)
- **Project Planner**: `requirements-analysis.md`
- **Airtable Sync**: `project-plan.md`

#### Token Management
- **Requirements Analyzer**: ~4K-8K tokens output
- **Project Planner**: ~6K-12K tokens output
- **Airtable Sync**: ~2K-4K tokens procesamiento

**Estrategia**: Usar modelos grandes (Claude 3.5 Sonnet) para análisis y planificación, modelo más pequeño para sync si es necesario.

---

## Documentación Complementaria

### Para Usuarios de los Agentes

#### Guías de Uso Rápido
1. **Quick Start: Requirements Analyzer**
   - Qué información preparar antes de usar el agente
   - Mejores prácticas para inputs
   - Cómo interpretar el output

2. **Quick Start: Project Planner**
   - Cómo revisar el documento de requisitos antes de planificar
   - Qué ajustar en el plan generado
   - Cómo validar estimaciones

3. **Quick Start: Airtable Sync**
   - Información necesaria de Airtable
   - Cómo verificar la sincronización
   - Qué hacer si hay errores

#### Templates de Input
- **Para Requirements Analyzer**:
  - Template de brief de cliente
  - Template de notas de reunión
  - Checklist de información mínima necesaria

### Para Mantenimiento

#### System Prompts Completos
- Archivo de cada prompt en versión completa
- Historial de versiones y cambios
- Rationale detrás de cada sección del prompt

#### Configuración de Airtable
- Esquema de campos (nombres, tipos, relaciones)
- Capturas de pantalla de la estructura
- Scripts de setup si es necesario

#### Logs y Debugging
- Qué eventos registrar
- Formato de logs
- Dónde almacenar logs (Notion, Airtable, archivos)

---

## Roadmap de Evolución

### Fase 1: MVP (1-2 meses)
**Objetivo**: Agentes funcionando individualmente

**Tareas**:
- [ ] Crear system prompts completos para cada agente
- [ ] Implementar Requirements Analyzer (script o n8n)
- [ ] Implementar Project Planner (script o n8n)
- [ ] Implementar Airtable Sync (n8n recomendado)
- [ ] Validar con 3 proyectos piloto
- [ ] Documentar learnings y ajustar prompts

**Criterio de éxito**: 80% de precisión en análisis y planificación

### Fase 2: Automatización (1 mes)
**Objetivo**: Workflow automatizado conectando los 3 agentes

**Tareas**:
- [ ] Crear workflow maestro en n8n
- [ ] Conectar salida de cada agente con entrada del siguiente
- [ ] Implementar notificaciones automáticas de progreso
- [ ] Dashboard de seguimiento (análisis → plan → Airtable)
- [ ] Documentación de uso del workflow completo

**Criterio de éxito**: Flujo completo funcionando con intervención humana mínima en puntos de decisión

### Fase 3: Inteligencia (2-3 meses)
**Objetivo**: Agentes que aprenden de proyectos anteriores

**Tareas**:
- [ ] Sistema de captura de tiempo real vs. estimado
- [ ] Base de conocimiento de estimaciones históricas
- [ ] Detección automática de patrones en requisitos
- [ ] Sugerencias proactivas de optimización
- [ ] Templates inteligentes según tipo de proyecto

**Criterio de éxito**: 90% de precisión en estimaciones

### Fase 4: Escalabilidad (3-4 meses)
**Objetivo**: Múltiples proyectos en paralelo y feedback bidireccional

**Tareas**:
- [ ] Multi-proyecto: analizar y planificar varios proyectos simultáneamente
- [ ] Detección automática de tipo de proyecto (MVP, Enterprise, Migración)
- [ ] Aplicación de templates según tipo detectado
- [ ] Integración bidireccional: updates en Airtable → update de project-plan.md
- [ ] Dashboard ejecutivo de todos los proyectos en pipeline

**Criterio de éxito**: Capacidad de gestionar 5+ proyectos simultáneamente con alta precisión

---

## Próximos Pasos Inmediatos

### Para Comenzar la Implementación

1. **Revisar y validar las descripciones de agentes**
   - Leer `agent-requirements-analyzer.md`
   - Leer `agent-project-planner.md`
   - Leer `agent-airtable-sync.md`
   - Hacer ajustes necesarios según contexto específico

2. **Preparar entorno técnico**
   - Decidir stack: Claude API vs. n8n vs. Hybrid
   - Configurar accesos a Airtable API
   - Preparar estructura de archivos de contexto

3. **Crear primer system prompt**
   - Empezar con Requirements Analyzer
   - Usar template de prompt base + descripción del agente
   - Probar con 1-2 casos de uso reales

4. **Validar con proyecto piloto**
   - Elegir proyecto real pequeño-mediano
   - Ejecutar los 3 agentes manualmente
   - Documentar qué funciona y qué necesita mejora

5. **Iterar y expandir**
   - Ajustar prompts según feedback
   - Implementar siguientes agentes
   - Construir workflow automatizado

---

## Recursos Adicionales

### Documentos Clave
- `yellow-glasses-context.md` - Contexto completo de la empresa
- `agent-requirements-analyzer.md` - Especificación del agente 1
- `agent-project-planner.md` - Especificación del agente 2
- `agent-airtable-sync.md` - Especificación del agente 3

### Referencias Técnicas
- [Anthropic Claude API Docs](https://docs.anthropic.com/)
- [n8n Documentation](https://docs.n8n.io/)
- [Airtable API Reference](https://airtable.com/developers/web/api/introduction)

### Comunidad y Soporte
- Documentar casos de uso internos en Notion
- Crear canal de feedback del equipo
- Registro de mejoras y ajustes realizados
