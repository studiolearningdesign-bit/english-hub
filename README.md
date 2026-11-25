# English Hub — Espacio Limpio de Producción (L&D Studio)

Carpeta base limpia para producir lecciones por nivel sin mezclar clases anteriores ni sobrescribir código.

- **Repositorio oficial en GitHub:** `https://github.com/studiolearningdesign-bit/english-hub` (`git@github.com:studiolearningdesign-bit/english-hub.git`)

## 1. Documentos Rectores (`_docs/`)

Todos los proyectos por nivel deben regirse por estos documentos oficiales:

- `lineamientos-clases-plataforma.md` — Reglas de diseño (*Executive Standard*), estructura de módulos, audios externos, anti-monotonía, `Experience` / `Explore` / `teacher-hub` y progresión `P / P? / N / F`.
- `documento-rector-scope-and-sequence.md` — Documento rector completo de Scope & Sequence.
- `Master_Scope_Sequence_LD_Studio.docx` — Mapa oficial de Macro-Unidades, Unidades y Lecciones.
- `Manual_Maestro_de_Lanzamiento.md` — Identidad visual e institucional de Learning & Development Studio.

## 2. Estructura de Carpetas

- `assets/` — Recursos visuales institucionales compartidos (`logo.png`, `logo-white-lockup.webp`, `favicon.png`, `hero-clean.jpg`, etc.).
- `teacher-hub/<Nivel>/` — Guías docentes imprimibles y planes de lección por nivel.
- `<Nivel>/` — Carpetas limpias por nivel:
  - `A1.1`
  - `A1.2`
  - `A2.1`
  - `A2.2`
  - `B1.1`
  - `B1.2`
  - `B1-Plus` *(nombre seguro para URLs correspondiente a `B1+`)*
  - `B2.1`
  - `B2.2`
  - `C1`
  - `Business-Executive-English`
  - `Business-Foundations`
  - `TOEFL-Preparation`
  - `TOEIC-Preparation`

## 3. Regla de Alcance para Cada Proyecto de Nivel

Al abrir un proyecto nuevo para un nivel específico (por ejemplo `A1.2`), incluye en sus instrucciones iniciales:

> "Este proyecto es exclusivamente para el nivel **[NIVEL]**. Lee siempre `_docs/lineamientos-clases-plataforma.md` y el Scope & Sequence antes de generar cualquier archivo. Solo puedes crear o editar archivos dentro de `[NIVEL]/` y `teacher-hub/[NIVEL]/`. No modifiques carpetas de otros niveles ni crees scripts temporales fuera de tu alcance."
