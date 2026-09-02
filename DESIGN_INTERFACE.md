# Diseño de la Interfaz Visual (Mockup y UX)

Este documento define la estructura de pantallas y la experiencia de usuario (UX) para la plataforma de estudio adaptada a dispositivos móviles y tablets (iPad).

## 🎛️ 1. Distribución de la Pantalla Principal (Layout de Tres Columnas)

Para aprovechar la pantalla del iPad en horizontal, la aplicación se dividirá en tres bloques visuales limpios:

```text
+------------------------------------------------------------------------------------+

| [Logo] Plataforma Oposiciones          | Perfil Activo: [ Ayuntamiento Alicante v ]|
+------------------------------------------------------------------------------------+

| 📂 MENÚ LATERAL       | 📖 PANEL DE ESTUDIO             | 🤖 CHAT INTELIGENTE (CLAUDE) |
|                       |                                |                              |
| 🔴 BLOQUE COMÚN       | **Tema 3: El Acto Adtvo.**     | > _¿Qué duda tienes sobre   |
|  - T1. Constitución   |                                |    el artículo 4 de la Ley_  |
|  - T2. Ley 39/2015    | [Texto del Temario / Apuntes]  |                              |
|                       |                                | [Botón: Crear Test de Tema]  |
| 🔵 BLOQUE ESPECÍFICO  | ------------------------------ |                              |
|  - T1. Ordenanzas ALC | 📊 PROGRESO DEL TEMA            | 💬 Historial:                |
|                       |  - Lectura: [🟢 Completado]    | - Alumno: ¿Plazo de recurso? |
| 📈 MI PROGRESO        |  - Último Test: [ 8.5 / 10 ]   | - Claude: Son 2 meses para.. |
|  - Global: [██░░░] 30%|  - Repaso: [⚠️ Toca repasar]   |                              |
+------------------------------------------------------------------------------------+
```

## 🎨 2. Componentes Clave de la Interfaz

### A. Selector de Perfil (El interruptor Alicante / Valencia)
- **Ubicación:** Esquina superior derecha.
- **Función:** Un menú desplegable donde el alumno elige su objetivo actual. 
- **Comportamiento visual:** Si cambia de "Alicante" a "Valencia", el menú lateral oculta instantáneamente las carpetas azules de Alicante y muestra las de Valencia. El "Bloque Común" (rojo) y la sección de "Mi Progreso" no se mueven ni se borran.

### B. El Semáforo de Progreso (Menú Lateral)
Cada tema del menú lateral tendrá un pequeño indicador visual de color según las notas guardadas del alumno:
- 🔴 **Rojo:** Tema no leído o test suspenso (nota menor de 5).
- 🟡 **Amarillo:** Tema en estudio o test aprobado raspado (nota entre 5 y 7.5).
- 🟢 **Verde:** Tema dominado (test con nota superior a 7.5).

### C. El Panel del Asistente (Columna Derecha)
El chat con Claude no será una pantalla flotante molesta, sino una columna fija a la derecha del texto de estudio. 
- **Acceso rápido:** Incluye un botón brillante: `"Generar examen de este tema"`. Al pulsarlo, el texto de estudio desaparece temporalmente y se carga un cuestionario interactivo de 4 opciones generado por Claude.

## 🪟 3. Paleta de Colores Propuesta (Modo Enfoque / Oscuro)
Para evitar la fatiga visual durante largas jornadas de estudio de leyes:
- **Fondo principal:** Gris muy oscuro o azul noche (`#121824`).
- **Texto:** Blanco suave o gris claro (`#E2E8F0`).
- **Destacados (Botones/Enlaces):** Azul eléctrico o violeta para elementos de acción (`#6366F1`).
