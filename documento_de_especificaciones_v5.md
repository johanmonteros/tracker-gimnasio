# PRD: Gym Tracker App (PWA) v5

## 1. Visión del Proyecto
Aplicación Web Progresiva (PWA) minimalista para registro de entrenamientos de hipertrofia y rendimiento (básquet). Diseño para uso con una sola mano, sin distracciones, enfocado en progresión de cargas, tiempos de descanso estrictos y recomendaciones automáticas.

## 2. UI/UX y Reglas de Diseño
* **Framework:** HTML5, Tailwind CSS (vía CDN), Vanilla JavaScript.
* **Almacenamiento:** LocalStorage.
* **Tema:** Modo Oscuro estricto (fondo casi negro, texto claro, botones con acentos verdes/naranjas).
* **Interacción:** Botones gigantes [+] y [-] para ajustar Peso y Repeticiones (útil para dedos sudados). Sin animaciones complejas ni menús profundos.

## 3. Funcionalidades Core
1. **Selector de Fases:** Desplegable principal para elegir entre Fase 1 (1 mes), Fase 2 (2 meses) y Fase 3 (Permanente).
2. **Selector de Día:** Desplegable secundario ('Día 1: Lower', 'Día 2: Upper', 'Día 3: Lower', 'Día 4: Upper').
3. **Indicador de Lugar:** Etiqueta visual debajo del selector de días. Si es Día 1, 2 o 4: "📍 Lugar: Gym". Si es Día 3: "📍 Lugar: CrossFit".
4. **Lista Dinámica:** Los ejercicios cambian automáticamente según la Fase y el Día seleccionados.
5. **Recomendación de Series y Reps (NUEVO):** Al seleccionar un ejercicio, debe mostrarse debajo del nombre un pequeño texto con la meta. Ej: "🎯 Recomendado: 3 series x 8-10 reps".
6. **Lógica de Peso Dinámico:** Si el ejercicio es de peso corporal (ej. Dominadas, Saltos, Plancha), la sección de "Peso (kg)" debe ocultarse completamente de la interfaz para ese ejercicio.
7. **Temporizador Inteligente:** Al presionar "Completar Serie", se guarda en LocalStorage y se inicia un temporizador que pre-selecciona automáticamente 60s, 90s o 120s según el ejercicio.
8. **Historial Diario:** Lista inferior que muestra las series de hoy, con un botón (ícono de papelera o 'X') para eliminar registros erróneos.

## 4. Base de Datos de Ejercicios (Con Parámetros Inteligentes)
*Nota para el desarrollador: Estructurar cada ejercicio como un objeto que incluya `nombre`, `recomendacion`, `requierePeso` (boolean) y `descanso` (número en segundos).*

### Fase 1: Adaptación y Base (1 mes)
**Día 1: Lower (Gym)**
* Sentadilla Búlgara | 🎯 3x8-10 | Peso: Sí | Descanso: 120
* Peso Muerto Rumano con mancuernas | 🎯 3x10-12 | Peso: Sí | Descanso: 120
* Extensión de Cuádriceps | 🎯 3x12-15 | Peso: Sí | Descanso: 60
* Curl de Isquiotibiales | 🎯 3x12-15 | Peso: Sí | Descanso: 60
* Elevación de Talón a 1 pierna | 🎯 4x15-20 | Peso: Sí | Descanso: 60

**Día 2: Upper (Gym)**
* Press Inclinado con mancuernas | 🎯 4x8-10 | Peso: Sí | Descanso: 120
* Dominadas estrictas | 🎯 4x Al fallo | Peso: No | Descanso: 120
* Remo en polea/mancuerna | 🎯 3x10-12 | Peso: Sí | Descanso: 90
* Face Pull | 🎯 4x15 | Peso: Sí | Descanso: 60
* Elevaciones Laterales | 🎯 3x15 | Peso: Sí | Descanso: 60
* Curl de Bíceps alterno | 🎯 3x12 | Peso: Sí | Descanso: 60

**Día 3: Lower (CrossFit)**
* Saltos a Cajón | 🎯 4x5 | Peso: No | Descanso: 120
* Kettlebell Swings | 🎯 4x12-15 | Peso: Sí | Descanso: 90
* Zancadas Laterales (Lateral Lunges) | 🎯 3x12 | Peso: Sí | Descanso: 90
* Plancha abdominal | 🎯 3x45-60 seg | Peso: No | Descanso: 60

**Día 4: Upper (Gym)**
* Press Plano con mancuernas | 🎯 4x8-10 | Peso: Sí | Descanso: 120
* Jalón al pecho (Polea) | 🎯 3x10-12 | Peso: Sí | Descanso: 90
* Press Militar sentado | 🎯 3x10 | Peso: Sí | Descanso: 90
* Extensión de Tríceps (Cuerda) | 🎯 4x12-15 | Peso: Sí | Descanso: 60
* Curl Martillo para Bíceps | 🎯 4x12 | Peso: Sí | Descanso: 60

### Fase 2: Fuerza e Hipertrofia (2 meses)
**Día 1: Lower (Gym)**
* Prensa de Piernas (Leg Press) | 🎯 4x8-10 | Peso: Sí | Descanso: 120
* Peso Muerto Rumano con barra | 🎯 4x8-10 | Peso: Sí | Descanso: 120
* Extensión de Cuádriceps | 🎯 3x12 (al fallo) | Peso: Sí | Descanso: 60
* Curl de Isquiotibiales | 🎯 3x12 | Peso: Sí | Descanso: 60
* Elevación de talones (Máquina) | 🎯 4x15 | Peso: Sí | Descanso: 60

**Día 2: Upper (Gym)**
* Press de Banca con barra | 🎯 4x6-8 | Peso: Sí | Descanso: 120
* Dominadas | 🎯 4x Al fallo | Peso: No | Descanso: 120
* Remo con barra | 🎯 4x8-10 | Peso: Sí | Descanso: 90
* Face Pull | 🎯 4x15 | Peso: Sí | Descanso: 60
* Elevación Lateral con mancuernas | 🎯 4x12 | Peso: Sí | Descanso: 60

**Día 3: Lower (CrossFit)**
* Saltos a Cajón (Alto) | 🎯 5x3 | Peso: No | Descanso: 120
* Sentadilla Búlgara pesada | 🎯 3x8 | Peso: Sí | Descanso: 120
* Kettlebell Swings Pesados | 🎯 4x12 | Peso: Sí | Descanso: 90
* Zancadas Laterales | 🎯 3x10 | Peso: Sí | Descanso: 90
* Plancha abdominal con peso | 🎯 3x45 seg | Peso: Sí | Descanso: 60

**Día 4: Upper (Gym)**
* Press Inclinado con mancuernas | 🎯 4x8-10 | Peso: Sí | Descanso: 120
* Jalón al Pecho | 🎯 4x10 | Peso: Sí | Descanso: 90
* Press Militar sentado | 🎯 3x10 | Peso: Sí | Descanso: 90
* Curl de Bíceps alterno | 🎯 4x12 | Peso: Sí | Descanso: 60
* Extensión de Tríceps en polea | 🎯 4x12 | Peso: Sí | Descanso: 60

### Fase 3: Atleta Pro / Mantenimiento (Permanente)
**Día 1: Lower (Gym)**
* Sentadilla Libre con barra | 🎯 4x5 | Peso: Sí | Descanso: 120
* Peso Muerto Rumano pesado | 🎯 4x8 | Peso: Sí | Descanso: 120
* Sentadilla Búlgara | 🎯 3x8 | Peso: Sí | Descanso: 90
* Elevación de talones pesada | 🎯 4x15 | Peso: Sí | Descanso: 60

**Día 2: Upper (Gym)**
* Press de Banca Inclinado con barra | 🎯 4x6 | Peso: Sí | Descanso: 120
* Dominadas con lastre | 🎯 4x6-8 | Peso: Sí | Descanso: 120
* Remo con barra | 🎯 4x8 | Peso: Sí | Descanso: 90
* Face Pull | 🎯 4x15 | Peso: Sí | Descanso: 60
* Elevaciones Laterales | 🎯 4x12 | Peso: Sí | Descanso: 60

**Día 3: Lower (CrossFit)**
* Saltos de profundidad (Depth Jumps) | 🎯 5x3 | Peso: No | Descanso: 120
* Push Press con barra/mancuernas | 🎯 4x5 | Peso: Sí | Descanso: 120
* Zancadas Laterales | 🎯 3x10 | Peso: Sí | Descanso: 90
* Kettlebell Swings | 🎯 4x15 | Peso: Sí | Descanso: 90

**Día 4: Upper (Gym)**
* Press Plano | 🎯 4x8 | Peso: Sí | Descanso: 120
* Jalón al Pecho pesado | 🎯 4x8-10 | Peso: Sí | Descanso: 90
* Press Arnold | 🎯 3x10 | Peso: Sí | Descanso: 90
* Curl de Bíceps (Superserie) | 🎯 4x12 | Peso: Sí | Descanso: 60
* Extensión Tríceps (Superserie) | 🎯 4x12 | Peso: Sí | Descanso: 60