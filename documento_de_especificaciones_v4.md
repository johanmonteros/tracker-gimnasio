# PRD: Gym Tracker App (PWA) v4

## 1. Visión del Proyecto
Aplicación Web Progresiva (PWA) minimalista para registro de entrenamientos de hipertrofia y rendimiento (básquet). Diseño inteligente que se adapta al tipo de ejercicio ocultando campos innecesarios y preconfigurando tiempos.

## 2. UI/UX y Reglas de Diseño
* **Framework:** HTML5, Tailwind CSS (vía CDN), Vanilla JavaScript.
* **Almacenamiento:** LocalStorage.
* **Tema:** Modo Oscuro estricto (fondo casi negro, texto claro, botones con acentos verdes/naranjas).
* **Interacción:** Botones gigantes [+] y [-] para ajustar Peso y Repeticiones (útil para dedos sudados). Sin animaciones complejas ni menús profundos.

## 3. Funcionalidades Core
1. **Selector de Fases:** Desplegable principal para elegir entre:
   - "Fase 1: Adaptación y Base (1 mes)"
   - "Fase 2: Fuerza e Hipertrofia (2 meses)"
   - "Fase 3: Atleta Pro / Mantenimiento (Permanente)"
2. **Selector de Día (con etiquetas Upper/Lower):** 
   - "Día 1: Lower 1"
   - "Día 2: Upper 1"
   - "Día 3: Lower 2"
   - "Día 4: Upper 2"
3. **Indicador de Lugar:** Etiqueta visual debajo del selector de días. Si es Día 1, 2 o 4: "📍 Lugar: Gym". Si es Día 3: "📍 Lugar: CrossFit".
4. **Lista Dinámica e Inteligente:** Los ejercicios cambian automáticamente según la Fase y el Día. La estructura de datos JS de los ejercicios debe guardar propiedades de si usa peso o no, y su descanso óptimo.
5. **Interfaz Adaptativa (Ocultar Peso):** Si un ejercicio está marcado como "Sin Peso" (ej. Dominadas, Saltos, Planchas), el contenedor de botones de "Peso (kg)" **debe desaparecer** por completo de la pantalla, dejando solo el contenedor de "Repeticiones" (o tiempo).
6. **Temporizador Dinámico:** Al seleccionar un ejercicio, el temporizador debe pre-seleccionar automáticamente su tiempo de descanso óptimo (60s, 90s o 120s) según los datos del ejercicio.
7. **Historial Diario:** Lista inferior que muestra las series de hoy. Debe incluir obligatoriamente el botón de eliminar (ícono de papelera o 'X') para borrar series erróneas.

## 4. Base de Datos de Ejercicios
*(Formato para el desarrollador: Nombre del Ejercicio [Requiere Peso: Sí/No, Descanso: X seg])*

### Fase 1 (1 mes)
* **Día 1: Lower 1 (Gym)**
  - Sentadilla Búlgara [Peso: Sí, Descanso: 120s]
  - Peso Muerto Rumano con mancuernas [Peso: Sí, Descanso: 120s]
  - Extensión de Cuádriceps [Peso: Sí, Descanso: 60s]
  - Curl de Isquiotibiales [Peso: Sí, Descanso: 60s]
  - Elevación de Talón a 1 pierna [Peso: Sí, Descanso: 60s]
* **Día 2: Upper 1 (Gym)**
  - Press Inclinado con mancuernas [Peso: Sí, Descanso: 120s]
  - Dominadas estrictas [Peso: No, Descanso: 120s]
  - Remo en polea/mancuerna [Peso: Sí, Descanso: 90s]
  - Face Pull [Peso: Sí, Descanso: 60s]
  - Elevaciones Laterales [Peso: Sí, Descanso: 60s]
  - Curl de Bíceps alterno [Peso: Sí, Descanso: 60s]
* **Día 3: Lower 2 (CrossFit)**
  - Saltos a Cajón [Peso: No, Descanso: 120s]
  - Kettlebell Swings [Peso: Sí, Descanso: 90s]
  - Zancadas Laterales (Lateral Lunges) [Peso: Sí, Descanso: 90s]
  - Plancha abdominal [Peso: No, Descanso: 60s]
* **Día 4: Upper 2 (Gym)**
  - Press Plano con mancuernas [Peso: Sí, Descanso: 120s]
  - Jalón al pecho (Polea) [Peso: Sí, Descanso: 90s]
  - Press Militar sentado [Peso: Sí, Descanso: 90s]
  - Extensión de Tríceps (Cuerda) [Peso: Sí, Descanso: 60s]
  - Curl Martillo para Bíceps [Peso: Sí, Descanso: 60s]

### Fase 2 (2 meses)
* **Día 1: Lower 1 (Gym)**
  - Prensa de Piernas (Leg Press) [Peso: Sí, Descanso: 120s]
  - Peso Muerto Rumano con barra [Peso: Sí, Descanso: 120s]
  - Extensión de Cuádriceps [Peso: Sí, Descanso: 60s]
  - Curl de Isquiotibiales [Peso: Sí, Descanso: 60s]
  - Elevación de talones (Máquina) [Peso: Sí, Descanso: 60s]
* **Día 2: Upper 1 (Gym)**
  - Press de Banca con barra [Peso: Sí, Descanso: 120s]
  - Dominadas [Peso: No, Descanso: 120s]
  - Remo con barra [Peso: Sí, Descanso: 90s]
  - Face Pull [Peso: Sí, Descanso: 60s]
  - Elevación Lateral con mancuernas [Peso: Sí, Descanso: 60s]
* **Día 3: Lower 2 (CrossFit)**
  - Saltos a Cajón (Alto) [Peso: No, Descanso: 120s]
  - Sentadilla Búlgara pesada [Peso: Sí, Descanso: 120s]
  - Kettlebell Swings Pesados [Peso: Sí, Descanso: 90s]
  - Zancadas Laterales (Lateral Lunges) [Peso: Sí, Descanso: 90s]
  - Plancha abdominal con peso [Peso: Sí, Descanso: 60s]
* **Día 4: Upper 2 (Gym)**
  - Press Inclinado con mancuernas [Peso: Sí, Descanso: 120s]
  - Jalón al Pecho [Peso: Sí, Descanso: 90s]
  - Press Militar sentado [Peso: Sí, Descanso: 90s]
  - Curl de Bíceps alterno [Peso: Sí, Descanso: 60s]
  - Extensión de Tríceps en polea [Peso: Sí, Descanso: 60s]

### Fase 3 (Permanente)
* **Día 1: Lower 1 (Gym)**
  - Sentadilla Libre con barra [Peso: Sí, Descanso: 120s]
  - Peso Muerto Rumano pesado [Peso: Sí, Descanso: 120s]
  - Sentadilla Búlgara [Peso: Sí, Descanso: 120s]
  - Elevación de talones pesada [Peso: Sí, Descanso: 60s]
* **Día 2: Upper 1 (Gym)**
  - Press de Banca Inclinado con barra [Peso: Sí, Descanso: 120s]
  - Dominadas con lastre [Peso: Sí, Descanso: 120s]
  - Remo con barra [Peso: Sí, Descanso: 90s]
  - Face Pull [Peso: Sí, Descanso: 60s]
  - Elevaciones Laterales [Peso: Sí, Descanso: 60s]
* **Día 3: Lower 2 (CrossFit)**
  - Saltos de profundidad (Depth Jumps) [Peso: No, Descanso: 120s]
  - Push Press con barra/mancuernas [Peso: Sí, Descanso: 120s]
  - Zancadas Laterales [Peso: Sí, Descanso: 90s]
  - Kettlebell Swings [Peso: Sí, Descanso: 90s]
* **Día 4: Upper 2 (Gym)**
  - Press Plano [Peso: Sí, Descanso: 120s]
  - Jalón al Pecho pesado [Peso: Sí, Descanso: 90s]
  - Press Arnold [Peso: Sí, Descanso: 90s]
  - Superserie: Curl Bíceps + Ext. Tríceps [Peso: Sí, Descanso: 60s]