# 📚 Contexto y Documentación

Esta carpeta contiene el contexto de Yellow Glasses y la documentación del flujo de trabajo integrado de los agentes.

---

## Archivos Disponibles

### 🌍 Yellow Glasses Context
**Archivo**: [yellow-glasses-context.md](yellow-glasses-context.md)

Contexto completo de la empresa que **TODOS los agentes deben cargar** antes de ejecutarse.

**Contenido**:
- Misión, valores y filosofía Yellow Glasses
- Stack tecnológico (WeWeb, Supabase, n8n, Webflow)
- Metodología de trabajo y filosofía operativa
- Tipos de proyectos habituales
- Gestión con Airtable (estructura y campos clave)
- Uso de agentes IA en la empresa
- Estándares de documentación y comunicación

**¿Por qué es importante?**
Este contexto asegura que los agentes:
- Entiendan la filosofía y valores de Yellow Glasses
- Propongan soluciones alineadas con el stack tecnológico
- Apliquen la metodología correcta según el tipo de proyecto
- Generen documentación en el estilo de la empresa

---

### 🔗 Agents Integration Workflow
**Archivo**: [agents-integration-workflow.md](agents-integration-workflow.md)

Documentación completa del flujo de trabajo integrado de los 3 agentes.

**Contenido**:
- **Workflow Completo**: Cómo los 3 agentes trabajan juntos
- **Puntos de Decisión Humana**: Dónde y cuándo interviene el equipo
- **Iteración y Mejora Continua**: Feedback loops y aprendizaje
- **Métricas de Éxito**: KPIs para cada agente
- **Consideraciones Técnicas**: Stack sugerido para implementación
- **Roadmap de Evolución**: Fases de desarrollo (MVP → Inteligencia)
- **Próximos Pasos Inmediatos**: Guía para empezar la implementación

**¿Por qué es importante?**
Este documento:
- Muestra cómo integrar los 3 agentes en un workflow cohesivo
- Define puntos de validación humana críticos
- Establece métricas para medir el éxito
- Proporciona un roadmap claro de evolución

---

## Cómo Usar Estos Archivos

### Para Implementar un Agente

1. **Leer yellow-glasses-context.md** completo
2. **Incluirlo en el system prompt** del agente
3. Leer la especificación del agente específico
4. Combinar contexto + especificación en el prompt final

### Para Entender el Workflow Completo

1. **Leer agents-integration-workflow.md**
2. Identificar los puntos de decisión humana
3. Preparar los flujos de validación
4. Implementar según el stack recomendado

---

## Actualización de Documentos

### Yellow Glasses Context
**Actualizar cuando**:
- Cambien los valores o filosofía de la empresa
- Se adopten nuevas herramientas en el stack
- Cambie la metodología de trabajo
- Se modifique la estructura de Airtable
- Se actualicen convenciones de nomenclatura

### Agents Integration Workflow
**Actualizar cuando**:
- Se añadan nuevos agentes al sistema
- Cambien los puntos de decisión humana
- Se implementen mejoras en el workflow
- Se actualicen las métricas de éxito
- Se avance en el roadmap de evolución

---

## Integración con Agentes

Todos los agentes en la carpeta `../agents/` deben:

✅ Cargar `yellow-glasses-context.md` como contexto base
✅ Seguir los estándares definidos en estos documentos
✅ Integrarse según el workflow definido
✅ Generar outputs compatibles con el flujo completo

---

## Estructura de Información

### Yellow Glasses Context
```
├── Sobre la Empresa
├── Rol de Víctor Bompart (COO)
├── Servicios de Yellow Glasses
├── Stack Tecnológico
│   ├── Core Stack (WeWeb, Supabase, n8n, Webflow)
│   └── Herramientas Complementarias
├── Metodología de Trabajo
├── Tipos de Proyectos Habituales
├── Gestión con Airtable
│   ├── Estructura de bases
│   ├── Campos clave
│   └── Flujo de información
├── Uso de Agentes IA
└── Documentación y Comunicación
```

### Agents Integration Workflow
```
├── Flujo Integrado de los 3 Agentes
├── Puntos de Decisión Humana
├── Iteración y Mejora Continua
│   ├── Feedback Loop
│   └── Métricas de Éxito
├── Consideraciones Técnicas de Implementación
│   ├── Stack Sugerido
│   ├── Prompts Base
│   └── Gestión de Contexto
├── Documentación Complementaria
└── Roadmap de Evolución
    ├── Fase 1: MVP
    ├── Fase 2: Automatización
    ├── Fase 3: Inteligencia
    └── Fase 4: Escalabilidad
```

---

## Casos de Uso

### Nuevo Miembro del Equipo
1. Leer `yellow-glasses-context.md` para entender la empresa
2. Leer `agents-integration-workflow.md` para entender el sistema
3. Revisar especificaciones de agentes en `../agents/`

### Implementar Nuevo Agente
1. Seguir estructura de agentes existentes
2. Cargar `yellow-glasses-context.md`
3. Actualizar `agents-integration-workflow.md` con el nuevo agente

### Actualizar Metodología
1. Modificar `yellow-glasses-context.md`
2. Actualizar agentes afectados
3. Documentar cambios en `agents-integration-workflow.md`

---

## Mantenimiento

### Frecuencia de Revisión
- **Yellow Glasses Context**: Trimestral o cuando haya cambios significativos
- **Agents Integration Workflow**: Mensual o al implementar mejoras

### Control de Versiones
Incluir fecha y versión en cada actualización:
```markdown
---
**Última actualización**: DD de Mes, YYYY
**Versión**: X.Y
**Cambios**: Descripción breve de cambios
---
```

---

Volver al [README principal](../README.md)
