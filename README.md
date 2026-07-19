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

## Deploy

Conectada a Vercel: cada push a `main` redespliega automáticamente.

---

Hacemos fácil cuidar de quienes nos cuidaron.
