<template>
  <Navbar :titulo="this.configuracionPagina.marca" :menuColor="this.configuracionPagina.menuColor" :menus="this.configuracionPagina.menus" />
  <router-view />
  <Footer :color="this.configuracionPagina.footerColor" />
</template>

<script>
// @ is an alias to /src
import Navbar from '@/components/Navbar.vue';
import Footer from  '@/components/Footer.vue';
export default {
  components: {
    Navbar,
    Footer
  },
  data: () => ( {
      configuracionPagina: {
        marca: "MegaDron",
        menuColor: "lightblue",
        footerColor: "slategrey",
        precioEstilos: "background: orangered; color: white; font-weight: bold",
        menus: [
          {
            etiqueta: "Inicio",
            url: "?"
          },
          {
            etiqueta: "Tienda",
            url: "?"
          }
        ]
      },  
  })
}
</script>




<style>
.color-box {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  margin: 7px;
  display: inline-block;
}

.clic {
  cursor: pointer;
}

.quantity button {
  border-radius: 50%;
  display: inline-block;
  width: 30px;
}

.quantity div {
  text-align: center;
  min-width: 30px;
  display: inline-block;
  font-weight: bold;
}

.buy-box {
  margin: 20px;
}

footer {

  text-align: center;
  padding: 30px 10px;
  margin-top: 50px;
  min-height: 100px;
}

.container {
  margin-top: 50px;
}

.producto-relacionado-precio {
  background: orangered;
  color: white;
  text-align: center;
  padding: 10px;
}
</style>
