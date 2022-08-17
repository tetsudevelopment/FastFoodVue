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

    <!--Hamburguesas -->
      <section id="hamburguesas" class="mt-5 mb-5">
        <div class="container-fluid">
          <div class="row row-hamburguesa mb-4 p-0 ">
            <div class="col  col-lg-6 text-uppercase p-3 text-center text-md-center text-lg-start">
              <small class="h5 fw-bold offset-lg-2">Hamburguesa</small>
            </div>
          </div>
          <div class="container">
            <!-- Cards -->
            <div class="row justify-content-center">
              <div class="col-md-6 col-lg-3 col mb-4" v-for="item in dataFood[0].burger" :key="item.id">
                <div class="card col h-100">
                  <div class="container">
                    <div class="row">
                      <div class="col text-center btn" data-bs-toggle="modal" :data-bs-target="item.idModal">
                        <img :src="item.img" class="card-img-top card-img1 mb-2 mt-3" :alt="item.name">
                      </div>
                    </div>
                  </div> 
                  <div class="card-body text-center">
                    <h5 class="card-title ">{{item.name}}</h5>
                  </div>
                  <!-- Ingresar cantidad -->
                  <div class="container-fluid mb-2">
                    <div class="row">
                      <div class="col text-center">
                        <p class="text-center fw-bold">Cantidad</p>
                      </div>
                      <div class="input-group mb-3">
                        <button class="btn btn-outline " type="button" id="button-image"><img
                            src="assets/images/menos.png" alt="" @click="cant(item,0)"></button>
                        <input type="number" class="form-control rounded text-center" placeholder=""
                          aria-label="Example text with button addon" aria-describedby="button-addon1"
                          v-model="item.cant">
                        <button class="btn btn-outline " type="button" id="button-image"><img
                            src="assets/images/mas.png" alt="" @click="cant(item,1)"></button>
                      </div>
                    </div>
                  </div>
                  <!-- /Ingresar Cantidad -->
                  <div class="card-footer">
                    <div class="container">
                      <div class="row">
                        <div class="col text-center">
                          <button type="button" class="btn btn-hamburger" @click="agg(item)"> Agregar</button>

                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>

            </div>
          </div>
          <!-- /Cards -->
        </div>
      </section>
      <!-- /Hamburguesa -->
    <!-- Hot Dogs-->
      <section id="hot-dogs" class="mt-4 mb-2">
        <div class="container-fluid">
          <div class="row row-hotDogs mb-4 p-0 ">
            <div class="col  col-lg-6 text-uppercase p-3 text-center text-md-center text-lg-start">
              <small class="h5 fw-bold offset-lg-2">Hot Dogs</small>
            </div>
          </div>
          <div class="container">
            <!-- Cards -->
            <div class="row justify-content-center">
              <div class="col-md-6 col-lg-3 col mb-4" v-for="item in dataFood[0].hotDog" :key="item.id">
                <div class="card col h-100">
                  <div class="container">
                    <div class="row">
                      <div class="col text-center btn" data-bs-toggle="modal" :data-bs-target="item.idModal">
                        <img :src="item.img" class="card-img-top card-img1 mb-2 mt-3" :alt="item.name">
                      </div>
                    </div>
                  </div>
                  <div class="card-body text-center">
                    <h5 class="card-title ">{{item.name}}</h5>
                  </div>
                  <!-- Ingresar cantidad -->
                  <div class="container-fluid mb-2">
                    <div class="row">
                      <div class="col text-center">
                        <p class="text-center fw-bold">Cantidad</p>
                      </div>
                      <div class="input-group mb-3">
                        <button class="btn btn-outline " type="button" id="button-image"><img
                            src="assets/images/menos.png" alt="" @click="cant(item,0)"></button>
                        <input type="number" class="form-control rounded text-center" placeholder=""
                          aria-label="Example text with button addon" aria-describedby="button-addon1"
                          v-model="item.cant">
                        <button class="btn btn-outline " type="button" id="button-image"><img
                            src="assets/images/mas.png" alt="" @click="cant(item,1)"></button>
                      </div>
                    </div>
                  </div>
                  <!-- /Ingresar Cantidad -->
                  <div class="card-footer">
                    <div class="container">
                      <div class="row">
                        <div class="col text-center">
                          <button type="button" class="btn btn-hotDog" @click="agg(item)"> Agregar</button>

                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <!-- /Cards -->
        </div>
      </section>
      <!-- /Hot Dogs-->

      
      <!-- Footer -->
      <footer id="footer" class="pb-4 pt-4 bg-dark">
        <div class="container">
          <div class="row justify-content-center">
            <div class="col text-center p-2">
              <a href="#" class="text-center"> Bogota-Colombia</a>
            </div>
            <div class="col-md-1 col-2  text-center ">
              <a href="#"><img src="assets/images/instagram.png" alt="" width="40px"></a>

            </div>
            <div class="col-md-1 col-2 text-center ">
              <a href="https://www.facebook.com/"><img src="assets/images/facebook.png" alt="" width="40px"> </a>

            </div>
            <div class="col text-center p-2">
              <a href="#" class="">Contáctanos: 60158897</a>
            </div>

          </div>
        </div>
      </footer>
      <!--/Footer  -->

      <!-- Modal -->
      <!-- Hamburguesas -->
      <section id="hamburguesa-modal">
        <div class="container" v-for="item in dataFood[0].burger" :key="item.id">
          <!-- Modal hamburger Mega Stacker -->
          <div class="modal fade" :id="item.id" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
            <div class="modal-dialog">
              <div class="modal-content" id="modal-content-h">
                <div class="modal-header">
                  <h5 class="modal-title" id="exampleModalLabel">{{item.name}}</h5>
                  <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body text-center" id=" modal-body-h">
                  <div class="modal-body-image">
                    <img :src="item.img" :alt="item.name">
                  </div>
                </div>
                <div class="modal-footer">
                  <div class="container">
                    <div class="row">
                      <div class="col">
                        <h5 id="ingredients">Ingredientes:</h5>
                      </div>
                      <div class="row">
                        <div class="col">
                          <p>{{item.description}}</p>
                        </div>
                        <div class="row">
                          <div class="col">
                            <h4>${{item.price}}</h4>
                          </div>
                        </div>
                        <!-- Ingresar cantidad -->
                        <div class="container-fluid mb-2">
                          <div class="row">
                            <div class="col text-center">
                              <p class="text-center fw-bold">Cantidad</p>
                            </div>
                            <div class="input-group mb-3">
                              <button class="btn btn-outline " type="button" id="button-image"><img
                                  src="assets/images/menos.png" alt="" @click="cant(item,0)"></button>
                              <input type="number" class="form-control rounded text-center" placeholder=""
                                aria-label="Example text with button addon" aria-describedby="button-addon1"
                                v-model="item.cant">
                              <button class="btn btn-outline " type="button" id="button-image"><img
                                  src="assets/images/mas.png" alt="" @click="cant(item,1)"></button>
                            </div>
                          </div>
                        </div>
                        <!-- /Ingresar cantidad -->
                        <!-- Botón Agregar -->
                        <div class="container">
                          <div class="row">
                            <div class="col text-center mt-3">
                              <button type="button" class="btn btn-outline-light btn-lg" @click="agg(item)">
                                Agregar</button>
                            </div>
                          </div>
                        </div>
                        <!-- /Botón Agregar -->
                      </div>
                    </div>
                  </div>

                </div>
              </div>
            </div>
          </div>
          <!-- /Hamburguesa Mega Stacker -->
        </div>


      </section>
      <!-- /Hamburguesas -->

      <!-- Perros calientes -->
      <section id="hot-dog-modal">
        <div class="container" v-for="item in dataFood[0].hotDog" :key="item.id">
          <!-- Hot Dog Americano -->
          <div class="modal fade" :id="item.id" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
            <div class="modal-dialog">
              <div class="modal-content" id="modal-content-p">
                <div class="modal-header">
                  <h5 class="modal-title" id="exampleModalLabel">{{item.name}}</h5>
                  <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body text-center" id="modal-body-p">
                  <div class="modal-body-image">
                    <img :src="item.img" :alt="item.name">
                  </div>
                </div>
                <div class="modal-footer">
                  <div class="container">
                    <div class="row">
                      <div class="col">
                        <h5 id="ingredients">Ingredientes:</h5>
                      </div>
                      <div class="row">
                        <div class="col">
                          <p>{{item.description}}</p>
                        </div>
                        <div class="row">
                          <div class="col">
                            <h4>${{item.price}}</h4>
                          </div>
                        </div>
                        <!-- Ingresar cantidad -->
                        <div class="container-fluid mb-2">
                          <div class="row">
                            <div class="col text-center">
                              <p class="text-center fw-bold">Cantidad</p>
                            </div>
                            <div class="input-group mb-3">
                              <button class="btn btn-outline " type="button" id="button-image"><img
                                  src="assets/images/menos.png" alt="" @click="cant(item,0)"></button>
                              <input type="number" class="form-control rounded text-center" placeholder=""
                                aria-label="Example text with button addon" aria-describedby="button-addon1"
                                v-model="item.cant">
                              <button class="btn btn-outline " type="button" id="button-image"><img
                                  src="assets/images/mas.png" alt="" @click="cant(item,1)"></button>
                            </div>
                          </div>
                        </div>
                        <!-- /Ingresar cantidad -->
                        <!-- Botón Agregar -->
                        <div class="container">
                          <div class="row">
                            <div class="col text-center mt-3">
                              <button type="button" class="btn btn-outline-light btn-lg" @click="agg(item)">
                                Agregar</button>
                            </div>
                          </div>
                        </div>
                        <!-- /Botón Agregar -->
                      </div>
                    </div>
                  </div>

                </div>
              </div>
            </div>
          </div>
          <!-- /Hot Dog Americano -->

        </div>


      </section>
      <!-- /Perros calientes -->

      <!-- Carrito de compras -->
      <!-- <div class="modal fade" id="carrito" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog modal-lg">
          <div class="modal-content">
            <div class="modal-header">
              <h5 class="modal-title" id="exampleModalLabel">Carrito de compras</h5>
              <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
            </div>
            <div class="modal-body">
              <table class="table table-striped">
                <thead>
                  <tr>
                    <th scope="col">Producto</th>
                    <th scope="col">Cant</th>
                    <th scope="col">Nombre</th>
                    <th scope="col">Precio U</th>
                    <th scope="col">Precio Total</th>
                  </tr>
                </thead>
                <tbody v-if="dataTable.length>0">
                  <tr v-for="(item, index) in dataTable" :key="item.id">
                    <th><img :src="item.img" :alt="item.name" style="height: 50px; width: 50px;"></th>
                    <th scope="row">{{item.cant}}</th>
                    <td>{{item.name}}</td>
                    <td>${{item.price}}</td>
                    <td>${{item.total=item.cant*item.price}}</td>
                    <td class="border"><button class="btn btn-danger" @click="deleteProduct(index)"
                        type="button">Eliminar</button></td>
                  </tr>
                  <tr>
                    <th class="text-center">Total</th>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td>${{totall}}</td>
                  </tr>
                </tbody>
                <tbody v-else>
                  <td>hay productos agregados al carrito</td>
                  <td></td>
                  <td></td>
                  <td></td>
                  <td></td>
                  <td></td>
                </tbody>
              </table>
              <div class="modal-footer">
                <button type="button" class="btn btn-secondary" data-bs-dismiss="modal" @click="cancel">Cancela</button>
                <button type="button" class="btn btn-primary" @click="buy" v-if="dataTable.length===0">Comprar</button>
                <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#pagos" v-else>Comprar</button>
              </div>
            </div>
          </div>
        </div>
      </div> -->
      <!-- /Carrito de compras -->

      <!-- Comprar -->
      <!-- <div class="modal fade" id="pagos" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog">
          <div class="modal-content">
            <div class="modal-header">
              <h5 class="modal-title" id="exampleModalLabel">Metodos de pago</h5>
              <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
            </div>
            <div class="modal-body">
              <div class="d-flex justify-content-center mt-3">
                <div class="col-1 d-flex align-items-center ">
                  <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1" value="1"
                    v-model="pago">
                </div>
                <div class="col-4 align-items-end">
                  <img src="assets/images/nequi.svg" alt="" style="width: 200px; height: 50px;" class="align-items-end">
                </div>
              </div>
              <div class="d-flex justify-content-center mt-3">
                <div class="col-1 d-flex align-items-center ">
                  <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1" value="2"
                    v-model="pago">
                </div>
                <div class="col-4 align-items-end">
                  <img src="assets/images/mastercard.svg" alt="" style="width: 200px; height: 50px;" class="align-items-end">
                </div>
              </div>
              <div class="d-flex justify-content-center mt-3">
                <div class="col-1 d-flex align-items-center ">
                  <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1" value="3"
                    v-model="pago">
                </div>
                <div class="col-4 align-items-end">
                  <img src="assets/images/efectivo.svg" alt="" style="width: 200px; height: 50px;" class="align-items-end">
                </div>
              </div>
            </div>
            <div class="modal-footer">
              <button type="button" class="btn btn-secondary" data-bs-dismiss="modal" >Cancelar</button>
              <button type="button" class="btn btn-danger" @click="toBuy" v-if="pago==0">Pagar</button>
              <button type="button" class="btn btn-danger" @click="toBuy" data-bs-dismiss="modal" v-else>Pagar</button>
            </div>
          </div>
        </div>
      </div> -->
      <!-- /Comprar -->

  </div>
</template>

<script>
export default {
  data(){
    return{
      dataFood: [
      {
        burger: [
          {
            idModal: "#h01",
            id: "h01",
            name: "Hamburguesa Mega Stacker",
            img: "assets/food/hamburgerMegaStacker.png",
            description:
              "Cuenta con triple carne de res 113 gr C/U a la parrilla, queso, tocineta crujiente y deliciosa salsa stacker sobre un pan con ajonjolí",
            price: 35000,
            cant: 1,
            total: 0,
          },
          {
            idModal: "#h02",
            id: "h02",
            name: "Hamburguesa Whopper",
            img: "assets/food/hamburgerWhopper.png",
            description:
              "Nuestra WHOPPER® cuenta con carne 113 gr de res a la parrilla, preparada con jugosos tomates, lechuga recién cortada, pepinillos, cebollas en rodajas y cremosa mayonesa sobre un pan con ajonjolí tostado perfectamente y ketchup ¡Pídela en COMBO con papas a la francesa y tu bebida favorita!",
            price: 22000,
            cant: 1,
            total: 0,
          },
          {
            idModal: "#h03",
            id: "h03",
            name: "Hamburguesa Xl Queso Tocineta",
            img: "assets/food/hamburgerXlQuesoTocineta.png",
            description:
              "Cuenta con doble carne de res 48 gr c/u a la parrilla, jugosos tomates, lechuga recién cortada, y cremosa mayonesa sobre un pan sandwich con ajonjolí.",
            price: 22000,
            cant: 1,
            total: 0,
          },
          {
            idModal: "#h04",
            id: "h04",
            name: "Hamburguesa XT BBQ",
            img: "assets/food/hamburgerXTBQQ.png",
            description:
              "Cuenta con una carne de res a la parrilla de 198 gr, queso, lechuga, tomates, cebolla crujiente, salsa BBQ y cremosa mayonesa sobre un pan esponjoso de maíz.",
            price: 32000,
            cant: 1,
            total: 0,
          },
        ],
        hotDog: [
          {
            idModal: "#hd01",
            id: "hd01",
            name: "Hot Dog Americano",
            img: "assets/food/HotDogAmericano.jpg",
            description:
              "Bacon ahumado, doble queso, pepinillos, cebolla crunch, salsa de tomate y mostaza. Salchicha suiza, tocineta",
            price: 18000,
            cant: 1,
            total: 0,
          },
          {
            idModal: "#hd02",
            id: "hd02",
            name: "Hot Dog Argentino",
            img: "assets/food/HotDogArgentino.jpg",
            description:
              "Queso cervecero, pimentones asados, chimichurri y chorizo artesanal.",
            price: 19000,
            cant: 1,
            total: 0,
          },
          {
            idModal: "#hd03",
            id: "hd03",
            name: "Hot Dog Azul",
            img: "assets/food/HotDogAzul.jpg",
            description:
              "Queso roquefort, tomates rostizados, rugula, hongos, salchicha alemana.",
            price: 18000,
            cant: 1,
            total: 0,
          },
          {
            idModal: "#hd04",
            id: "hd04",
            name: "Hot Dog Borracho",
            img: "assets/food/HotDogBorracho.jpg",
            description:
              "Demiglace de Buchanan’s , cebollas caramelizadas con cerveza a8tesanal, queso cheddar y tocineta ahumada, Salchicha suiza,tocineta.",
            price: 19000,
            cant: 1,
            total: 0,
          },
        ],
      },
    ], // Datos comida
    }
  }
}
</script>

<style>

</style>