# El Pulso

Plataforma web de noticias de demostración para la Entrega 2 - Semana 5 del módulo Desarrollo de Front-end del Politécnico Grancolombiano.

## Ejecutar

La aplicación carga noticias desde `data/news.json`, por lo que debe abrirse mediante un servidor local y no directamente con `file://`.

```bash
python3 -m http.server 8000
```

Luego visita `http://localhost:8000` en el navegador.

## Estructura

- `index.html`: punto de entrada y estructura compartida.
- `styles.css`: estilos responsive de la plataforma.
- `js/app.js`: enrutamiento por hash, renderizado, favoritos, formulario y mini CRUD.
- `data/news.json`: catálogo inicial de noticias ficticias.
- `mockups/`: maquetas originales de BOCA, conservadas sin modificaciones.

## Funcionalidades

Inicio editorial, catálogo filtrable, detalle de noticia, favoritos persistentes con `localStorage`, formulario de contacto con validación y administración local para crear o eliminar noticias. Los cambios del CRUD se guardan únicamente en el navegador; no existe backend ni base de datos.

Las fotografías del catálogo se cargan desde URLs estables de Unsplash y se usan como imágenes de referencia para contenido ficticio académico.