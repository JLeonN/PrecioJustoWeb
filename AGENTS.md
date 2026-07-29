# Instrucciones del Proyecto

## Propósito

- Este repositorio contiene la web pública de presentación de Precio Justo.
- Es una landing page simple, rápida, accesible y responsive, enfocada en llevar a la descarga desde Google Play.

## Tecnología

- Usar Vue 3 con Quasar CLI y Vite.
- Para iniciar el entorno local, usar `quasar dev`.
- Para construir la versión de producción, usar `quasar build`.
- Preparar el despliegue estático automático en GitHub Pages mediante GitHub Actions cuando el repositorio remoto esté creado.
- No agregar backend, Capacitor, Android, autenticación ni dependencias que no aporten directamente a la web pública salvo que Leo lo pida.

## Diseño y experiencia

- Priorizar la experiencia móvil y verificar que la web se adapte correctamente desde 320 px hasta pantallas de escritorio.
- Mantener una sola página con secciones claramente diferenciadas y navegación por anclas, salvo que Leo pida rutas adicionales.
- Dar prioridad visual al llamado a la acción para descargar desde Google Play, presente en la portada y al final de la página.
- Usar una apariencia clara, confiable y cercana. La paleta base de la aplicación es azul, verde y naranja.
- No inventar textos, enlaces, métricas, testimonios o capturas sin aprobación de Leo.

## Flujo Antes de Codificar

- Antes de crear o editar código, revisar los archivos cercanos para respetar la estructura y convenciones existentes.
- Si el proyecto ya usa español, seguir en español y no mezclar inglés innecesario.
- Si una capa ya usa un patrón concreto, respetarlo en vez de introducir uno nuevo sin motivo.
- Si una capa usa un separador concreto, mantenerlo de forma consistente; no mezclar `_` con `-` dentro del mismo tipo de nombre.
- Si ya existe una convención para nombres o estructura, adaptarse a ella antes de proponer una nueva.
- Si el proyecto ya usa acentos, eñes o un estilo de redacción particular, conservarlo en vez de simplificarlo a ASCII.

## Convención de Nomenclatura

**Regla de oro:** nunca usar guiones bajos (`_`) ni guiones medios (`-`) en nombres de archivos o carpetas.

- Carpetas y archivos: siempre usar PascalCase, sin separadores.
  - Correcto: `GestionUsuarios/`, `ListaProductos.vue`, `PlanMejorasComercios.md`
  - Incorrecto: `gestion_usuarios/`, `lista-productos.vue`, `PLAN_MEJORAS_COMERCIOS.md`
- Variables y funciones: camelCase en español.
  - Correcto: `nombreProducto`, `calcularPrecioPromedio()`
  - Incorrecto: `nombre_producto`, `calcular_precio_promedio()`
- Constantes: MAYÚSCULAS con guiones bajos, única excepción permitida.
  - Correcto: `const API_URL = '...'`, `const MAX_ITEMS = 100`
- Clases CSS globales: kebab-case.
  - Correcto: `.contenedor-pagina`, `.buscador-centrado`
  - Incorrecto: `.contenedor_pagina`, `.BuscadorCentrado`

Antes de crear cualquier archivo, verifica que cumpla con PascalCase.

- Excepción técnica: conservar los nombres y rutas requeridos por Quasar o sus herramientas, como `src/`, `css/`, `app.css` y `quasar.config.js`; los archivos y carpetas propios del proyecto sí deben cumplir PascalCase.

## Código y estructura

- Usar español en variables, funciones, comentarios, textos de interfaz y documentación, salvo nombres exigidos por APIs o herramientas externas.
- Mantener componentes pequeños, reutilizables y centrados en una responsabilidad.
- Priorizar HTML semántico, accesibilidad por teclado, textos alternativos útiles y contraste suficiente.

## Estilo de Comentarios

- Preferir comentarios de una sola línea siempre que sea posible.
- Usar `//` en lugar de `/* */` cuando el comentario cabe en una línea.
- Los comentarios multilínea `/** */` solo para documentación de funciones complejas.

## Estilos

- Usar CSS, sin Sass ni SCSS.
- Mantener `src/css/Variables.css` como única fuente de verdad para colores, espaciados, bordes, sombras, tipografías y demás valores visuales reutilizables.
- Todo color usado en la web debe declararse en `src/css/Variables.css` y consumirse mediante una variable CSS; no usar colores literales fuera de ese archivo.
- Antes de inventar o añadir una variable de color nueva, avisar a Leo y explicar brevemente para qué se necesita.
- Evitar valores de diseño repetidos: declarar primero una variable en `src/css/Variables.css` si el valor se reutiliza.
- No dejar líneas en blanco entre reglas CSS.
- Mantener el CSS compacto y sin espacios innecesarios entre selectores.
- Mantener el CSS ordenado, compacto y sin reglas duplicadas.

## Calidad y publicación

- Antes de dar por terminado un cambio, ejecutar las verificaciones disponibles de formato, lint y build.
- No incluir claves, credenciales ni datos privados en el repositorio o en el frontend.
- Configurar correctamente la ruta base de producción para GitHub Pages según el nombre final del repositorio.
- El despliegue debe realizarse desde GitHub Actions; no depender de publicación manual.
