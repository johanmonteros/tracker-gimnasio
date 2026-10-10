# PRD: Gym Tracker App (PWA)

## 1. Visión del Proyecto
Aplicación Web Progresiva (PWA) minimalista para registro de entrenamientos de hipertrofia y rendimiento (básquet). Diseño para uso con una sola mano, sin distracciones, enfocado en progresión de cargas y tiempos de descanso estrictos.

## 2. UI/UX y Reglas de Diseño
* **Framework:** HTML5, Tailwind CSS (vía CDN), Vanilla JavaScript.
* **Almacenamiento:** LocalStorage.
* **Tema:** Modo Oscuro estricto (fondo casi negro, texto claro, botones con acentos verdes/naranjas).
* **Interacción:** Botones gigantes [+] y [-] para ajustar Peso y Repeticiones (útil para dedos sudados). Sin animaciones complejas ni menús profundos.

## 3. Funcionalidades Core
1. **Selector de Fases:** Desplegable principal para elegir entre Fase 1, Fase 2 y Fase 3.
2. **Selector de Día:** Desplegable secundario ('Día 1', 'Día 2', 'Día 3', 'Día 4').
3. **Indicador de Lugar:** Etiqueta visual debajo del selector de días. Si es Día 1, 2 o 4: "📍 Lugar: Gym". Si es Día 3: "📍 Lugar: CrossFit".
4. **Lista Dinámica:** Los ejercicios cambian automáticamente según la Fase y el Día seleccionados.
5. **Registro:** Cada ejercicio muestra controles de Peso (kg) y Repeticiones. 
6. **Temporizador Automático:** Botón "Completar Serie" que guarda en LocalStorage e inicia una cuenta regresiva visible de 90 segundos (con botones rápidos para cambiar a 60s o 120s).
7. **Historial Diario:** Lista inferior que muestra las series de hoy. Debe incluir obligatoriamente el botón de eliminar (ícono de papelera o 'X') para borrar series erróneas.

## 4. Base de Datos de Ejercicios (Las 3 Fases)

### Fase 1: Adaptación y Base (Semanas 1-4)
* **Día 1 (Gym):** Sentadilla Búlgara, Peso Muerto Rumano con mancuernas, Extensión de Cuádriceps, Curl de Isquiotibiales, Elevación de Talón a 1 pierna.
* **Día 2 (Gym):** Press Inclinado con mancuernas, Dominadas estrictas, Remo en polea/mancuerna, Face Pull, Elevaciones Laterales, Curl de Bíceps alterno.
* **Día 3 (CrossFit):** Saltos a Cajón, Kettlebell Swings, Zancadas Laterales (Lateral Lunges), Plancha abdominal.
* **Día 4 (Gym):** Press Plano con mancuernas, Jalón al pecho (Polea), Press Militar sentado, Extensión de Tríceps (Cuerda), Curl Martillo para Bíceps.

### Fase 2: Fuerza e Hipertrofia (Semanas 5-12)
* **Día 1 (Gym):** Prensa de Piernas (Leg Press), Peso Muerto Rumano con barra, Extensión de Cuádriceps, Curl de Isquiotibiales, Elevación de talones (Máquina).
* **Día 2 (Gym):** Press de Banca con barra, Dominadas, Remo con barra, Face Pull, Elevación Lateral con mancuernas.
* **Día 3 (CrossFit):** Saltos a Cajón (Alto), Sentadilla Búlgara pesada, Kettlebell Swings Pesados, Zancadas Laterales (Lateral Lunges), Plancha abdominal con peso.
* **Día 4 (Gym):** Press Inclinado con mancuernas, Jalón al Pecho, Press Militar sentado, Curl de Bíceps alterno, Extensión de Tríceps en polea.

### Fase 3: Atleta Pro / Mantenimiento (Permanente)
* **Día 1 (Gym):** Sentadilla Libre con barra, Peso Muerto Rumano pesado, Sentadilla Búlgara, Elevación de talones pesada.
* **Día 2 (Gym):** Press de Banca Inclinado con barra, Dominadas con lastre, Remo con barra, Face Pull, Elevaciones Laterales.
* **Día 3 (CrossFit):** Saltos de profundidad (Depth Jumps), Push Press con barra/mancuernas, Zancadas Laterales, Kettlebell Swings.
* **Día 4 (Gym):** Press Plano, Jalón al Pecho pesado, Press Arnold, Superserie: Curl de Bíceps + Extensión Tríceps.