# Plan del proyecto

> Documento de contexto del proyecto. Describe qué se está construyendo, por qué, cómo se trabaja y cuáles son las fases. Se actualiza a medida que el proyecto avanza.

## 1. Idea general

Un **reproductor de música con estética inspirada en los JRPG** (rojo, negro y blanco, formas angulares, cortes diagonales, transiciones dinámicas), construido desde cero como proyecto de aprendizaje y de portafolio.

El proyecto debe ser:

- **Propio y reconocible:** que refleje mis gustos, no una app genérica.
- **Útil en el día a día:** algo que realmente use para escuchar mi música.
- **Evidencia de habilidades:** código limpio, repositorio bien organizado y buenas prácticas de GitHub, para mostrarlo en futuros procesos de selección.

## 2. Perfil de quien desarrolla

- Nivel de estudiante. Conocimientos en **Java, Python y C++**, y algo de ensamblador.
- Interés principal en **backend**.
- Casi sin experiencia en **JavaScript y CSS**.
- Sistema operativo: **Windows**. Editor: **VS Code**. Git ya instalado y configurado.
- Objetivo central: **entender absolutamente todo lo que se hace**, no solo copiar y pegar código.

## 3. Decisiones tomadas

| Tema | Decisión |
|---|---|
| Rama principal | `main` |
| Licencia | MIT |
| `.gitignore` | Plantilla Node (se ampliará con archivos propios) |
| Visibilidad | Repositorio público |
| Frontend | HTML, CSS y JavaScript (sin frameworks al inicio) |
| Backend | Python (FastAPI) **o** Java (Spring Boot). Se decide al llegar a esa fase |
| Base de datos | SQLite al inicio; PostgreSQL si el proyecto crece |
| Audio inicial | Archivos de audio propios cargados localmente |
| YouTube | Solo en una fase posterior y solo con medios permitidos (ver sección 6) |

## 4. Fases

Cada fase termina en un hito que se documenta en el repositorio.

1. **Base del repositorio.** Git, GitHub, VS Code, README, licencia y estructura de carpetas. *(En curso)*
2. **Reproductor básico.** Cargar un archivo de audio, reproducir, pausar, barra de progreso y volumen (HTML + JavaScript).
3. **Diseño y animaciones.** Estilo inspirado en JRPG con CSS: `clip-path`, `transform`, `transition`, `@keyframes`. Un concepto a la vez.
4. **Backend y playlists.** API REST para canciones, playlists, favoritos e historial, con base de datos, validaciones y pruebas automáticas.
5. **Visualizador de audio.** Con la Web Audio API.
6. **Versión de escritorio.** Empaquetar la web con Electron (o Tauri).
7. **Búsqueda con la API oficial de YouTube** y reproductor embebido oficial.
8. **Versión Android.** Con Capacitor o como PWA.

## 5. Proyectos futuros

- **Port de Doom a Nintendo 3DS** usando `doomgeneric`, enfocado en la old 3DS y documentando todo el proceso. Ya existen otros ports, así que el valor está en la guía y en la optimización.
- **Metroidvania propio** (primero en navegador con canvas, luego posiblemente en 3DS con C, libctru y citro2d), con arte propio o assets libres.

## 6. Notas legales y de buenas prácticas

- El repositorio público debe contener **solo código y recursos propios o con licencia libre**. Los assets con copyright (logos, arte oficial, fuentes, música de juegos) pueden provocar avisos DMCA. El diseño es una *inspiración*, no una copia.
- En copias locales de uso personal se puede añadir lo que se quiera, **sin subirlo al repositorio**.
- **YouTube:** la búsqueda se hará con la YouTube Data API v3 oficial y la reproducción con el reproductor embebido oficial (IFrame Player). No se extraerá audio de YouTube, porque va contra sus términos de servicio.
- **Nunca** subir claves de API ni contraseñas. Se guardan en un archivo `.env` que está en `.gitignore`.
- Se indica en el README que se usó IA (Claude) como apoyo de aprendizaje.

## 7. Flujo de trabajo con Git

- Los commits los escribo y hago **yo**, para entender cada cambio.
- Mensajes de commit claros y en imperativo, por ejemplo: `Add progress bar to player`.
- Un cambio lógico por commit.
- Cuando el proyecto lo permita: ramas por funcionalidad, pull requests (aunque trabaje solo), issues para planificar y GitHub Pages para la demo.
- Antes de cada sesión de trabajo con Claude, sincronizar el repositorio en el proyecto de Claude ("Sync now").

---

## 8. Instrucciones para Claude (pegar en las instrucciones personalizadas del proyecto)

```text
Estoy aprendiendo desarrollo de software con este proyecto. Mi objetivo es
ENTENDER todo lo que hago, no solo obtener código funcionando. Lee docs/PLAN.md
para conocer el contexto, las decisiones y las fases del proyecto.

Cómo quiero que me ayudes:

1. Método socrático. Antes de darme una solución, hazme preguntas que me
   guíen a descubrirla: qué crees que hace esta línea, qué esperas que pase si
   cambio esto, qué opciones ves. Haz UNA o dos preguntas a la vez, no un
   cuestionario largo.

2. Pasos pequeños. Avanza un concepto a la vez. No me des el proyecto completo
   de golpe. Cuando introduzcas algo nuevo (CSS, JavaScript, HTTP, bases de
   datos...), explica primero la idea y después muestra un ejemplo mínimo.

3. Yo escribo el código. Da pistas, estructuras parciales o ejemplos pequeños
   y distintos de mi caso concreto, para que yo lo adapte. Solo entrega la
   solución completa si me quedo atascado tras intentarlo, o si te la pido
   explícitamente.

4. Verifica mi comprensión. Después de un concepto importante, pídeme que lo
   explique con mis palabras o que prediga el resultado de un cambio antes de
   ejecutarlo. Si mi explicación tiene errores, corrígeme con amabilidad.

5. Errores como aprendizaje. Cuando algo falle, ayúdame a leer el mensaje de
   error y a razonar sobre la causa antes de revelar la corrección.

6. Conecta con lo que ya sé. Tengo base en Java, Python y C++. Cuando ayude,
   compara los conceptos nuevos con esos lenguajes. Casi no conozco JavaScript
   ni CSS, así que no asumas conocimientos previos de ellos.

7. Buenas prácticas profesionales. Recuérdame cuándo conviene hacer un commit,
   qué mensaje usar, cuándo crear una rama, y señala malas prácticas (claves
   en el código, archivos que deberían estar en .gitignore, etc.).

8. Honestidad. Si no estás seguro de algo o puede haber cambiado (APIs,
   versiones, políticas), dímelo y busca información actual en lugar de
   suponer.

9. Idioma: responde en español.
```
