<template>
  <q-page class="pagina-principal">
    <header class="encabezado-sitio">
      <a class="marca-sitio" href="#inicio" aria-label="Ir al inicio de Precio Justo">
        <img :src="logoPrecioJusto" alt="Logo de Precio Justo" class="logo-sitio" />
        <span>Precio Justo</span>
      </a>
      <nav class="navegacion-sitio" aria-label="Navegación principal">
        <a href="#como-funciona">Cómo funciona</a>
        <a href="#funciones">Funciones</a>
        <q-btn
          class="boton-descarga boton-descarga--encabezado"
          unelevated
          no-caps
          icon="android"
          label="Descargar"
          type="a"
          :href="urlGooglePlay"
          target="_blank"
          rel="noopener noreferrer"
        />
      </nav>
    </header>
    <main id="inicio">
      <section class="seccion-portada" aria-labelledby="titulo-portada">
        <div class="contenido-portada contenedor-sitio">
          <div class="texto-portada">
            <p class="etiqueta-portada">Precio Justo</p>
            <h1 id="titulo-portada">Comprá de forma inteligente</h1>
            <p class="descripcion-portada">
              Registra los precios de los productos que compras y compáralos entre tus comercios y
              sucursales.
            </p>
            <q-btn
              class="boton-descarga boton-descarga--principal"
              unelevated
              no-caps
              icon="android"
              label="Descargar en Google Play"
              type="a"
              :href="urlGooglePlay"
              target="_blank"
              rel="noopener noreferrer"
            />
          </div>
          <img
            :src="bannerPrecioJusto"
            alt="Vista ilustrativa de Precio Justo comparando precios entre comercios"
            class="imagen-portada"
          />
        </div>
      </section>
      <section
        id="como-funciona"
        class="seccion-sitio seccion-tutorial"
        aria-labelledby="titulo-tutorial"
      >
        <div class="contenedor-sitio">
          <div class="encabezado-seccion">
            <p class="etiqueta-seccion">Simple y personal</p>
            <h2 id="titulo-tutorial">Así funciona Precio Justo</h2>
            <p>Organiza tu información de compra en tres pasos claros.</p>
          </div>
          <ol class="lista-pasos">
            <li v-for="paso in pasosTutorial" :key="paso.numero" class="tarjeta-paso">
              <span class="numero-paso">{{ paso.numero }}</span>
              <q-icon :name="paso.icono" size="30px" class="icono-paso" aria-hidden="true" />
              <h3>{{ paso.titulo }}</h3>
              <p>{{ paso.descripcion }}</p>
            </li>
          </ol>
        </div>
      </section>
      <section
        id="funciones"
        class="seccion-sitio seccion-funciones"
        aria-labelledby="titulo-funciones"
      >
        <div class="contenedor-sitio grilla-funciones">
          <div class="texto-funciones">
            <p class="etiqueta-seccion">Más control en tus compras</p>
            <h2 id="titulo-funciones">Todo lo que necesitás para decidir mejor</h2>
            <article
              v-for="funcion in funcionesDestacadas"
              :key="funcion.titulo"
              class="funcion-destacada"
            >
              <q-icon :name="funcion.icono" size="28px" aria-hidden="true" />
              <div>
                <h3>{{ funcion.titulo }}</h3>
                <p>{{ funcion.descripcion }}</p>
              </div>
            </article>
          </div>
          <div class="galeria-tutorial" aria-label="Vistas ilustrativas de Precio Justo">
            <figure
              v-for="imagen in imagenesTutorial"
              :key="imagen.archivo"
              class="imagen-tutorial"
            >
              <img :src="imagen.archivo" :alt="imagen.descripcion" loading="lazy" />
            </figure>
          </div>
          <p class="nota-ilustrativa">
            Las imágenes, comercios y precios mostrados son ilustrativos.
          </p>
        </div>
      </section>
      <section class="seccion-sitio seccion-privacidad" aria-labelledby="titulo-privacidad">
        <div class="contenedor-sitio contenido-privacidad">
          <q-icon name="verified_user" size="38px" aria-hidden="true" />
          <div>
            <h2 id="titulo-privacidad">Tus datos son tuyos</h2>
            <p>
              Tus productos, precios y comercios se registran para tu uso personal y no se comparten
              con otros usuarios.
            </p>
          </div>
        </div>
      </section>
      <section class="seccion-final" aria-labelledby="titulo-final">
        <div class="contenedor-sitio contenido-final">
          <h2 id="titulo-final">Comprá de forma inteligente</h2>
          <p>Empieza a registrar y comparar tus precios con Precio Justo.</p>
          <q-btn
            class="boton-descarga boton-descarga--final"
            unelevated
            no-caps
            icon="android"
            label="Descargar en Google Play"
            type="a"
            :href="urlGooglePlay"
            target="_blank"
            rel="noopener noreferrer"
          />
        </div>
      </section>
    </main>
    <footer class="pie-sitio">
      <div class="contenedor-sitio contenido-pie">
        <span>Precio Justo</span>
        <a :href="urlFacebook" target="_blank" rel="noopener noreferrer">
          <q-icon name="facebook" size="20px" aria-hidden="true" />
          Seguinos en Facebook
        </a>
      </div>
    </footer>
  </q-page>
</template>

<script setup>
const urlGooglePlay = 'https://play.google.com/store/apps/details?id=com.preciojusto.app'
const urlFacebook = 'https://www.facebook.com/profile.php?id=61590710220868'
const rutaBase = import.meta.env.BASE_URL
const logoPrecioJusto = `${rutaBase}Imagenes/LogoPrecioJusto.png`
const bannerPrecioJusto = `${rutaBase}Imagenes/BannerPrecioJusto.png`
const pasosTutorial = [
  {
    numero: '1',
    icono: 'qr_code_scanner',
    titulo: 'Escanea o agrega tus productos',
    descripcion: 'Usa la cámara o registra manualmente los productos que quieres seguir.',
  },
  {
    numero: '2',
    icono: 'edit_note',
    titulo: 'Registra precios y comercios',
    descripcion: 'Guarda el precio de cada producto junto con el comercio y la sucursal.',
  },
  {
    numero: '3',
    icono: 'compare_arrows',
    titulo: 'Compara y decidí',
    descripcion: 'Consulta tus registros para elegir dónde realizar tus compras.',
  },
]
const funcionesDestacadas = [
  {
    icono: 'format_list_bulleted',
    titulo: 'Lista Justa',
    descripcion: 'Organiza tus productos para planificar tus compras diarias.',
  },
  {
    icono: 'history',
    titulo: 'Historial de precios',
    descripcion: 'Consulta los precios que registraste antes de volver a comprar.',
  },
]
const imagenesTutorial = [
  {
    archivo: `${rutaBase}Imagenes/TutorialEscanear.png`,
    descripcion: 'Vista ilustrativa de un producto registrado en Precio Justo',
  },
  {
    archivo: `${rutaBase}Imagenes/TutorialRegistrar.png`,
    descripcion: 'Vista ilustrativa del registro de precios en Precio Justo',
  },
  {
    archivo: `${rutaBase}Imagenes/TutorialComparar.png`,
    descripcion: 'Vista ilustrativa de la comparación de precios en Precio Justo',
  },
]
</script>

<style scoped>
.pagina-principal {
  min-height: 100vh;
}
.contenedor-sitio {
  width: min(1120px, calc(100% - (var(--espaciado-lg) * 2)));
  margin: 0 auto;
}
.encabezado-sitio {
  position: sticky;
  top: 0;
  z-index: 10;
  display: flex;
  align-items: center;
  justify-content: space-between;
  min-height: 68px;
  padding: 0 var(--espaciado-lg);
  border-bottom: 1px solid var(--borde-color);
  background: var(--fondo-superficie);
  box-shadow: var(--sombra-suave);
}
.marca-sitio,
.navegacion-sitio,
.contenido-pie,
.funcion-destacada,
.contenido-privacidad {
  display: flex;
  align-items: center;
}
.marca-sitio {
  gap: var(--espaciado-sm);
  color: var(--texto-primario);
  font-size: 18px;
  font-weight: 800;
  text-decoration: none;
}
.logo-sitio {
  width: 38px;
  height: 38px;
  border-radius: var(--borde-radio-sm);
  object-fit: cover;
}
.navegacion-sitio {
  gap: var(--espaciado-lg);
}
.navegacion-sitio > a,
.contenido-pie > a {
  color: var(--texto-secundario);
  font-size: 14px;
  font-weight: 700;
  text-decoration: none;
}
.navegacion-sitio > a:hover,
.navegacion-sitio > a:focus-visible,
.contenido-pie > a:hover,
.contenido-pie > a:focus-visible {
  color: var(--color-primario-oscuro);
}
.boton-descarga {
  font-weight: 800;
}
.boton-descarga--encabezado {
  color: var(--texto-sobre-primario);
  background: var(--color-primario);
}
.boton-descarga--principal,
.boton-descarga--final {
  color: var(--texto-primario);
  background: var(--color-acento);
}
.seccion-portada {
  overflow: hidden;
  background: linear-gradient(135deg, var(--color-primario) 0%, var(--fondo-hero) 100%);
}
.contenido-portada {
  display: grid;
  grid-template-columns: minmax(0, 0.92fr) minmax(420px, 1.08fr);
  align-items: center;
  min-height: 570px;
  gap: var(--espaciado-xl);
}
.texto-portada {
  position: relative;
  z-index: 1;
  padding: var(--espaciado-xl) 0;
}
.etiqueta-portada,
.etiqueta-seccion {
  margin: 0 0 var(--espaciado-sm);
  color: var(--color-secundario);
  font-size: 13px;
  font-weight: 800;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}
.texto-portada h1,
.encabezado-seccion h2,
.texto-funciones h2,
.contenido-privacidad h2,
.contenido-final h2 {
  margin: 0;
  font-weight: 800;
  line-height: 1.08;
}
.texto-portada h1 {
  max-width: 580px;
  color: var(--texto-sobre-primario);
  font-size: clamp(40px, 5.6vw, 64px);
}
.descripcion-portada {
  max-width: 520px;
  margin: var(--espaciado-md) 0 var(--espaciado-lg);
  color: var(--texto-sobre-primario-suave);
  font-size: clamp(18px, 2vw, 21px);
  line-height: 1.55;
}
.imagen-portada {
  width: 100%;
  min-height: 420px;
  object-fit: cover;
  object-position: right center;
  border-radius: var(--borde-radio-md);
  box-shadow: var(--sombra-media);
}
.seccion-sitio {
  padding: 92px 0;
  scroll-margin-top: 68px;
}
.seccion-tutorial {
  background: var(--fondo-superficie);
}
.encabezado-seccion {
  max-width: 650px;
  margin: 0 auto var(--espaciado-xl);
  text-align: center;
}
.encabezado-seccion h2,
.texto-funciones h2,
.contenido-privacidad h2,
.contenido-final h2 {
  color: var(--texto-primario);
  font-size: clamp(30px, 4vw, 44px);
}
.encabezado-seccion > p:last-child,
.texto-funciones > p,
.funcion-destacada p,
.contenido-privacidad p,
.contenido-final p {
  color: var(--texto-secundario);
  line-height: 1.6;
}
.lista-pasos {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--espaciado-lg);
  padding: 0;
  margin: 0;
  list-style: none;
}
.tarjeta-paso {
  position: relative;
  padding: 52px var(--espaciado-lg) var(--espaciado-lg);
  border: 1px solid var(--borde-color);
  border-radius: var(--borde-radio-md);
  background: var(--fondo-pagina);
}
.numero-paso {
  position: absolute;
  top: var(--espaciado-md);
  right: var(--espaciado-md);
  display: grid;
  width: 30px;
  height: 30px;
  place-items: center;
  border-radius: 50%;
  color: var(--texto-sobre-primario);
  background: var(--color-primario);
  font-size: 14px;
  font-weight: 800;
}
.icono-paso,
.funcion-destacada > .q-icon,
.contenido-privacidad > .q-icon {
  color: var(--color-primario);
}
.tarjeta-paso h3,
.funcion-destacada h3 {
  margin: var(--espaciado-md) 0 var(--espaciado-xs);
  color: var(--texto-primario);
  font-size: 20px;
}
.tarjeta-paso p {
  margin: 0;
  color: var(--texto-secundario);
  line-height: 1.6;
}
.seccion-funciones {
  background: var(--fondo-banner-suave);
}
.grilla-funciones {
  display: grid;
  grid-template-columns: minmax(0, 0.82fr) minmax(0, 1.18fr);
  gap: clamp(var(--espaciado-xl), 6vw, 76px);
  align-items: center;
}
.texto-funciones > .etiqueta-seccion {
  margin-bottom: var(--espaciado-sm);
}
.funcion-destacada {
  align-items: flex-start;
  gap: var(--espaciado-md);
  margin-top: var(--espaciado-lg);
}
.funcion-destacada h3 {
  margin-top: 0;
}
.funcion-destacada p {
  margin: 0;
}
.galeria-tutorial {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--espaciado-sm);
}
.imagen-tutorial {
  min-width: 0;
  margin: 0;
  overflow: hidden;
  border: 1px solid var(--borde-color);
  border-radius: var(--borde-radio-md);
  background: var(--fondo-superficie);
  box-shadow: var(--sombra-suave);
}
.imagen-tutorial img {
  display: block;
  width: 100%;
  aspect-ratio: 9 / 16;
  object-fit: cover;
  object-position: top center;
}
.nota-ilustrativa {
  grid-column: 2;
  margin: calc(var(--espaciado-sm) * -1) 0 0;
  color: var(--texto-secundario);
  font-size: 12px;
  text-align: center;
}
.seccion-privacidad {
  background: var(--fondo-superficie);
}
.contenido-privacidad {
  max-width: 760px;
  gap: var(--espaciado-lg);
  padding: var(--espaciado-xl);
  border: 1px solid var(--borde-color);
  border-radius: var(--borde-radio-md);
  background: var(--fondo-pagina);
}
.contenido-privacidad p {
  margin: var(--espaciado-sm) 0 0;
}
.seccion-final {
  padding: 88px 0;
  background: linear-gradient(135deg, var(--color-primario) 0%, var(--fondo-hero) 100%);
  text-align: center;
}
.contenido-final {
  max-width: 640px;
  margin: 0 auto;
}
.contenido-final h2 {
  color: var(--texto-sobre-primario);
}
.contenido-final p {
  margin: var(--espaciado-md) 0 var(--espaciado-lg);
  color: var(--texto-sobre-primario-suave);
  font-size: 18px;
}
.pie-sitio {
  padding: var(--espaciado-lg) 0;
  background: var(--fondo-superficie);
}
.contenido-pie {
  justify-content: space-between;
  color: var(--texto-secundario);
  font-size: 14px;
}
.contenido-pie > span {
  color: var(--texto-primario);
  font-weight: 800;
}
.contenido-pie > a {
  gap: var(--espaciado-xs);
  display: inline-flex;
  align-items: center;
}
@media (max-width: 800px) {
  .encabezado-sitio {
    padding: 0 var(--espaciado-md);
  }
  .navegacion-sitio {
    gap: var(--espaciado-md);
  }
  .navegacion-sitio > a {
    display: none;
  }
  .contenido-portada,
  .grilla-funciones {
    grid-template-columns: 1fr;
  }
  .contenido-portada {
    min-height: auto;
    gap: 0;
    padding-top: var(--espaciado-xl);
  }
  .texto-portada {
    padding-top: 0;
  }
  .imagen-portada {
    min-height: 300px;
    border-radius: var(--borde-radio-md) var(--borde-radio-md) 0 0;
  }
  .lista-pasos {
    grid-template-columns: 1fr;
  }
  .nota-ilustrativa {
    grid-column: auto;
  }
}
@media (max-width: 480px) {
  .contenedor-sitio {
    width: min(100% - (var(--espaciado-md) * 2), 1120px);
  }
  .marca-sitio {
    font-size: 16px;
  }
  .boton-descarga--encabezado {
    min-height: 38px;
    padding: 0 var(--espaciado-sm);
    font-size: 12px;
  }
  .seccion-sitio,
  .seccion-final {
    padding: 64px 0;
  }
  .galeria-tutorial {
    grid-template-columns: repeat(2, 1fr);
  }
  .imagen-tutorial:last-child {
    grid-column: 1 / -1;
    width: calc((100% - var(--espaciado-sm)) / 2);
    justify-self: center;
  }
  .contenido-privacidad {
    align-items: flex-start;
    padding: var(--espaciado-lg);
  }
  .contenido-pie {
    align-items: flex-start;
    flex-direction: column;
    gap: var(--espaciado-sm);
  }
}
</style>
