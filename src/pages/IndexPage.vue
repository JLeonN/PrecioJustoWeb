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
        <img
          :src="heroCompras"
          alt="Persona consultando su celular mientras compra"
          class="fondo-portada"
        />
        <div class="capa-portada" aria-hidden="true"></div>
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
          <div class="vista-portada" aria-label="Vista real de la comparación de precios">
            <div class="marco-celular marco-celular--portada">
              <img
                :src="capturaComparacion"
                alt="Comparación de precios por producto en Precio Justo"
              />
            </div>
          </div>
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
            <p>Registrá lo que compras, organizá tu lista y decidí con tus propios registros.</p>
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
        <div class="contenedor-sitio">
          <div class="encabezado-seccion">
            <p class="etiqueta-seccion">Más control en tus compras</p>
            <h2 id="titulo-funciones">Todo lo que necesitás para decidir mejor</h2>
            <p>
              Precio Justo reúne tu información para comparar, organizar y aprovechar cada compra.
            </p>
          </div>
          <div class="lista-funciones">
            <article
              v-for="funcion in funcionesDestacadas"
              :key="funcion.titulo"
              class="funcion-destacada"
            >
              <q-icon :name="funcion.icono" size="30px" aria-hidden="true" />
              <div>
                <h3>{{ funcion.titulo }}</h3>
                <p>{{ funcion.descripcion }}</p>
              </div>
            </article>
          </div>
          <div class="galeria-capturas" aria-label="Capturas reales de Precio Justo">
            <figure
              v-for="captura in capturasAplicacion"
              :key="captura.archivo"
              class="captura-aplicacion"
            >
              <div class="marco-celular">
                <img :src="captura.archivo" :alt="captura.descripcion" loading="lazy" />
              </div>
              <figcaption>{{ captura.titulo }}</figcaption>
            </figure>
          </div>
          <p class="nota-capturas">
            Las capturas muestran funciones reales de Precio Justo. Los comercios y precios visibles
            se incluyen únicamente a modo ilustrativo.
          </p>
        </div>
      </section>
      <section class="seccion-gracias" aria-labelledby="titulo-gracias">
        <div class="contenedor-sitio contenido-gracias">
          <q-icon name="favorite" size="34px" aria-hidden="true" />
          <div>
            <h2 id="titulo-gracias">Gracias por darle una oportunidad a Precio Justo</h2>
            <p>
              Cada descarga y cada registro ayudan a que este proyecto siga creciendo y mejorando.
            </p>
          </div>
        </div>
      </section>
      <section class="seccion-final" aria-labelledby="titulo-final">
        <div class="contenedor-sitio contenido-final">
          <h2 id="titulo-final">Comprá de forma inteligente</h2>
          <p>Empezá a registrar y comparar tus precios con Precio Justo.</p>
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
const heroCompras = `${rutaBase}Imagenes/HeroCompras.png`
const capturaComparacion = `${rutaBase}Imagenes/CapturaComparacion.jpeg`
const pasosTutorial = [
  {
    numero: '1',
    icono: 'edit_note',
    titulo: 'Registrá tus productos y precios',
    descripcion: 'Agregá productos y guardá su precio junto con el comercio y la sucursal.',
  },
  {
    numero: '2',
    icono: 'format_list_bulleted',
    titulo: 'Organizá tu Lista Justa',
    descripcion: 'Prepará tus compras con los productos que necesitás y los comercios a comparar.',
  },
  {
    numero: '3',
    icono: 'compare_arrows',
    titulo: 'Compará y decidí',
    descripcion:
      'Consultá precios, historial y opciones de compra para elegir con más información.',
  },
]
const funcionesDestacadas = [
  {
    icono: 'price_check',
    titulo: 'Compará precios por producto',
    descripcion:
      'Revisá tus registros por comercio y descubrí dónde te conviene comprar cada producto.',
  },
  {
    icono: 'savings',
    titulo: 'Organizá una compra más conveniente',
    descripcion:
      'La Lista Justa te ayuda a comparar comercios, ordenar tus productos y estimar el ahorro.',
  },
  {
    icono: 'history',
    titulo: 'Consultá tu historial',
    descripcion:
      'Volvé a ver los precios registrados por período y comercio antes de salir a comprar.',
  },
]
const capturasAplicacion = [
  {
    archivo: `${rutaBase}Imagenes/CapturaInicio.jpeg`,
    titulo: 'Todo a mano',
    descripcion: 'Pantalla de inicio de Precio Justo con acceso a listas, productos y comercios',
  },
  {
    archivo: `${rutaBase}Imagenes/CapturaComparacion.jpeg`,
    titulo: 'Compará precios',
    descripcion: 'Comparación de precios por producto entre comercios',
  },
  {
    archivo: `${rutaBase}Imagenes/CapturaListaCompras.jpeg`,
    titulo: 'Lista Justa',
    descripcion: 'Lista de compras organizada por productos',
  },
  {
    archivo: `${rutaBase}Imagenes/CapturaCompraOptimizada.jpeg`,
    titulo: 'Compra optimizada',
    descripcion: 'Vista de compra optimizada por producto y ahorro estimado',
  },
  {
    archivo: `${rutaBase}Imagenes/CapturaHistorialPrecios.jpeg`,
    titulo: 'Historial de precios',
    descripcion: 'Historial de precios registrados por comercio',
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
  z-index: 20;
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
.contenido-gracias {
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
  color: var(--texto-sobre-primario) !important;
  background-color: var(--color-primario) !important;
}
.boton-descarga--principal,
.boton-descarga--final {
  color: var(--texto-primario);
  background: var(--color-acento);
}
.seccion-portada {
  position: relative;
  min-height: 590px;
  overflow: hidden;
  background: var(--fondo-hero);
}
.fondo-portada,
.capa-portada {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
}
.fondo-portada {
  object-fit: cover;
  object-position: center;
}
.capa-portada {
  background: var(--fondo-hero);
  opacity: 0.72;
}
.contenido-portada {
  position: relative;
  z-index: 1;
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(280px, 0.72fr);
  min-height: 590px;
  gap: var(--espaciado-xl);
  align-items: center;
}
.texto-portada {
  padding: var(--espaciado-xl) 0;
}
.etiqueta-portada,
.etiqueta-seccion {
  margin: 0 0 var(--espaciado-sm);
  font-size: 13px;
  font-weight: 800;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}
.etiqueta-portada {
  color: var(--texto-sobre-primario);
}
.etiqueta-seccion {
  color: var(--color-secundario);
}
.texto-portada h1,
.encabezado-seccion h2,
.contenido-gracias h2,
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
.vista-portada {
  display: flex;
  justify-content: center;
}
.marco-celular {
  width: min(100%, 230px);
  padding: var(--espaciado-xs);
  overflow: hidden;
  border: 1px solid var(--borde-color);
  border-radius: var(--borde-radio-md);
  background: var(--fondo-superficie);
  box-shadow: var(--sombra-media);
}
.marco-celular--portada {
  width: min(100%, 278px);
  border-color: var(--borde-blanco-sutil);
}
.marco-celular img {
  display: block;
  width: 100%;
  aspect-ratio: 9 / 16;
  border-radius: var(--borde-radio-sm);
  object-fit: cover;
  object-position: top center;
}
.seccion-sitio {
  padding: 92px 0;
  scroll-margin-top: 68px;
}
.seccion-tutorial {
  background: var(--fondo-superficie);
}
.encabezado-seccion {
  max-width: 720px;
  margin: 0 auto var(--espaciado-xl);
  text-align: center;
}
.encabezado-seccion h2,
.contenido-gracias h2,
.contenido-final h2 {
  color: var(--texto-primario);
  font-size: clamp(30px, 4vw, 44px);
}
.encabezado-seccion > p:last-child,
.funcion-destacada p,
.contenido-gracias p,
.contenido-final p {
  color: var(--texto-secundario);
  line-height: 1.6;
}
.lista-pasos,
.lista-funciones {
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
.funcion-destacada > .q-icon {
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
.funcion-destacada {
  align-items: flex-start;
  gap: var(--espaciado-md);
  padding: var(--espaciado-lg);
  border: 1px solid var(--borde-color);
  border-radius: var(--borde-radio-md);
  background: var(--fondo-superficie);
}
.funcion-destacada h3 {
  margin-top: 0;
}
.funcion-destacada p {
  margin: 0;
}
.galeria-capturas {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: var(--espaciado-md);
  margin-top: var(--espaciado-xl);
}
.captura-aplicacion {
  min-width: 0;
  margin: 0;
  text-align: center;
}
.captura-aplicacion .marco-celular {
  width: 100%;
}
.captura-aplicacion figcaption {
  margin-top: var(--espaciado-sm);
  color: var(--texto-primario);
  font-size: 14px;
  font-weight: 800;
}
.nota-capturas {
  max-width: 680px;
  margin: var(--espaciado-lg) auto 0;
  color: var(--texto-secundario);
  font-size: 13px;
  line-height: 1.5;
  text-align: center;
}
.contenido-gracias {
  max-width: 800px;
  gap: var(--espaciado-lg);
  padding: var(--espaciado-xl);
  border: 1px solid var(--borde-color);
  border-radius: var(--borde-radio-md);
  background: var(--fondo-pagina);
}
.contenido-gracias p {
  margin: var(--espaciado-sm) 0 0;
}
.seccion-gracias {
  padding: 72px 0;
  background: var(--fondo-banner-suave);
}
.contenido-gracias > .q-icon {
  color: var(--color-acento);
}
.seccion-final {
  padding: 88px 0;
  background: var(--fondo-hero);
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
  display: inline-flex;
  align-items: center;
  gap: var(--espaciado-xs);
}
@media (max-width: 900px) {
  .contenido-portada {
    grid-template-columns: minmax(0, 1fr) minmax(220px, 0.55fr);
  }
  .galeria-capturas {
    grid-template-columns: repeat(3, 1fr);
  }
}
@media (max-width: 700px) {
  .encabezado-sitio {
    padding: 0 var(--espaciado-md);
  }
  .navegacion-sitio {
    gap: var(--espaciado-md);
  }
  .navegacion-sitio > a {
    display: none;
  }
  .contenido-portada {
    grid-template-columns: 1fr;
    min-height: auto;
    padding: var(--espaciado-xl) 0 0;
    gap: 0;
  }
  .texto-portada {
    padding-top: 0;
  }
  .vista-portada {
    margin-top: var(--espaciado-lg);
  }
  .marco-celular--portada {
    width: min(68vw, 278px);
  }
  .lista-pasos,
  .lista-funciones {
    grid-template-columns: 1fr;
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
  .seccion-gracias {
    padding: 56px 0;
  }
  .galeria-capturas {
    grid-template-columns: repeat(2, 1fr);
  }
  .captura-aplicacion:last-child {
    grid-column: 1 / -1;
    width: calc((100% - var(--espaciado-md)) / 2);
    justify-self: center;
  }
  .contenido-gracias {
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
