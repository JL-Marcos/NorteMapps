# NorteMapps

José Luis Marcos Silva · Realidades Extendidas y Experiencias Inmersivas · UGM · 2026

## 1 · Qué es

NorteMapps es una cartografía narrativa navegable de «La Norte Maps», proyecto de la Cooperativa de Relatos en la población Norte Grande (Valdivia). En vez de leer los relatos como archivos sueltos (murales, Instagram, documentos), el visitante recorre un mapa 3D del barrio en el navegador, recoge cassettes con relatos reales en audio, los guarda en una radio y reconstruye el mural pintado en el gimnasio. Está pensado para niñas, niños y jóvenes que participaron en las actividades de la Cooperativa, y para artistas e investigadores interesados en metodologías participativas (usuarios identificados en la Solemne 1). No requiere visor.

- Palabra que busco transmitir: **explorar** (el visitante recorre el barrio, descubre los cassettes y los relatos del territorio; la cartografía es el medio, la exploración es la experiencia).

## 2 · Cómo se usa

- Enlace a la escena: https://jl-marcos.github.io/NorteMapps/
- Dispositivo pensado: computador con mouse y teclado (principal). También funciona en teléfono: probado en un Huawei Y9s (Android, navegador Opera) y en un iPhone 17. El joystick en pantalla camina y arrastrar el dedo mira.
- Al entrar: el visitante aparece dentro de la radio (CECOF). Un tutorial le pide tocar el cassette de la mesa, tocar la radio para guardarlo y salir por la puerta marcada SALIDA.
- Afuera: recorre el barrio y toca los cassettes (2 a 6 clics, según el relato) para llevarlos en la mano. Mientras los lleva puede escucharlos en el **reproductor portátil** (abajo, al centro). Al tocar la radio los deposita y se enciende un punto verde en el mural del gimnasio. El botón **CC** activa los subtítulos (hoy solo el relato de la radio los tiene).
- Dentro de la radio, los relatos depositados quedan en la **repisa** y se escuchan al tocarlos. Con los 9 relatos reunidos se desbloquea el documental en la pantalla del gimnasio (frente a las gradas).
- Misión secundaria: recoger 5 montones de basura, depositarlos en los contenedores verdes y ver el videoclip «NORTE FLOW» en la pantalla de la cancha, detrás del gimnasio.
- Controles: W A S D y mouse (computador); joystick y arrastre del dedo (teléfono). Botón «Reiniciar» para volver a empezar; botón de pantalla completa (abajo a la derecha).

## 3 · Cómo está hecha

- Herramientas: A-Frame 1.7.0 (WebXR declarativo) con componentes propios en JavaScript dentro de `index.html`; publicado en GitHub Pages con HTTPS. Transcripciones con faster-whisper 1.2.1 (licencia MIT, según los metadatos del paquete instalado).
- Archivos que usé:

| Archivo | Qué es | Origen | Licencia |
|---|---|---|---|
| `index.html` | Escena y componentes | Escrito con un agente de código (Claude, vía Hermes) a partir de mis indicaciones | Obra del proyecto, sin material de terceros |
| A-Frame 1.7.0 (no está en el repo; se carga desde `aframe.io/releases/1.7.0/`) | Librería | aframe.io | MIT (verificado en el archivo LICENSE del código fuente) |
| `activos/radio.glb` | Modelo 3D de la radio | Generado con Claude (IA) a pedido mío; los metadatos del archivo indican que se construyó por código con la librería trimesh | Sin licencia de terceros. Anthropic asigna al usuario sus derechos sobre los resultados («we assign to you all of our right, title, and interest—if any—in Outputs», Condiciones del consumidor, §4) |
| `activos/texturas/panel.jpg`, `pared-gimnasio.jpg`, `piso-gimnasio.jpg`, `repisa.png` | Texturas de las salas | Generadas en Vizcom con mi cuenta de estudiante (Education); optimizadas a 512 px (la repisa, 1024 px) | Vizcom: conservo la propiedad de los diseños generados con una cuenta Education, pensada para uso académico y no comercial; Vizcom puede usar los diseños para mejorar sus servicios (Términos de servicio, §3.2, consultados el 16-nov-2026) |
| `activos/golpe.mp3`, `activos/campana.mp3` | Sonidos cortos de clic y de soltar el cassette | Entregados por el profesor | Licencia por confirmar |
| `activos/gimnasio.mp3`, `cecof.mp3`, `huerta.mp3`, `perritos.mp3`, `cancha.mp3`, `comida-rapida.mp3`, `locomocion.mp3`, `radio.mp3` | Los 8 relatos en audio | Cooperativa de Relatos | Uso autorizado: soy integrante de la Cooperativa y tengo su autorización para trabajarlos |
| `activos/mural/mural-completo.jpg` | Foto del mural «NORTE MAPS» del gimnasio | Cooperativa de Relatos | Uso autorizado (integrante de la Cooperativa) |
| `activos/norte-maps-datos.js` | Puntos, calles y territorio | Google My Maps de la Cooperativa; edificios © colaboradores de OpenStreetMap | Edificios: ODbL. Puntos, calles y territorio: de la Cooperativa de Relatos, de la que soy integrante (uso autorizado) |
| `activos/transcripciones/radio.json`, `.txt`, `.vtt` | Subtítulos y transcripción del relato de la radio | Generados con faster-whisper (modelo `small`) y corregidos a mano por mí | El texto es el relato de la Cooperativa (uso autorizado). Whisper (OpenAI): código con licencia MIT; el modelo `small` usado a través de faster-whisper está publicado con licencia MIT (conversión de Systran) a partir de `openai/whisper-small` (Apache-2.0), según sus fichas en Hugging Face (consultadas el 18-nov-2026). Los archivos del repo son copias que corregí a mano, no la salida directa del modelo |
| Videoclip «NORTE FLOW» | Se abre desde la pantalla de la cancha | Escuela Documentales de Barrio, YouTube: https://youtu.be/nb0cvkEZ2zg?t=567 (desde 9:27) | Se incrusta desde YouTube, no se aloja aquí |
| Documental | Se abre desde la pantalla del gimnasio | YouTube: https://youtu.be/S1ep6XOCqaQ | Se incrusta desde YouTube, no se aloja aquí |

- El resto (calles, edificios, árboles, humedal, vehículos, perritos, cielo, casas) se genera por código; no hay archivos de imagen ni de modelo para ellos.
- Peso de `activos/`: ≈ 27,3 MB, de los cuales ≈ 26,2 MB son los 8 relatos. Es mayor que los 5 MB que sugiere la guía de la Sesión 8 (ver sección 7).

## 4 · Decisiones

- **Escala 1:5** con altura de cámara proporcional: a escala 1:1 el barrio se sentía enorme.
- **Cassette como unidad de relato**: se extrae con clics, se lleva en la mano, se escucha con el reproductor portátil y se guarda en la radio. El video (documental) solo se desbloquea al depositar los 9 relatos en la radio.
- **Parte clave de mi proyecto (criterio A3): el origen, es decir, la radio y el tutorial que ocurre dentro de ella.** El visitante parte en la radio, donde están los relatos y donde el tutorial le muestra la mecánica (tomar el cassette, dejarlo en la radio, salir). Ahí la propuesta de emisión queda relativamente clara: al dejar un relato en la radio aparece la posibilidad de juntar los otros y ver qué sucede. Esa es la apuesta y la intención de la experiencia. Lo elegí porque en el origen se determina la misión y de ahí se abre el mundo abierto que he venido desarrollando; y el hecho de que los relatos estén distribuidos por el mapa es lo que genera la sensación de **explorar**.
- **Gimnasio y CECOF** modelados como volúmenes con la forma medida sobre imágenes de referencia; puertas por fuera de la cara a la calle y salas cerradas, con el tamaño del volumen exterior (el gimnasio mide 22,1 × 30,3 m). Las alturas son estimadas.
- **Luz, sonido y materiales** (apoyan «explorar»): luz focal sobre la radio, la repisa y el mural, para guiar la mirada; el golpe al tocar el cassette y la campana al depositarlo son sonidos posicionales; texturas de panel y de piso en las salas.
- **Los relatos acompañan al visitante (decisión)**: la idea original era que el visitante portara algo como una grabadora. Por eso los relatos no son posicionales: se escuchan desde el reproductor portátil que lleva consigo, o desde la radio y la repisa. El sonido posicional de los relatos y el audio ambiental los abordo en la próxima entrega.
- **Texturas con Vizcom** para dar carácter a las salas sin aumentar el peso.
- **Ambientación** (humedal con totora, vegetación del borde, casas de colores con ventanas, colectivos y un bus que circulan, autos estacionados, perritos, multicancha, carrito de comida rápida, almacén «El Narigón») para que el mapa no se sintiera vacío. Las posiciones se calibraron con los íconos del mapa referencial; varias son estimadas.
- **Colisión por la huella exacta de cada edificio**, no por círculos, porque con círculos se podía entrar por las esquinas.
- **Pantalla completa de toda la página**, porque con la de A-Frame el video quedaba oculto.
- **Cambios respecto de la Solemne 1**:
  - Prometí 2 a 4 unidades narrativas; el prototipo tiene 8 relatos más el documental y el videoclip.
  - Prometí texto, imagen y audio; el texto alternativo se implementó como **subtítulos y transcripción**: generados con Whisper y **corregidos por mí, integrante de la Cooperativa**. Hoy solo el relato de la radio está revisado y subtitulado (botón CC).
  - Prometí computador como dispositivo principal; se agregó control táctil para teléfono.
  - El hito de «primera prueba de usuario» estaba comprometido para el 21-oct en la Solemne 1. Esa fecha se desplazó: las pruebas en teléfono se hicieron el 4 de noviembre y las del computador el 28 de octubre.

## 5 · Testing

Video del recorrido: https://youtu.be/iBC2ZpKEoyQ (YouTube, no listado)

El video dura 5 min 42 s, más que los 2 a 4 minutos de la guía. Regrabé para acortarlo, pero la escena tiene varias interacciones (tutorial, relatos, reproductor, subtítulos, mural, pantalla, basura, videoclip) y no alcanzaba a mostrarlas todas en menos tiempo. Prioricé mostrar cada interacción.

Quién probó: «PC» lo probó el asistente en un navegador controlado por él, sobre las versiones locales que luego se publicaron (la última publicada es `37d9044`); no es una prueba de usuario. «Android» lo prueba José en su teléfono.

### Abrir el enlace en ventana privada
- Resultado: carga en ventana privada en mi Huawei Y9s (Opera) y también en una pestaña privada en el computador. Además, el asistente comprobó con peticiones HTTP que el enlace sirve la versión `37d9044` con sus 11 recursos principales.
- Ajuste que hice: ninguno.

### Dispositivo elegido
- Resultado: Huawei Y9s con Opera. El joystick y el botón de correr (») funcionan. El botón de correr no acelera tanto como en el computador, pero sirve y se siente más orgánico. En la versión del 4-nov el botón de correr no respondía.
- Ajuste que hice: el botón de correr pasó de `click` a `pointerdown`; con eso funciona en el teléfono.

### Interacciones, una por una

| Interacción | PC (asistente) | Android (José) |
|---|---|---|
| Tutorial: cassette → radio → salida | Probado: los tres estados y la salida | Funciona: se completa |
| Puertas de las dos salas (entrar y salir) | Probado | Funciona |
| Extraer un cassette con clics | Probado en sesiones anteriores | Funciona |
| Depositar en la radio y encender el punto del mural | Probado | Funciona; los puntos calzan con los íconos |
| Reproductor portátil (reproducir, pausar, siguiente) | Probado | Funciona: suena |
| Botón CC y subtítulos de la radio | Probado: se ven en sus tiempos y se apagan | Funciona: se ven los subtítulos |
| Repisa del CECOF: tocar un relato depositado | No probado | Funciona |
| Misión de basura y contenedores | Probada en sesiones anteriores | Funciona |
| Video en pantalla completa | Probado abriendo el modal en pantalla completa; no probado el clic sobre la pantalla del gimnasio | Funciona |

- Ajuste que hice: el video no se veía en pantalla completa en el computador. Causa: el botón de pantalla completa de A-Frame pone solo el dibujo 3D en pantalla completa y deja oculto el resto de la página, incluida la ventana del video. Arreglo: un componente propio (`pantalla-completa-pagina`, en `index.html`) que lleva esa petición a la página entera. Con él la ventana del video se ve en pantalla completa; funciona en el computador y en el Android.
- Falla identificada y corregida: al pegarse a la pared de una casa se podía mirar hacia su interior (no se entra en ella). Causa: el margen de colisión con las casas (0,1 unidades de escena) era igual al plano cercano de la cámara (`near: 0.1`), así que muy pegado a una pared parte de ella no se dibujaba. En el video lo probé cambiando `near` desde el navegador; el valor que dejé es `near: 0.03`, y con eso dejé de ver el interior. Ese valor ya está en `index.html`. Lo probé de dos maneras: con el agente en un navegador, mirando una pared y una vista abierta del barrio sin parpadeos visibles, y en vivo durante la grabación del video. No lo probé en el teléfono.

### Sonido con audífonos
- Resultado: con audífonos en el computador, el sonido de los objetos (golpe y campana) se oye del lado donde aparece el objeto. No comprobé si el volumen baja al alejarse.
- Ajuste que hice: ninguno.

### Fluidez del recorrido
- Resultado: en el PC la escena marca entre 40.000 y 51.500 triángulos y entre 88 y 433 llamadas de dibujo según el lugar; el gimnasio (50.122) y el CECOF (51.460) superan levemente el margen de 50.000 que me propuse. No medí fluidez (fps) ni en el PC ni en el teléfono. En el Huawei Y9s (Opera) el recorrido funciona, pero **dentro del gimnasio se pone un poco más lento**.
- Ajuste que hice: ninguno todavía; queda como pendiente (sección 7).

### Entrar como si fuera la primera vez
- Resultado: el 4 de noviembre lo probó un amigo en un iPhone 17, con la versión publicada ese día (anterior a la actual). Entró sin indicaciones, se desplazó, movió cosas y recorrió el mapa; funcionó. Además salió del área construida y se fue muy lejos del barrio.
- Ajuste que hice: de esa observación surgió la idea de cerrar el mapa a lo jugable; queda como pendiente (sección 7).

## 6 · Uso de IA

- **Qué le pedí a la IA**:
  - **Claude (agente de código, vía Hermes):** escribió la mayor parte del código de `index.html` (conversión de coordenadas del mapa, edificios, colisión, cassettes, salas, vehículos, joystick, cielo, misión de basura, reproductor, subtítulos); creó ejemplos de los ejercicios de las guías de clase y un informe comparativo guías vs. código; y generó el modelo `radio.glb`.
  - **Vizcom:** las texturas de las salas.
  - **Whisper (faster-whisper):** la transcripción automática de los relatos, que luego corregí a mano.
  - En la Solemne 1 declaré ChatGPT y Claude para organizar el documento.
- **Qué hice yo**:
  - **La idea y su traducción:** desarrollé la idea del mapa de recorrido y la conceptualización de «explorar»: cómo se traduce la cartografía situada, el trabajo con la comunidad, a esta plataforma digital.
  - **La investigación:** la entrevista a la Cooperativa (en este caso, entrevisté a una colega, otra persona que participa en ella) y la comprensión de su trabajo.
  - **La mecánica de juego**, que fui mejorando a medida que exploraba la escena: recolectar los cassettes, tener un punto de encuentro donde se guardan (la radio) y que eso active cosas en el mural hasta desbloquear el video.
  - **La escala y la proporción**, decididas por la sensación de navegación que tenía al recorrer el mapa.
  - **La posición de las cosas en el mapa:** hubo un traspaso automático del mapa al código, pero situar algunas cosas fue una decisión humana.
  - **Decidir qué cambia en cada versión**, subiendo y construyendo de forma gradual, y aportar las imágenes de referencia.
  - **Probar cada versión en el PC y en el teléfono**, porque se comportan distinto en los dos.
  - **Corregir las transcripciones:** los subtítulos los generó Whisper y necesitan corrección manual; corregí a mano la primera (la de la radio).
  - **Decidir qué se publica y qué no**, es decir, cuándo se hace cada commit y push.
- **Qué hizo la IA**: ver el primer punto de esta sección. El código lo escribió el agente a partir de mis indicaciones y mis decisiones.
- **Poder explicar y modificar el proyecto en vivo**: el proyecto se hizo con un agente de código y es mucho más largo que los ejercicios de clase, que son puntuales y apuntan a situaciones muy concretas. Por eso `index.html` está lleno de comentarios que explican cada parte; ahí me apoyo para entender la extensión del código y para ubicar lo que quiero explicar o modificar.

## 7 · Pendientes para el examen

Quedaron fuera de esta entrega a propósito: son parte del proyecto, pero no de la Solemne 2. Están en el orden en que pienso abordarlos.

- Subtítulos y transcripción de los otros 7 relatos (la herramienta ya existe en `herramientas/subtitulos/`).
- Audio ambiental del barrio y sonido posicional de los relatos (hoy solo suenan posicionalmente el golpe y la campana).
- Interacciones menores con los lugares (por ejemplo, con la huerta) para darles más carácter.
- Cierre o límite del mapa a lo jugable: en la prueba con un iPhone, el visitante salió del área construida y se fue muy lejos.
- Mejorar la fluidez del gimnasio en teléfono (se pone más lento en un Huawei Y9s con Opera; el gimnasio y el CECOF superan levemente los 50.000 triángulos).
- Reducir el peso de los audios (≈ 26 MB frente a los 5 MB que sugiere la guía de la Sesión 8).
- Niebla progresiva con la recolección.
- Texturas de suelo con mis fotos de calle.
- Limpieza hecha: se quitaron del repo los archivos que la escena no usa (`silla.glb`, `relieve.png` y los 9 recortes del mural).
