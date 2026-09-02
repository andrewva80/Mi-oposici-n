# Arquitectura del Proyecto y Estructura de Datos

Este documento define cómo se organiza la información dentro de la plataforma de temarios y cómo interactúa el sistema con la API de Claude (Anthropic).

## 📐 Estructura de Navegación y Base de Datos

El contenido de la plataforma se organiza en cuatro niveles jerárquicos estrictos:

1. **Categoría Principal (Área de Estudio):** Grandes bloques (Ej: Oposiciones, Bachillerato, Universidad).
2. **Asignatura / Módulo:** Materias específicas dentro de una categoría.
3. **Temas:** Unidades didácticas individuales que contienen el texto base del estudio.
4. **Recursos Vinculados (Por Tema):** Cada tema tiene asignados de forma exclusiva sus propios recursos:
   - Resúmenes estructurados.
   - Banco de exámenes (Tests / Preguntas de desarrollo).
   - Historial del chat de Inteligencia Artificial.

## 🤖 Integración con Claude (Anthropic)

Para garantizar respuestas precisas, el chat de IA funcionará bajo un modelo de **Contexto Bloqueado**:

- Cuando un usuario abra el chat dentro de un **Tema específico**, la plataforma enviará automáticamente el texto de ese tema a Claude como "Contexto del Sistema" (System Prompt).
- El asistente virtual (Claude 3.5 Sonnet) solo responderá preguntas basadas en dicho material didáctico, evitando mezclar información de otras asignaturas.

## 📁 Mapa de Carpetas Propuesto (Estructura Inicial)

```text
/
├── src/
│   ├── frontend/         # Pantallas del sitio web (React/Next.js)
│   │   ├── components/   # Chat, Menú lateral, Tarjetas de temas
│   │   └── pages/        # Vista de Temas, Vista de Exámenes
│   └── backend/          # Servidor y lógica de la IA (Node.js)
│       ├── controllers/  # Lógica para enviar datos a Claude
│       └── models/       # Modelos de datos (Categorías, Temas, Usuarios)
└── docs/                 # Guías de estudio y esquemas
```
## 🎯 Estrategia de Oposiciones (Pivotaje Alicante / Valencia)

Para optimizar el estudio de oposiciones con temarios compartidos, el sistema implementará:

1. **Módulos Modulares:**
   - `Bloque Común`: Legislación nacional/autonómica compartida.
   - `Bloque Alicante`: Procedimientos locales específicos de Alicante.
   - `Bloque Valencia`: Procedimientos locales específicos de Valencia.
2. **Sistema de Progreso:** Trackeo de notas de exámenes, estados de temas y alertas de repaso inteligente basadas en el éxito de las respuestas del usuario con el chat de Claude.
