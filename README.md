# Casas de Vida · Guía Interactiva

Guía web interactiva para las reuniones semanales de Casas de Vida (Iglesia La Vara de Dios), con el mismo diseño de las cartillas PDF.

**📱 En línea:** https://jairesacevedo.github.io/casas-de-vida/
*(el enlace nunca cambia: guárdalo como favorito o compártelo)*

## Estructura (igual a la cartilla)

1. **Portada** — número del tema, serie y pasaje bíblico
2. **Aprendamos en Familia** — enseñanza con puntos desplegables
3. **Conversemos en Familia** — preguntas con respuestas que se guardan en el dispositivo + Acción de la Semana
4. **Reto Familiar** — cambia según la cartilla de la semana:
   - 🌀 **Laberinto** jugable (flechas, botones o deslizar en pantalla táctil)
   - 🔤 **Sopa de letras** interactiva (arrastra el dedo sobre las palabras)
5. **Próximamente** — anuncios de la iglesia

## Actualización semanal

Todo el contenido vive en el objeto `TEMA` al inicio del `<script>` de `index.html`. El diseño nunca se toca: cada semana solo se reemplaza ese bloque con el contenido del nuevo PDF.

### Opción 1 · Hazlo tú mismo (recomendado)

Sigue el manual paso a paso: **[COMO-ACTUALIZAR.md](COMO-ACTUALIZAR.md)**.
Todo se hace desde el navegador con el lápiz ✏️ de GitHub — sin instalar nada.

### Opción 2 · Pídeselo a Claude

Guarda el nuevo PDF en la carpeta `TRABAJO\Iglesia` del computador y dile:
*"actualiza la guía de Casas de Vida con el nuevo PDF"*.
Útil también cuando la cartilla trae un tipo de reto nuevo (crucigrama,
apareamiento, etc.), porque eso sí requiere programar.

## Detalles técnicos

- Un solo archivo (`index.html`): HTML + CSS + JavaScript, sin dependencias.
- Publicado con **GitHub Pages** desde la rama `main`; cada commit republica solo en 1–2 minutos.
- Las respuestas escritas se guardan en el dispositivo de cada persona (`localStorage`), con una llave por tema (`casaDeVida_temaN`): el material nuevo no borra lo de semanas anteriores.
- El historial completo de versiones está en la pestaña [Commits](https://github.com/jairesacevedo/casas-de-vida/commits/main) — cualquier versión anterior se puede restaurar (ver la sección 🚑 del manual).
