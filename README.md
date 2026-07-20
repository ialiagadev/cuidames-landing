# Cuidames — Landing (lista de espera)

Landing de **Cuidames**: cuidar a los mayores empezando por su televisión.
Diseño v2 (Claude Design) convertido a HTML puro y autocontenido.

## Estructura

```
index.html            → la página (autocontenida: estilos y JS dentro)
assets/logo.jpeg      → logo
assets/foto-*.svg     → ilustraciones (hero, recuerdos, familia)
favicon.svg           → icono
```

Sin build ni dependencias. Doble clic o cualquier servidor estático.

## Lista de espera → Supabase

El formulario inserta en la tabla `waitlist` del proyecto **cuidames** de Supabase
(RLS insert-only: la clave anónima solo permite apuntarse; **los correos no se pueden
leer** con ella). Duplicados → mensaje "ya estabas en la lista".

**Ver los apuntados:** Supabase → Table Editor → `waitlist` (o con la clave service_role).

## Píxel de Meta (para la campaña de ads)

Ya está instalado y **desactivado por defecto**. Para activarlo cuando lances la campaña:

1. Crea la cuenta en [business.facebook.com](https://business.facebook.com) → Events Manager → **Crear píxel** → copia el ID (solo números).
2. En `index.html`, busca `const META_PIXEL_ID = "";` y pega el ID.
3. Push → Vercel despliega. Listo.

Cómo funciona:
- **Sin ID** → no se carga nada ni aparece el banner (cero cookies).
- **Con ID** → aparece el banner de cookies (RGPD): el píxel **solo se carga si el visitante acepta**.
- Al apuntarse alguien a la lista se dispara el evento **`Lead`** → configura la campaña optimizada a "Clientes potenciales (Lead)" para que Meta busque gente que se registre, no solo que haga clic.

## Deploy

Conectada a Vercel: cada push a `main` redespliega automáticamente.

---

Hacemos fácil cuidar de quienes nos cuidaron.
