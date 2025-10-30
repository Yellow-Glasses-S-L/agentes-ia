# 🤖 Agentes IA

Esta carpeta contiene las especificaciones completas de los 3 agentes de IA para Yellow Glasses.

---

## Agentes Disponibles

### 1. 🔍 Requirements Analyzer
**Archivo**: [agent-requirements-analyzer.md](agent-requirements-analyzer.md)

Analiza y estructura requisitos de proyectos transformando información no estructurada en especificaciones claras y accionables.

**Input**: Briefs, transcripciones, emails, notas
**Output**: `requirements-analysis.md`

---

### 2. 📐 Project Planner
**Archivo**: [agent-project-planner.md](agent-project-planner.md)

Convierte requisitos estructurados en planes de proyecto ejecutables con tareas detalladas, estimaciones y dependencias.

**Input**: `requirements-analysis.md`
**Output**: `[proyecto]-project-plan.md`

---

### 3. 🔄 Airtable Sync
**Archivo**: [agent-airtable-sync.md](agent-airtable-sync.md)

Sincroniza automáticamente las tareas del project-plan a Airtable (Base: Proágil Sprints) con mapeo inteligente de campos.

**Input**: `[proyecto]-project-plan.md`
**Output**: Tareas en Airtable

---

## Flujo de Uso

```
Requirements Analyzer → Project Planner → Airtable Sync
```

Cada agente está diseñado para funcionar de manera independiente pero se integran perfectamente en un workflow completo.

---

## Estructura de Cada Archivo de Agente

Todos los archivos de agente siguen esta estructura:

1. **Propósito**: Qué hace el agente y por qué
2. **Contexto de Uso**: Input, output y usuarios
3. **Capacidades Principales**: Funcionalidades detalladas
4. **Comportamiento del Agente**: Tono, estilo y proceso
5. **Casos de Uso Específicos**: Ejemplos reales
6. **Integración con Otros Agentes**: Cómo se conecta con los demás

---

## Cómo Implementar un Agente

### 1. Leer la especificación completa
Abrir y leer el archivo .md del agente específico.

### 2. Cargar contexto de Yellow Glasses
Incluir `../context-and-docs/yellow-glasses-context.md` en el system prompt.

### 3. Crear system prompt
Combinar:
- Contexto de Yellow Glasses
- Especificación del agente
- Instrucciones de formato de output

### 4. Ejecutar con input correspondiente
Proporcionar el input esperado según la especificación.

### 5. Validar output
Verificar que el output cumple con el formato y calidad esperados.

---

## Consideraciones Importantes

### Compatibilidad entre Agentes
Los agentes están diseñados para ser compatibles:
- El output del Requirements Analyzer es el input del Project Planner
- El output del Project Planner es el input del Airtable Sync
- Los formatos son consistentes y parseables

### Formato de Estimaciones
- Usar siempre "X hours" (ej: "4 hours", "8 hours")
- El Airtable Sync convierte automáticamente a formato duration

### IDs de Tareas
- Usar formato TASK-001, TASK-002, TASK-003...
- Mantener secuencia consistente

### Prioridades
- 0 = Crítico (bloqueante)
- 1 = Alto (importante, pronto)
- 2 = Medio (importante, no urgente)
- 3 = Bajo (nice to have)

---

## Próximos Pasos

1. Implementar el primer agente (Requirements Analyzer)
2. Probar con caso de uso real
3. Validar output y ajustar prompts si es necesario
4. Implementar siguiente agente
5. Probar workflow completo

---

Volver al [README principal](../README.md)
