# Lineamientos para la Elaboración de Clases en Plataforma — English Hub

**Institución:** Learning & Development Studio (`Educate • Design • Grow`)  
**Referencia visual de plataforma:** [`A1.2-U04: White Lies We Tell Right Now`](https://learning-development-studio.github.io/english-hub/A1.2/white-lies/)  
**Fuentes normativas:**

- *L\&D Studio \| Documento rector de Scope and Sequence* (versión consolidada 3 nov 2026\)  
* *MasterScope*Sequence*LD*Studio.docx (mapa de Macro-Unidades, Unidades y Lecciones)  
- *Manual Maestro de Lanzamiento — Learning & Development Studio* (identidad oficial)

---

## 1\. Identidad Visual y Sistema de Diseño (*Executive Standard*)

Toda lección creada en la plataforma **English Hub** debe conservar exactamente la línea estética de `white-lies` y el *Manual Maestro de Lanzamiento*:

### 1.1 Marca y Denominación

- **Nombre institucional:** `Learning & Development Studio` (nunca abreviar en encabezados oficiales ni usar variantes no autorizadas).  
- **Descriptor:** `Educate • Design • Grow` (con mayúscula inicial en cada palabra).  
* **Tono visual:** estudio profesional especializado en aprendizaje y desarrollo. Prohibido usar estética infantil, *clipart*, pizarrones, banderas genéricas como recurso principal o saturación de emojis. Prohibido usar el nombre **"Maya"** como personaje en cualquier lección.  
- **Prohibición de tarjetas cliché de IA:** queda **estrictamente prohibido** usar en cualquier parte de la plataforma (navegación, vocabulario, gramática, avisos o ejercicios) tarjetas con bordes gruesos de color superior o lateral (`border-top` / `border-left` de acento). Toda tarjeta o contenedor debe usar superficies limpias, bordes finos uniformes (`1px`) o elevación sutil.

### 1.2 Tipografía

- **Principal (UI, títulos y cuerpo):** `Plus Jakarta Sans` (pesos `300` a `800`).  
- **Técnica / Etiquetas / Códigos de módulo:** `IBM Plex Mono` (pesos `400` a `700`).

### 1.3 Paleta de Color Oficial (`:root`)

Conservar los tokens de diseño de *Executive Standard* sin inventar tonos paralelos:

- **Deep Navy (dominante):** `--navy-950: #071527`, `--navy-900: #001F54`, `--navy-800: #0B2545`, `--navy-700: #133E68` (alineado con `#00245B` institucional).  
- **Teal (secundario / interacción):** `--teal-800: #0F766E`, `--teal-700: #007A87`, `--teal-500: #14B8A6`, `--teal-300: #4DD0E1`, `--teal-50: #F0FDFA`.  
- **Champagne Gold (acento / énfasis):** `--gold-600: #B57C00`, `--gold-500: #D4A843`, `--gold-400: #E5A922`, `--gold-100: #FEF8EB`, `--gold-border: rgba(212, 168, 67, 0.35)`.  
- **Neutros y superficies:** `--white: #FFFFFF`, `--slate-50: #F8FAFC` a `--slate-900: #0A192F`.  
- **Estado de error / alerta:** `--danger-600: #DC2626`, `--danger-50: #FEF2F2`.

---

## 2\. Arquitectura de Pantalla y Componentes de Plataforma

Cada lección se construye como una experiencia web autocontenida en HTML/CSS/JS siguiendo la estructura exacta de `white-lies`:

1. **Barra Superior (`header.site-header`) — ✅ Acordado:**  
   - Fondo **Navy** en todas las páginas.  
* **Izquierda — Logo invertido obligatorio en TODOS los headers:** usar la versión invertida del logotipo oficial (mundo y detalles en **blanco**, con presencia visual clara de \~44–48 px de alto), acompañado del nivel/curso discreto.  
  - **Derecha — Únicamente 3 elementos con estilo tipográfico editorial limpio (sin botones toscos ni cajas pesadas):**  
    1. **Nombre del alumno:** recuperado automáticamente del registro inicial (`localStorage`), mostrado como texto limpio (ej. `Student · [Nombre]`).  
    2. **`Teacher's Version ↗`:** enlace tipográfico limpio en Champagne Gold (`#D4A843`) sin fondo sólido, que abre el modal de acceso por **PIN** docente.  
    3. **`← Back to Menu`:** enlace tipográfico limpio en blanco/gris claro (`#E2E8F0`) para regresar al menú anterior.  
2. **Hero Banner (`header.workspace-hero-banner`) — ✅ Acordado:**  
   - **Dimensiones:** exactamente el mismo alto y ancho que el Hero de `white-lies`.  
   - **Fondo:** fotografía *premium* de calidad cinematográfica referente al título de la lección, con el **lavado navy** característico de `white-lies`.  
   - **Sin cápsulas ni métricas:** se **eliminan** las cápsulas superiores (`TRAJECTORY · STAGE...`, `CEFR...`) y cualquier barra de conteo/métricas inferior (`Communicative Quests`, `Language Labs`, etc.).  
   - **Título (`<h1>`):** estilo unificado con el menú principal y el hero de curso: texto en **blanco** destacando palabras clave en **dorado** (`#D4A843` / `#E5A922`).  
* **Subtítulo debajo del título:** **únicamente** una pequeña introducción/resumen atractivo sobre la lección (el dilema o situación real). **Prohibido** incluir explicaciones gramaticales (*"Today we check Present Simple"*), nivel, número de ejercicios o datos irrelevantes para el alumno.  
  - **Vocabulario prohibido:** queda estrictamente prohibido usar `master`, `mastery` (y sus derivados), `pace` o frases genéricas de IA en el Hero y en toda la plataforma.  
3. **Navegación Modular (`nav.module-nav-grid`) — ✅ Acordado:**  
* **Estándar único en TODAS las clases:** **Segmented Bar editorial** (contenedor único `#F1F5F9` con borde fino `1px solid #E2E8F0` y `padding: 5px`).  
  - **Segmentos uniformes:** índice numérico limpio en `IBM Plex Mono` (`01`, `02`, `03`…) \+ título corto en `Plus Jakarta Sans` (sin repetir la palabra *"Module"*).  
  - **Estados:** inactivo transparente; activo en blanco (`#FFFFFF`) con elevación sutil (sombra suave, **cero bordes gruesos de colores**), texto en Deep Navy (`#001F54`) y número en Teal/Dorado. Scroll horizontal fluido en móvil.  
  - **Continuidad:** navegación discreta al pie de cada pantalla (`← Previous` / `Next →`).  
  - *Regla metodológica:* el orden y cantidad de módulos se adapta al objetivo comunicativo de cada lección (sin repetir mecánicamente siempre la misma secuencia fija).  
4. **Secuencia, Cantidad y Estructura de Módulos / Segmentos — ✅ Acordado:**  
* **Primer segmento obligatorio (Warm-up / Activación):** **SIEMPRE** la primera parte de la clase es un *warm-up* que habilita los conocimientos previos del alumno y lo conecta con el tema.  
  * **Intercambio real y acotado:** además del estímulo inicial, debe incluir **pocas preguntas detonadoras bien dirigidas** (sin saturar con 20 preguntas) que pongan al alumno a reaccionar, intercambiar opiniones o producir desde el inicio, con frases claras. **Prohibido** mostrar porcentajes inventados o datos ficticios en encuestas/*polls*.  
    - **Diversidad de formatos y regla de no repetición:** no existe un formato único (no siempre *WhatsApp screenshot*); se alternan formatos variados (*survey/poll*, mini *podcast*, lluvia de ideas, *comic*, *magazine*, escenario/situación, video, juego breve, etc.). **Dentro de una misma Macro-Unidad, NO se repite el mismo formato de Warm-up** entre sus lecciones.  
  - **Segundo segmento obligatorio (Vocabulario):** después del *warm-up* viene el módulo de vocabulario.  
* **Cantidad:** en niveles **A1**, **6 palabras/expresiones** útiles de alto valor en *Flip Cards* (no gastar tarjetas en palabras transparentes como *family* o *brother*); cuando el tema dé para más (ej. familia, casa), complementar con un **mapa visual o árbol temático con fotos** para ampliar el vocabulario sin saturar.  
* **Formato de tarjeta (*Flip Card* limpia, sin bordes gruesos de color):**  
> > > > > > * **Frente:** palabra, *part of speech*, pronunciación y ejemplo centrado en contexto (con botones de audio real).  
> > > > > > * **Reverso:** **palabra repetida en grande** \+ *meaning* centrado y legible.  
  - **Micro-foco de inteligibilidad (integrado):** contraste breve de pronunciación crítica con audios reales (ej. `I'm` vs `I am`, `his` vs `her`, `this` vs `these`) dentro de Vocabulario o Gramática.  
    - **Vocab Activity anexa (variedad obligatoria):** dentro del mismo módulo se incluye una actividad práctica de vocabulario **creativa y variada**. **Prohibido** repetir siempre el mismo formato de completar enunciados (*Situational Match* de `white-lies`); alternar dinámicas como *Hangman* (ahorcado), *Guess the word*, *Unscramble the word*, *Use the word in a sentence*, *Match*, *Drag & drop*, *Label* (etiquetar imágenes/escenarios), etc., evitando repetir el mismo tipo de actividad dentro de una misma Macro-Unidad.  
* **Regla absoluta de Audio (toda la plataforma):** **NUNCA se utiliza el sintetizador de voz del navegador (`speechSynthesis` / TTS)**. **Todos** los audios de vocabulario (pronunciación y ejemplo) y de cualquier otra sección de la lección son producidos externamente por la coordinación (archivos de audio reales). En desarrollo, se dejan preparadas las rutas/reproductores de audio correspondientes.  
* **Orden inductivo por defecto (Habilidad Receptiva → Gramática):** presentar primero los *USA Chunks* y el **Listening / Reading** breve para que el alumno note la estructura en contexto real (*Notice*), y después abrir la sistematización explícita en **Gramática** (*Understand*), alternando con enfoque deductivo solo cuando el tema lo justifique.  
  - **Módulo de Gramática (Explícita \+ Grammar in Context) — ✅ Acordado:**  
    - **Alcance estricto al nodo `[N]`:** se enseña **exactamente lo que dicta el nodo en `Master_Scope_Sequence_LD_Studio.docx`**, ni más ni menos.  
* **Explicación breve y natural (antes del cuadro):** 1–2 líneas naturales explicando su uso en la situación real (sin cajas rígidas literales de *When / Why / How*).  
* **Cuadro gramatical estructurado:** mostrar de forma explícita las estructuras aplicables al nodo en **Affirmative**, **Negative**, **Yes/No Questions** e **Information Questions (`Wh-`)** *(respetando siempre límites `[F]`)*.  
* **Grammar in Context (en la misma pantalla, con variedad obligatoria):** **prohibido** depender siempre del típico *complete the blank space* y **prohibido** resaltar en rojo o subrayar el error en ejercicios de *Spot & Fix / Error Clinic* (el alumno debe detectarlo por sí mismo). Alternar dinámicas contextuales como *Error Clinic / Find & Fix*, *Sentence Reordering / Wordbox*, *Spot the Rule in a real text/dialogue*, *Transform (affirmative ↔ negative ↔ question)*, *Match form to meaning/intention*, *Natural vs. Broken choice*, etc., sin repetir la misma mecánica dentro de una Macro-Unidad.  
  - **Módulo de Functional Language / USA Pragmatic Chunks — ✅ Acordado:**  
* **Cantidad:** **3 a 4 chunks** por lección, enseñados explícitamente como **bloques fijos** (sin desglosar ni analizar su gramática interna; ej. *I gotta go* tal cual es la frase).  
* **Mismo formato y orden que Vocabulario:** tarjetas *Flip Card* limpias (sin bordes gruesos de color), con expresión, uso/categoría, pronunciación y ejemplo centrado en el **frente** (con audio real producido externamente), y expresión repetida \+ *meaning* / sentido pragmático real centrado en el **reverso**.  
  - **Módulo de Habilidad Receptiva Integrada (Reading / Listening / Video) — ✅ Acordado:**  
    - Seleccionando la habilidad que mejor encuadre con la gramática y el tema (clip de serie, *podcast*, artículo de revista, diálogo, etc.).  
    - **Regla de integración obligatoria:** el texto, audio o video **debe incluir sí o sí** la gramática de la lección y **varias de las expresiones / USA Pragmatic Chunks enseñadas**, respetando estrictamente el aprendizaje acumulativo (cero estructuras futuras `F` contaminando el texto). (Si es *Listening*, la transcripción permanece oculta antes de la escucha independiente).  
* **Perfiles en Reading (retratos \+ audio opcional post-lectura):** cuando el *Reading* presente perfiles o testimonios de personas, incluir retratos fotográficos circulares limpios (`border-radius: 50%`, sin bordes gruesos) y un botón opcional de audio (`Listen (after reading)`) para que el alumno lea primero en silencio y luego pueda escuchar la pronunciación y ritmo real.  
  - **Módulo de Producción Libre / Speaking (Dinámica Comunicativa) — ✅ Acordado:**  
> > > > > > * Para que el alumno produzca de forma libre e integrada usando el repertorio de la clase, **sin mostrar etiquetas técnicas (`P + N + L`) en la vista del alumno**.  
> > > > > > * **Rúbrica visible para el alumno (*Speaking Checklist*):** incluir siempre un cuadro breve y claro con 3–4 criterios medibles en lenguaje sencillo para que el alumno sepa exactamente qué se espera de su producción.  
  - **Creatividad y variedad de dinámicas:** alternar *Information Gap* (tarjetas A/B donde uno tiene datos que el otro no ve), *Roleplay*, *Mystery Box*, *Deck of Questions*, simulaciones, entrevistas, juegos temáticos, retos comunicativos, etc., fomentando interacción real y evitando repetir el mismo formato dentro de una Macro-Unidad.  
  - **Cierre: Exit Ticket \+ Can-Do Statements — ✅ Acordado:**  
  * Último segmento de la lección: **Exit Ticket** con espacio de respuesta **totalmente en blanco** (sin texto preformulado para copiar) para recoger una micro-producción observable real acompañada de **Can-Do Statements medibles y cuantificables** ligados a la evidencia demostrada.  
  * **Tiempo flexible (*Understanding Comes Before Advancement*):** **no es necesario terminar toda la lección en una sola clase/sesión**; el docente y el alumno toman el tiempo necesario hasta demostrar comprensión real.  
2. **Pie de Página (`footer.studio-site-footer`) — ✅ Acordado:**  
   - `Learning & Development Studio · Educate • Design • Grow · English Hub · [Título de la lección] ([Curso])`.  
   - Enlace separado a **`Teacher's Portal & Printable Version →`**.  
1. **Teacher's Version & `teacher-hub/` (Separación de Roles) — ✅ Acordado:**  
* **En vivo dentro de la clase (`Teacher's Version ↗` con PIN / `?role=teacher`):** acordeones limpios (`.teacher-note-box` con borde fino `1px` Champagne Gold, **sin bordes gruesos**) colocados **ANTES de las instrucciones del alumno** en cada módulo y redactados como **secuencia didáctica paso a paso** (*1\. Setup · 2\. Modeling · 3\. Check · 4\. Keys*), ocultos por defecto para el alumno.  
* **En `teacher-hub/[curso]/[leccion]/index.html` (enlazado en el footer):** documento maestro de preparación y producción que incluye:  
1. **Complete Lesson Plan (Secuencia Didáctica Completa)** paso a paso para toda la clase.  
2. **Delimitación curricular `P / N / F`**  
3. **Guion de Producción de Audios** (texto exacto y nombre de archivo MP3 para grabación en estudio)  
4. **Protocolo de mediación y Rúbrica Cualitativa (`E0–E3`)**  
5. **Versión imprimible limpia** (*Print Teacher Guide* con `@media print` optimizado).  
* **Explore imprimible:** cada página de `Explore` incluye botón **`Print Worksheet`** con `@media print` limpio.

---

## 3\. Reglas Pedagógicas y Control Lingüístico (Documento Rector)

1. **Principio rector:** *Understanding Comes Before Advancement*. Una página completada no equivale a competencia; cada actividad debe generar evidencia observable.  
2. **Clasificación estricta del repertorio (`P / P? / N / F`):**  
   - **`P` (Previamente demostrado):** disponible como base.  
   - **`P?` (Dependencia prevista sin evidencia individual):** diagnosticar o reforzar antes de exigir.  
   - **`N` (Recurso nuevo):** debe enseñarse explícitamente y practicarse con apoyos antes de evaluarse.  
   - **`F` (Límite frontera / futuro prohibido):** queda estrictamente excluido de consignas, textos, audios, distractores, ejemplos, botones e interfaz.  
3. **Control de consignas, interfaz y nivel léxico:**  
   - Todo material del estudiante se presenta en inglés accesible o previamente enseñado.  
   - No usar verbos de instrucción no enseñados sin apoyo visual/modelado.  
* **Sencillez léxica estricta en A1 (aprendizaje progresivo):** prohibido usar vocabulario elevado, literario o B1+ en títulos de tarjetas, descripciones, textos de lectura o ejemplos (ej. *close-knit roots, bustling, metropolis, serene, hectic*). Usar únicamente palabras básicas, concretas y cotidianas (`big, small, quiet, nice, good, happy, old, new, place, family, friends`).  
* **Progresión acumulativa estricta DENTRO de cada lección (`01` a `07`):** nunca preguntar ni exigir al alumno lo que aún no se ha enseñado. El `01 Warm-Up` utiliza **exclusivamente `[P]`** (conocimientos previos de lecciones anteriores, cero `[N]` y cero `[F]`). Los ejemplos de `02 Vocabulary` y `03 USA Chunks` usan únicamente `[P]`. En `04 Reading / Listening` (antes de `05 Grammar`), las preguntas de comprensión se formulan con estructuras `[P]`. Prohibido filtrar posesivos (`his, her, our, their`), genitivo sajón (`'s`) o comparativos/superlativos (`more, most, best, easiest, hardest`) antes de su lección correspondiente.  
4. **Separación estricta de materiales:**  
   - Las guías docentes, claves de respuesta, rúbricas (`E0–E3`), notas de aplicación y transcripciones reservadas permanecen ocultas al alumno (solo visibles en los acordeones de `Teacher's Version` tras PIN y en la versión imprimible aparte).  
5. **Dual Resource (`Experience & Explore`) — ✅ Acordado:**  
   - **Experience** (equivalente al *Student's Book*): la experiencia principal interactiva de clase.  
* **Explore** (equivalente al *Workbook*): la práctica y consolidación autónoma correspondiente (no usar *Workbook Gym*).

1. **Regla Anti-Monotonía y Diseño Comunicativo Vivo (a partir de Unidad 2 en adelante) — ✅ Acordado:**  
* En la Unidad 1 se permite una estructura predecible para dar seguridad inicial al principiante absoluto.  
* A partir de la **Unidad 2 en adelante**, queda **estrictamente prohibido clonar la mecánica interactiva** de la lección anterior en `01 Warm-Up`, `02 Vocabulary` (práctica), `05 Grammar` (práctica) o `06 Speaking` (prohibido repetir *Partner A / Partner B* o cuestionarios idénticos).  
* Toda lección nueva debe variar su dinámica visual y comunicativa (juegos, dilemas, escenas fotográficas, mapas/árboles, roleplays por zonas, etc.) y superar la revisión independiente del auditor bajo este criterio antes de entregarse a vista previa.

---

## 4\. Alcance Inicial: Estructura Exacta de Nivel A1.1

La primera entrega en plataforma estructurará el **Nivel A1.1 (*Identity, Roots, Bonds & Spaces*)** respetando las **6 Macro-Unidades** y **15 Lecciones** de `Master_Scope_Sequence_LD_Studio.docx`:

| Macro-Unidad | Código | Título de la Lección | Gramática `[N]` | Límite Frontera `[F]` |
| :---- | :---- | :---- | :---- | :---- |
| **01\. The Name We Carry & First Impressions** | `A1.1-U01-L01` | The Story Behind Your Name | Pronombres (`I, you`), `To Be` (`I am / I am not`), posesivo `My` | Prohibido verbos de acción (`work, like, live`) |
|  | `A1.1-U01-L02` | Where Are You Really From? | `To Be` (`he, she, we, they`) \+ preguntas Yes/No (`Are you from...?`) | Prohibido `come from` con auxiliar `do` |
|  | `A1.1-U01-L03` | The Job vs. The Human | Artículos indefinidos (`a/an`) \+ `To Be` para profesiones | Prohibido rutinas de trabajo en Present Simple |
|  | `A1.1-U01-L04` | The First 30 Seconds | Preguntas `Wh-` \+ `To Be` (`Who, What, Where, How old`) | Prohibido preguntas con `What does he do?` |
| **02\. Chosen Family & Household Boundaries** | `A1.1-U02-L01` | Blood vs. Bond | Adjetivos posesivos (`my, your, his, her, our, their`) | Prohibido posesivos independientes (`mine, yours`) |
|  | `A1.1-U02-L02` | The Borrowed Jacket | Genitivo sajón (`'s`) \+ `Whose is this? / Whose are these?` | Prohibido doble genitivo (`a friend of mine's`) |
|  | `A1.1-U02-L03` | The Meaning Behind the Object | `Have / Has` para posesión física (afirmativa y negativa) | Prohibido `have` para rutinas (`have breakfast`) |
| **03\. Spaces, Sanctuaries & The Clutter Dilemma** | `A1.1-U03-L01` | The Junk Drawer | `There is / There are` (afirm./neg./preg.) \+ plurales | Prohibido cuantificadores complejos de B1 |
|  | `A1.1-U03-L02` | The Sanctuary | Preposiciones de lugar (`in, on, under, behind, next to, between, in front of`) | Prohibido preposiciones de movimiento |
|  | `A1.1-U03-L03` | The Impulse Buy on My Desk | Demostrativos (`this, that, these, those`) | Prohibido comparativos (`This is better than...`) |
| **04\. The Neighborhood & Lost Connections** | `A1.1-U04-L01` | The Disappearing Corner Shop | `Is there a...? / Are there any...?` | Prohibido condicionales o preguntas indirectas |
|  | `A1.1-U04-L02` | Could You Survive Without GPS? | Imperativos afirmativos y negativos \+ preposiciones | Prohibido modales de cortesía indirectos |
| **05\. Appearances, Aging & Character** | `A1.1-U05-L01` | Gray Hair & Wrinkles | Posición del adjetivo (`To be + adj` vs `have/has + adj + noun`) | Prohibido comparativos y superlativos |
|  | `A1.1-U05-L02` | Don't Judge the Book by Its Cover | Adjetivos de personalidad opuestos \+ `and, but` | Prohibido conectores complejos (`However, In spite of`) |
| **06\. A1.1 Capstone Studio** | `A1.1-U06-L01` | The Unsung Hero Profile | Integración total (`To Be`, posesivos, `'s`, `Have/Has`, `There is/are`) | Prohibido tiempos continuos o pasados |

---

## 5\. Flujo de Trabajo y Verificación Previa

1. **Antes de crear o modificar cada lección/módulo:** confirmar paso a paso el alcance, el repertorio `P / N / F` y la estructura visual.  
2. **Validación técnica y académica antes de entregar:**  
   - Revisar **V1** (correspondencia con nivel/objetivo) y **V2** (coherencia interna, dependencias y límites `F`).  
   - Comprobar en navegador/código que navegación por pestañas, audios/TTS, botones, retroalimentación y claves de respuesta funcionen correctamente.  
   - Verificar fidelidad visual al sistema *Executive Standard* (`Plus Jakarta Sans`, `IBM Plex Mono`, paleta Navy/Teal/Gold/Slate).