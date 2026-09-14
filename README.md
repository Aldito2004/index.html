# index.html
Logistic
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Logistic conecta transportistas con cargas compatibles con su ruta de regreso para reducir kilómetros vacíos.">
  <title>Logistic | Cada regreso cuenta</title>
  <style>
    :root {
      --azul: #102c40;
      --azul-claro: #20475e;
      --verde: #b6ed79;
      --fondo: #f5f7f4;
      --texto: #203544;
      --gris: #586b77;
      --borde: #dce4df;
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
      scroll-padding-top: 90px;
    }

    body {
      margin: 0;
      background: var(--fondo);
      color: var(--texto);
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      line-height: 1.6;
    }

    a {
      color: inherit;
    }

    a:focus-visible {
      outline: 3px solid #398200;
      outline-offset: 6px;
    }

    .contenedor {
      width: min(1120px, 90%);
      margin-inline: auto;
    }

    .navegacion {
      position: sticky;
      top: 0;
      z-index: 10;
      background: #f5f7f4;
      border-bottom: 1px solid var(--borde);
    }

    .barra {
      min-height: 80px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 24px;
    }

    .marca {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      font-size: 1.5rem;
      font-weight: 850;
      letter-spacing: -1px;
      text-decoration: none;
    }

    .simbolo {
      display: grid;
      width: 34px;
      height: 34px;
      place-items: center;
      border-radius: 10px;
      background: var(--azul);
      color: var(--verde);
      font-size: 1.3rem;
    }

    .enlaces {
      display: flex;
      gap: 28px;
      margin: 0;
      padding: 0;
      list-style: none;
    }

    .enlaces a {
      font-size: 0.92rem;
      font-weight: 650;
      text-decoration: none;
    }

    .enlaces a:hover {
      text-decoration: underline;
      text-underline-offset: 6px;
    }

    .hero {
      overflow: hidden;
      background: var(--azul);
      color: #fff;
    }

    .hero-interior {
      display: grid;
      grid-template-columns: 1.2fr 1fr;
      align-items: center;
      gap: 64px;
      padding-block: 96px;
    }

    .etiqueta {
      margin: 0 0 20px;
      color: var(--verde);
      font-size: 0.76rem;
      font-weight: 750;
      letter-spacing: 2px;
      text-transform: uppercase;
    }

    h1 {
      margin: 0;
      font-size: clamp(2.8rem, 5.5vw, 4.6rem);
      line-height: 1.06;
      letter-spacing: -2.5px;
    }

    h1 span {
      color: var(--verde);
    }

    .subtitulo {
      max-width: 520px;
      margin: 26px 0 32px;
      color: #d3e0e8;
      font-size: 1.1rem;
    }

    .boton {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 24px;
      padding: 15px 23px;
      border-radius: 8px;
      background: var(--verde);
      color: var(--azul);
      font-weight: 750;
      text-decoration: none;
      transition: background 160ms ease, transform 160ms ease;
    }

    .boton:hover {
      background: #c9f69b;
      transform: translateY(-2px);
    }

    .ruta {
      padding: 30px;
      border: 1px solid #476173;
      border-radius: 20px;
      background: var(--azul-claro);
      box-shadow: 0 24px 60px #061a2940;
    }

    .ruta-encabezado {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
      margin-bottom: 28px;
    }

    .ruta-encabezado h2 {
      margin: 0;
      font-size: 1rem;
    }

    .ejemplo {
      padding: 4px 9px;
      border: 1px solid #78919f;
      border-radius: 100px;
      color: #e0e9ed;
      font-size: 0.7rem;
    }

    .trayecto {
      margin: 0 0 26px 7px;
      padding: 0 0 0 26px;
      border-left: 2px dashed #8aa0ae;
      list-style: none;
    }

    .trayecto li {
      position: relative;
      padding-bottom: 27px;
    }

    .trayecto li:last-child {
      padding-bottom: 0;
    }

    .trayecto li::before {
      position: absolute;
      top: 7px;
      left: -33px;
      width: 12px;
      height: 12px;
      border: 2px solid var(--azul-claro);
      border-radius: 50%;
      background: var(--verde);
      content: "";
    }

    .trayecto strong,
    .trayecto span {
      display: block;
    }

    .trayecto span {
      color: #d3e0e8;
      font-size: 0.86rem;
    }

    .coincidencia {
      padding: 17px;
      border-radius: 10px;
      background: var(--azul);
    }

    .coincidencia strong {
      color: var(--verde);
      font-size: 0.9rem;
    }

    .coincidencia p {
      margin: 6px 0 0;
      color: #d3e0e8;
      font-size: 0.85rem;
    }

    .servicios {
      padding-block: 80px;
    }

    .seccion-etiqueta {
      margin: 0 0 10px;
      color: #46702e;
      font-size: 0.75rem;
      font-weight: 800;
      letter-spacing: 2px;
      text-transform: uppercase;
    }

    .servicios h2 {
      margin: 0 0 35px;
      font-size: clamp(1.9rem, 3.5vw, 2.7rem);
      line-height: 1.2;
      letter-spacing: -1px;
    }

    .tarjetas {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 22px;
    }

    .tarjeta {
      padding: 30px;
      border: 1px solid var(--borde);
      border-radius: 14px;
      background: #fff;
    }

    .numero {
      display: inline-grid;
      width: 44px;
      height: 44px;
      margin-bottom: 25px;
      place-items: center;
      border-radius: 12px;
      background: #edf5e7;
      color: #396124;
      font-size: 0.85rem;
      font-weight: 800;
    }

    .tarjeta h3 {
      margin: 0 0 10px;
      font-size: 1.2rem;
    }

    .dato {
      display: inline-block;
      margin: 0 0 14px;
      color: #396124;
      font-size: 0.82rem;
      font-weight: 750;
    }

    .descripcion {
      margin: 0;
      color: var(--gris);
      font-size: 0.95rem;
    }

    footer {
      padding-block: 30px;
      border-top: 1px solid var(--borde);
    }

    .pie {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 16px;
    }

    .pie p {
      margin: 0;
      color: var(--gris);
      font-size: 0.83rem;
    }

    .contacto {
      font-size: 0.9rem;
      font-weight: 700;
      text-underline-offset: 4px;
    }

    @media (max-width: 850px) {
      .hero-interior {
        grid-template-columns: 1fr;
        gap: 40px;
        padding-block: 64px;
      }

      .ruta {
        max-width: 560px;
        width: 100%;
      }

      .tarjetas {
        grid-template-columns: 1fr;
      }

      .servicios {
        padding-block: 56px;
      }
    }

    @media (max-width: 480px) {
      .barra {
        min-height: 96px;
        flex-direction: column;
        justify-content: center;
        gap: 9px;
        padding-block: 12px;
      }

      html {
        scroll-padding-top: 120px;
      }

      .enlaces {
        gap: 24px;
      }

      h1 {
        letter-spacing: -1.5px;
      }

      .ruta,
      .tarjeta {
        padding: 23px;
      }
    }

    @media (prefers-reduced-motion: reduce) {
      html {
        scroll-behavior: auto;
      }

      .boton {
        transition: none;
      }
    }
  </style>
</head>
<body>
  <header class="navegacion">
    <nav class="contenedor barra" aria-label="Navegación principal">
      <a class="marca" href="#inicio" aria-label="Logistic, inicio">
        <span class="simbolo" aria-hidden="true">↗</span>
        Logistic
      </a>
      <ul class="enlaces">
        <li><a href="#inicio">Inicio</a></li>
        <li><a href="#servicios">Servicios</a></li>
        <li><a href="#contacto">Contacto</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <section class="hero" id="inicio" aria-labelledby="titulo">
      <div class="contenedor hero-interior">
        <div>
          <p class="etiqueta">Logística inteligente de retorno</p>
          <h1>Tu camión regresa.<br><span>Que vuelva con carga.</span></h1>
          <p class="subtitulo">Conectamos tu ruta de regreso con cargas compatibles mediante IA para reducir kilómetros vacíos y aprovechar cada viaje.</p>
          <a class="boton" href="#servicios">
            Explorar soluciones <span aria-hidden="true">↗</span>
          </a>
        </div>

        <aside class="ruta" aria-labelledby="titulo-ruta">
          <div class="ruta-encabezado">
            <h2 id="titulo-ruta">Un regreso con oportunidad</h2>
            <span class="ejemplo">Ejemplo ilustrativo</span>
          </div>
          <ol class="trayecto">
            <li>
              <strong>Monterrey</strong>
              <span>Entrega completada · inicia el regreso</span>
            </li>
            <li>
              <strong>Querétaro</strong>
              <span>Carga compatible rumbo a tu base</span>
            </li>
            <li>
              <strong>Ciudad de México</strong>
              <span>Entrega de carga y retorno a base</span>
            </li>
          </ol>
          <div class="coincidencia">
            <strong>Una conexión que hace sentido</strong>
            <p>La plataforma sugiere la carga; transportista y empresa acuerdan el precio y el contrato directamente.</p>
          </div>
        </aside>
      </div>
    </section>

    <section class="servicios contenedor" id="servicios" aria-labelledby="titulo-servicios">
      <p class="seccion-etiqueta">Del registro al regreso</p>
      <h2 id="titulo-servicios">Tres pasos hacia menos kilómetros vacíos.</h2>

      <div class="tarjetas">
        <article class="tarjeta">
          <span class="numero" aria-hidden="true">01</span>
          <h3>Registro de flota</h3>
          <p class="dato">Uno o varios camiones</p>
          <p class="descripcion">Registra tus unidades, ubicación, destino y base de retorno para encontrar oportunidades que encajen con tu operación.</p>
        </article>

        <article class="tarjeta">
          <span class="numero" aria-hidden="true">02</span>
          <h3>Rutas compatibles</h3>
          <p class="dato">Sugerencias mediante IA</p>
          <p class="descripcion">Identifica cargas para tu regreso a partir de tu recorrido y del historial de pedidos de otros usuarios.</p>
        </article>

        <article class="tarjeta">
          <span class="numero" aria-hidden="true">03</span>
          <h3>Acuerdos directos</h3>
          <p class="dato">Precio y contrato entre usuarios</p>
          <p class="descripcion">Conecta con la empresa que necesita transportar su carga y acuerden las condiciones del servicio antes de confirmar el viaje.</p>
        </article>
      </div>
    </section>
  </main>

  <footer id="contacto" aria-label="Contacto y derechos reservados">
    <div class="contenedor pie">
      <p>© 2026 Logistic. Todos los derechos reservados.</p>
      <a class="contacto" href="mailto:contacto@logistic.example">Contáctanos ↗</a>
    </div>
  </footer>
</body>
</html>
