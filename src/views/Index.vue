<template>
  <div data-bs-spy="scroll" data-bs-target="#navbar">
      <!-- Header -->
      <nav id="header" class="navbar navbar-expand-lg navbar-dark bg-dark fixed-top">
        <div class="container justify-content-start">

          <!-- Logo del header -->
          <!-- /Logo del header -->
          <div class="container">
            <div class="row">
              <div class="col-12 col-sm-9  col-lg-6  ">
                <div class="row h-100">
                  <div class="col text-center text-sm-start">
                    <a class="navbar-brand" href="#">
                      <small>Comidas rápidas la 14</small>
                      <img src="assets/images/LogoPrimary.png" alt="Logo hamburguesa" class="btn">
                    </a>
                  </div>
                </div>
              </div>
              <div class="col-2 col-sm-2 col-lg-5 p-1 mt-2 text-end">
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbar"
                  aria-controls="navbar" aria-expanded="false" aria-label="Toggle navigation">
                  <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbar">
                  <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                      <a class="nav-link" aria-current="page" href="#main" ata-bs-toggle="collapse">Información</a>
                    </li>
                    <li class="nav-item">
                      <a class="nav-link" href="#hamburguesas" id="hamburguesa-nav">Hamburguesa</a>
                    </li>
                    <li class="nav-item text-end">
                      <a class="nav-link " href="#hot-dogs" id="hot-dog">HotDogs</a>
                    </li>
                    <li>
                      
                    </li>
                  </ul>
                </div>
              </div>
              <div class="col col-sm-1 text-end">
                <div class="row">
                  <div class="col   offset-lg-3 ">
                    <div class="btn btn-logo position-relative" data-bs-toggle="modal" data-bs-target="#carrito">
                      <span
                        class="position-absolute top-50  translate-middle badge rounded-pill bg-danger me-5">{{cantidad}}</span>
                      <img src="assets/images/logoSecundary.png" alt="Carrito" class="btn btn-logo me-0">
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>


        </div>
      </nav>
      <!--/Header -->


      <!-- Main -->
      <main id="main" class="mb-5">
        <!-- Carusel -->
        <div id="carousel" class="carousel slide carousel-fade mt-5 mt-sm-0" data-bs-ride="carousel"
          data-bs-pause="false">
          <div class="carousel-inner">
            <div class="carousel-item active">
              <img src="assets/images/image1.jpg" class="d-block w-100" alt="Images carousel">
            </div>
            <div class="carousel-item">
              <img src="assets/images/images2.jpg" class="d-block w-100" alt="Images carousel">
            </div>
            <div class="carousel-item">
              <img src="assets/images/images3.jpg" class="d-block w-100" alt="Images carousel">
            </div>
            <!-- Contenido que se ve por encima del Carousel -->
            <div class="overlay mt-5 mt-sm-0 pt-5 pt-sm-0 pb-2 pb-sm-0">
              <div class="container">
                <div class="row align-items-center">
                  <div class="col-md-6 offset-md-6 text-sm-end text-center " id="text-main">
                    <h1 class="mt-5 mt-sm-0 ">Comidas rápidas la 14</h1>
                    <p class="d-none d-sm-block">Ofrecemos gran variedad en Hamburguesa y perros calientes, con una
                      exquisita
                      salsa de la casa para chuparse los dedos, precios accesibles y un gran sabor, Comidas rápidas la
                      14
                      donde no matamos tus problemas pero si tus antojos </p>
                  </div>
                </div>
              </div>
            </div>
            <!-- /Contenido que se ve por encima del Carousel -->
          </div>
        </div>
        <!-- /Carusel -->
      </main>
      <!-- /Main -->

      
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>