# Cómo actualizar la guía cada semana (hazlo tú mismo)

No necesitas instalar nada: todo se hace desde el navegador, en GitHub.
Tiempo estimado: 15–20 minutos con el PDF al lado.

---

## Paso 1 · Abre el editor

1. Entra a **github.com/jairesacevedo/casas-de-vida** (con tu sesión iniciada).
2. Haz clic en el archivo **`index.html`**.
3. Arriba a la derecha del archivo, haz clic en el **lápiz ✏️** ("Edit this file").

## Paso 2 · Encuentra el bloque del contenido

Presiona **Ctrl + F** dentro del editor y busca:

```
const TEMA
```

Todo lo que vas a cambiar está entre `const TEMA = {` y el comentario
`/* ============ FIN DEL CONTENIDO SEMANAL ============ */`.
**No toques nada fuera de ese bloque.**

## Paso 3 · Reemplaza campo por campo con el PDF al lado

El bloque es un "formulario". Cambia solo lo que está **entre comillas** (y los números):

| Campo | Qué va ahí (según el PDF) |
|---|---|
| `numero` | El número grande del tema (sin comillas: `numero: 4,`) |
| `serie` | El nombre de la serie (ej. "La Casa es de Todos"), va debajo del número |
| `tituloLinea1` y `tituloLinea2` | El título partido en dos renglones |
| `etiquetas.paso1` / `etiquetas.paso2` | *Opcional.* Solo si esta semana la cartilla llama distinto a las secciones (ej. "Hablemos en Familia" en vez de "Aprendamos en Familia"). Si no lo pones, usa los nombres de siempre |
| `pasaje.ref` | La cita, ej. `"JUAN 13:13-17"` |
| `pasaje.versos` | Un renglón `{ n: 13, t: "texto..." },` por cada versículo. Si la cartilla trae una sola frase sin número, usa `{ n: "", t: "texto..." }` |
| `intro` | Los párrafos de la enseñanza (paso 1), uno por comillas |
| `preguntaReflexion` | *Opcional.* Si en medio de la enseñanza hay una pregunta destacada en un recuadro, va aquí |
| `subtituloPuntos` | El subtítulo verde antes de los puntos |
| `puntos` | Cada punto numerado con su título, cita y párrafos |
| `conclusion` | Los párrafos de la conclusión. Si el PDF no trae conclusión esta semana, déjalo como lista vacía: `conclusion: [],` — el bloque se oculta solo |
| `preguntas` | Las 3 preguntas del paso 2 |
| `accionSemana` | El texto de la Acción de la Semana |
| `fraseDestacada` | *Opcional.* La frase resumen en letra grande que a veces trae la cartilla al final (tipo cita destacada) |
| `oracion` | *Opcional.* Si la cartilla trae una oración de cierre, va aquí completa |
| `reto` | Ver abajo según el tipo de reto |
| `anuncios` | Los anuncios de "Próximamente" (si el PDF no trae, deja los vigentes y borra los de fechas pasadas) |

Los campos marcados *Opcional* se pueden borrar por completo del objeto `TEMA`
si esta semana no aplican (no hace falta dejarlos vacíos).

### El reto familiar

**Si la cartilla trae sopa de letras:**
```js
reto: {
  tipo: "sopa",
  instruccion: "Encuentra las palabras clave",
  palabras: ["PALABRA1", "PALABRA2", "PALABRA3"],
  mensajeWin: "¡Encontraron todas las palabras! ¡Reto completado en familia!"
},
```

**Si trae laberinto:**
```js
reto: {
  tipo: "laberinto",
  instruccion: "Ayuda a ... a llegar a ...",
  emojiJugador: "🚶",
  emojiMeta: "✝️",
  mensajeWin: "¡Llegaron a la meta! ¡Reto completado en familia!"
},
```

**Si trae una lámina para colorear:**
```js
reto: {
  tipo: "colorear",
  instruccion: "Pinten juntos esta escena en familia"
},
```
Este tipo muestra una ilustración propia (no es una copia exacta del dibujo del
PDF, por derechos de autor) con una paleta de 10 colores para pintar tocando
cada parte. Sirve para cualquier semana con reto de colorear, sin importar el tema.

**Si trae otra cosa** (crucigrama, apareamiento…): pídele a Claude que cree el
tipo nuevo — la página solo sabe hacer laberintos, sopas de letras y láminas para colorear.

### Las 5 reglas de oro (lo que evita que la página se rompa)

1. Cambia **solo el texto entre comillas** `"..."` y los números.
2. Cada elemento de una lista termina en **coma**, excepto el último antes de `]` o `}`.
3. **No borres** llaves `{ }`, corchetes `[ ]` ni comillas.
4. Dentro de un texto **no uses comillas dobles** `"` — usa comillas angulares `« »` o apóstrofo `'`.
5. Para agregar o quitar versículos/puntos/preguntas, **copia un renglón completo existente** (con su coma) y edítalo.

Tildes, eñes y signos ¿? ¡! van sin problema. También puedes usar `<b>negrilla</b>`
y `<em>cursiva</em>` dentro de los textos.

## Paso 4 · Guarda (commit)

1. Botón verde **"Commit changes..."** (arriba a la derecha).
2. En el mensaje escribe algo descriptivo, ej.: `Tema 4: El poder de servir`.
3. Deja marcado "Commit directly to the main branch" y confirma.

Ese "commit" es la fotografía nueva del archivo: queda en el historial para siempre.

## Paso 5 · Verifica

1. Espera 1–2 minutos (GitHub Pages republica solo).
2. Abre **jairesacevedo.github.io/casas-de-vida** y recarga:
   - En PC: `Ctrl + F5`
   - En celular: arrastra la página hacia abajo
3. Recorre las 5 pantallas completas antes de la reunión: portada, enseñanza,
   preguntas, reto y anuncios.

## Si la página queda en blanco o se ve rara 🚑

Casi siempre es una comilla o coma fuera de lugar. Para volver a la versión anterior:

1. En el repositorio, clic en **"Commits"** (el relojito con la lista de cambios).
2. Clic en el commit **anterior** al tuyo (el que sí funcionaba).
3. Clic en **"Browse files"** → abre `index.html` → botón **"Raw"** → selecciona todo y copia (`Ctrl+A`, `Ctrl+C`).
4. Vuelve a la rama main, edita `index.html` con el lápiz, borra todo, pega y haz commit: `restaurar versión anterior`.

Y si no encuentras el error, dile a Claude: *"la guía de Casas de Vida quedó rota,
revisa el último commit"* — con el historial de Git nada se pierde.
