# El Pulso

Plataforma web de noticias de demostración para la Entrega 2 - Semana 5 del módulo Desarrollo de Front-end del Politécnico Grancolombiano.

## Ejecución

La aplicación carga `data/news.json` mediante `fetch`, por lo que debe abrirse con un servidor local y no directamente con `file://`.

```bash
python3 -m http.server 8000
```

Después visita `http://localhost:8000`.

## Estructura del proyecto

```text
front/
├── index.html                         # Entrada de la aplicación dinámica.
├── styles.css                         # Sistema visual compartido y responsive.
├── js/app.js                          # Estado, rutas hash, renderizado e interacciones.
├── data/news.json                     # Catálogo inicial de noticias.
├── mockups/
│   ├── inicio/inicio.html             # Portada estática de demostración.
│   ├── noticias/noticias.html         # Catálogo estático con cards.
│   ├── detalle/detalle.html           # Detalle estático con favorito local.
│   ├── favoritos/favoritos.html       # Lista estática alimentada por localStorage.
│   └── contacto/contacto.html         # Formulario de contacto local.
└── mockups/*/style.css                # Hojas CSS originales conservadas.
```

## Funcionalidades implementadas

- Home editorial con bienvenida, noticias destacadas, llamados a la acción y footer.
- Catálogo dinámico: `js/app.js` obtiene las noticias desde `data/news.json` con `fetch` y genera las cards desde plantillas HTML.
- Detalle dinámico: muestra categoría, fecha, autor, imagen y contenido completo mediante la ruta `#noticia/id`.
- Favoritos: guarda IDs en `localStorage`, permite agregarlos o quitarlos y muestra una vista vacía cuando no existen.
- Contacto: valida nombre, correo, asunto y mensaje en el navegador. Confirma la validación, pero no envía datos porque no hay backend.
- Mini CRUD local: permite crear y eliminar noticias. Las noticias creadas y eliminadas se conservan en `localStorage`.
- Navegación por hash: `route()` interpreta `#inicio`, `#noticias`, `#noticia/id`, `#favoritos`, `#contacto` y `#admin` sin recargar la página.
- Mockups estáticos: las cinco páginas dentro de `mockups/` sirven como maquetación navegable y reutilizan `styles.css`.

## Descripción del JSON

`data/news.json` es un arreglo de objetos. Cada noticia contiene `id`, `category`, `title`, `excerpt`, `content`, `author`, `date`, `image` e `imageAlt`. El formato JSON estándar no admite comentarios; esta descripción documenta su contrato sin alterar los datos.

## Documentación agregada al código

Se añadieron comentarios profesionales en español a:

- `index.html`: inclusión de CSS y JavaScript, encabezado, contenedor dinámico y footer.
- `js/app.js`: claves de almacenamiento, carga de datos, plantillas, vistas, favoritos, validación, CRUD, navegación hash e inicialización.
- `styles.css`: propósito general de variables, estilos base, componentes y responsive.
- `mockups/*/*.html`: estructura de cada vista, navegación y scripts locales.
- `mockups/*/style.css`: propósito de las hojas CSS originales conservadas.

Los comentarios explican decisiones y relaciones entre partes; no describen operaciones obvias del lenguaje.

## Estado y limitaciones conocidas

- No existe backend, base de datos ni autenticación. El contacto, favoritos y CRUD son demostraciones locales del navegador.
- Las imágenes se cargan desde URLs de Unsplash; requieren conexión a internet para visualizarse.
- Los mockups estáticos muestran contenido de demostración y el detalle estático corresponde a una noticia fija. La experiencia completa y dinámica está en `index.html` con `js/app.js`.
- Las hojas `mockups/*/style.css` son estilos originales conservados, pero las vistas actuales enlazan `../../styles.css` para mantener una identidad visual común.
- Las noticias de `data/news.json` son contenido ficticio académico y están identificadas como demostración dentro de los textos.

## Recomendaciones para la entrega

1. Ejecutar la aplicación mediante el servidor local indicado y tomar capturas de Home, catálogo, detalle, favoritos, contacto y administración.
2. Mostrar en el informe que `localStorage` reemplaza temporalmente una base de datos en esta entrega.
3. Mantener la distinción entre las vistas estáticas de `mockups/` y la aplicación dinámica de la raíz para explicar la evolución de la maquetación a la funcionalidad.
4. Si el proyecto continúa creciendo, separar las plantillas de vistas y la gestión de estado en módulos JavaScript, sin cambiar el comportamiento actual durante esta entrega.
