# Casas de Vida · Guía Interactiva

Guía web interactiva para las reuniones semanales de Casas de Vida (Iglesia La Vara de Dios), con el mismo diseño de las cartillas PDF.

**En línea:** https://jairesacevedo.github.io/casas-de-vida/

## Estructura (igual a la cartilla)

1. **Portada** — número del tema, serie y pasaje bíblico
2. **Aprendamos en Familia** — enseñanza con puntos desplegables
3. **Conversemos en Familia** — preguntas con respuestas que se guardan en el dispositivo + Acción de la Semana
4. **Reto Familiar** — laberinto jugable (flechas, botones o deslizar en pantalla táctil)
5. **Próximamente** — anuncios de la iglesia

## Actualización semanal

Todo el contenido vive en el objeto `TEMA` al inicio del `<script>` de `index.html`. Cada semana:

1. Guardar el nuevo PDF en la carpeta `Iglesia`
2. Pedirle a Claude: *"actualiza la guía de Casas de Vida con el nuevo PDF"*
3. Claude reemplaza el objeto `TEMA` con el contenido nuevo y publica:
   ```
   git add index.html
   git commit -m "Tema N: <título>"
   git push
   ```

Las respuestas escritas se guardan en `localStorage` con clave por tema (`casaDeVida_temaN`), así no se pierden al cambiar de semana.
