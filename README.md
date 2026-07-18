# Cuidames — Landing (lista de espera)

Landing para validar la demanda de **Cuidames**, la marca que hace fácil cuidar de las personas mayores.
Primer producto: convertir la **televisión** de tus padres en la forma más sencilla de estar presente
(arreglar su tele desde el móvil, videollamadas que entran solas en su pantalla, recordatorios y fotos).

> **Objetivo de esta página:** medir cuánta gente se apunta a la lista de espera. Es un **test de demanda**, no el producto.

## Estructura

```
index.html     → la página (una sola)
styles.css     → estilos (paleta e identidad de Cuidames)
favicon.svg    → icono
```

No hay build ni dependencias: es HTML/CSS/JS puro. Ábrelo con doble clic o sírvelo con cualquier servidor estático.

## Conectar el formulario (para recibir los correos)

Por defecto, el formulario funciona en **modo demo** (muestra "¡Gracias!" pero no guarda el correo).
Para recibir de verdad los registros, elige una opción:

### Opción A — Formspree (lo más rápido, sin backend)
1. Crea un formulario gratis en <https://formspree.io> y copia tu endpoint (`https://formspree.io/f/xxxxxx`).
2. En `index.html`, busca `const FORMSPREE_ENDPOINT = "";` y pega ahí tu endpoint.

### Opción B — Supabase
Crea una tabla `waitlist (id, email, created_at)` y sustituye el `fetch` del `<script>` por una llamada a tu API de Supabase (`supabase.from('waitlist').insert(...)`).

## Publicarla (gratis)

- **Vercel** o **Netlify:** conecta este repo y despliega (detecta que es estático). Recomendado.
- **GitHub Pages:** Settings → Pages → Deploy from branch `main` / carpeta raíz.

## Medir

Para saber si la idea engancha, añade analítica (p. ej. [Plausible](https://plausible.io) o [Umami](https://umami.is)) y mira la conversión: **visitas → registros**. Un buen registro vale más que mil "me gusta".

---

Hacemos fácil cuidar de quienes nos cuidaron.
