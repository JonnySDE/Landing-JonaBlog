# JonaBlog · landing con Quarto

Esta es la carpeta del sitio para abrir directamente en Visual Studio Code y seguir ampliando en etapas. Sigue el diseño “Landing con color” de la captura de Figma y se adapta a pantallas pequeñas y grandes.

## Abrir y previsualizar

1. En VS Code, elige **Archivo → Abrir carpeta** y selecciona `landing-quarto`.
2. Instala Quarto y la extensión oficial de Quarto para VS Code si aún no están instalados.
3. Abre el proyecto desde su carpeta raíz y en la terminal integrada ejecuta `quarto preview`. La página inicial del sitio es `index.qmd` (la landing); el blog está dentro de `blog/` y se abre desde el botón de la landing.
4. Ejecuta `quarto render` para crear el sitio estático en `_site/`.

## Archivos

- `_quarto.yml`: navegación, nombre, metadatos y formato de publicación.
- `index.qmd`: contenido de la landing, tarjetas y formulario de contacto.
- `styles.css`: presentación visual adaptable a móvil y escritorio.
- `blog/`: inicio del blog, archivo de artículos, categorías y galería de proyectos/redes.
- `blog.css`: estilos editoriales del blog, independientes de la landing.
- `posts/`: artículos Quarto; las páginas de inicio y archivo se actualizan desde esta carpeta.
- `assets/images/`: carpeta reservada para tu retrato y capturas reales de proyectos.

## Dónde editar la información

Edita `index.qmd` para cambiar la presentación personal, estudios, habilidades, proyectos, credenciales y enlaces. Los perfiles de GitHub, LinkedIn e Instagram y el correo que compartiste ya están conectados. El formulario prepara el mensaje en Gmail.

La fotografía de perfil ya está en `assets/images/jonathan.jpg`. Las cuatro insignias cargadas se encuentran en `assets/images/badges/` y sus títulos e instituciones están en `index.qmd`.

### Añadir capturas de proyectos

Las capturas actuales ya están conectadas: `educontrol.png`, `homeScore.jpeg` y `uplace.png`. La captura vertical de Home Score se muestra completa dentro de un marco móvil; las capturas panorámicas conservan su proporción. Para reemplazarlas, conserva los nombres y cambia los archivos dentro de `assets/images/projects/`.

Para sumar un proyecto, duplica una tarjeta `<article class="other-card card">` dentro de `.other-projects`, actualiza su captura, texto, tecnologías y enlace al repositorio. El grid se ajusta automáticamente al número de tarjetas.

Para sumar una insignia, duplica una tarjeta `<article class="credential-card card">` dentro de `.credential-list` y completa el nombre, institución, aprendizajes y fecha de finalización.

El acceso de correo y el formulario abren un borrador en Gmail. El formulario lleva nombre, dirección de respuesta, asunto y mensaje; la persona revisa el borrador y elige **Enviar** desde Gmail. Debe iniciar sesión en Google para usar el compositor web.

El botón **IR AL BLOG** abre `blog/index.html`; **VOLVER AL PORTAFOLIO** regresa a `index.html`. El header, el ancho de contenido y la escala del logotipo siguen las mismas medidas entre la landing y las vistas del blog. La portada carga automáticamente las entradas recientes desde `posts/`. El archivo de artículos ofrece búsqueda y filtros por categoría; la página de categorías abre ese archivo con el filtro correspondiente, y muestra un aviso si aún no hay entradas. Social Media reúne capturas, redes y rutas de aprendizaje.

### Publicar una entrada nueva cada semana

1. Crea `posts/AAAA-MM-DD-titulo.qmd` duplicando una entrada existente.
2. Actualiza `title`, `description`, `author`, `date`, `image`, `image-alt` y `categories` en el bloque YAML.
3. Usa únicamente estas categorías: `Python`, `FastAPI`, `React` o `Kotlin`. Los casos que no pertenezcan a ellas pueden llevar `categories: []`; seguirán apareciendo en el inicio y en “Todos”, pero no dentro de un filtro tecnológico.
4. Agrega la portada a `assets/images/` y actualiza la ruta en `image` y en la imagen principal del artículo.
5. Escribe el contenido con Markdown y conserva el bloque de navegación/relacionados al final, actualizando los enlaces según corresponda.
6. Ejecuta `quarto preview` para revisar en local y `quarto render` antes de desplegar.

Las cuatro imágenes de las tarjetas temáticas están en `assets/images/category/`. Los proyectos iniciales conservan sus tecnologías reales: EduControl no recibe una categoría técnica; Home Score se etiqueta Kotlin y UPlace React. Python y FastAPI mostrarán un aviso de “Aún no hay artículos” hasta que agregues una entrada con esa categoría.

Antes del despliegue, configura `site-url` en `_quarto.yml` con el dominio definitivo para habilitar el feed RSS del blog; luego genera `_site/` con `quarto render`. La carpeta `_site/` es la que se publica en GitHub Pages, Netlify u otro alojamiento estático.
