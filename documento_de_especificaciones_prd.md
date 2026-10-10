# Documento de Requisitos del Producto (PRD)
## Proyecto: Tracker Minimalista de Gimnasio (PWA)

### 1. Visión del Proyecto
Aplicación web progresiva (PWA) de un solo archivo (index.html) para el registro rápido de entrenamientos de hipertrofia y rendimiento atlético. Diseñada para usarse en el celular durante el entrenamiento, con una mano y sin distracciones.

### 2. Stack Tecnológico
*   **Frontend:** HTML5 y JavaScript puro (Vanilla JS).
*   **Estilos:** Tailwind CSS (mediante CDN).
*   **Almacenamiento:** LocalStorage del navegador (no requiere backend ni base de datos externa).
*   **Iconos:** Opcional (usar SVGs en línea o emojis simples para evitar dependencias).

### 3. Reglas de Diseño (UI/UX)
*   **Tema:** Dark Mode estricto (fondo oscuro tipo gris carbón/negro, textos en blanco/gris claro, acentos en verde neón o naranja para botones de acción).
*   **Ergonomía:** Botones extra grandes de `+` y `-` para modificar peso y repeticiones. Textos grandes y legibles.
*   **Rendimiento:** Cero animaciones lentas, transiciones instantáneas.
*   **Estructura Visual:** 
    1. Selector de Día (Dropdown).
    2. Selector de Ejercicio (Dropdown dependiente del Día).
    3. Controles de Peso y Repeticiones (con botones + y -).
    4. Botón gigante de "Completar Serie".
    5. Temporizador visual.
    6. Historial de series del día actual.

### 4. Base de Datos Local (LocalStorage)
*   Guardar un array de objetos con las series completadas.
*   Estructura sugerida por registro: `{ id, fecha, dia, ejercicio, peso, repeticiones }`.

### 5. Lógica del Temporizador
*   Al hacer clic en "Completar Serie", el registro se guarda en el historial inferior.
*   Inmediatamente inicia una cuenta regresiva visible en pantalla, por defecto en 90 segundos.
*   Proveer 3 botones rápidos junto al temporizador para cambiar el tiempo al vuelo: `60s` | `90s` | `120s`.

### 6. Datos Iniciales: Rutina Fase 1 (Novato a Intermedio)
La aplicación debe cargar por defecto estos días y sus respectivos ejercicios:

**Día 1: Lower 1 (Gym)**
*   Sentadilla Búlgara
*   Peso Muerto Rumano (RDL)
*   Extensión de Cuádriceps
*   Curl de Isquiotibiales
*   Elevación de talón a 1 pierna

**Día 2: Upper 1 (Gym)**
*   Press Inclinado con mancuernas
*   Dominadas estrictas
*   Remo en máquina/barra
*   Face Pull
*   Elevaciones Laterales
*   Curl de Bíceps con mancuernas

**Día 3: Lower 2 (Box)**
*   Saltos a Cajón (Plyo Box)
*   Kettlebell Swings
*   Zancadas (Lunges) caminando
*   Plancha abdominal (Plank)

**Día 4: Upper 2 (Gym)**
*   Press Plano con mancuernas
*   Jalón al pecho en polea
*   Press Militar sentado
*   Extensión de Tríceps en polea
*   Curl Martillo para Bíceps