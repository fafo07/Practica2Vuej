<template>
  <div class="home">
    <div class="container" v-for="(product, index) in producto" :key="index">
      <Product  :producto="product" :precioEstilos="configuracionPagina.precioEstilos"></Product>
    </div>

    <div class="container">
      <div class="row">
        <h4>Productos relacionados</h4>
      </div>
      <div class="row">
        <div class="col" v-for="(product, index) in productos" :key="index">
          <Products  :producto="product"  ></Products>
        </div>
      </div>
    </div>

  </div>
</template>
<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Product from '@/components/Product.vue';
import Products from '@/components/Products.vue';


export default {
  name: 'HomeView',
  data: () => {
    return {
      productos: [],
      producto: {},
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
    }
  },
  components: {
    Product,
    Products
  },
  methods: {
    getProducts() {
      axios({
        method: "get",
        url: "http://localhost:3333/Productos"
      })
        .then(response => {
          this.productos = response.data.filter(b => b.id !== 1)
          this.producto = response.data.filter(b => b.id === 1)
        })
        .catch(e => console.log(e))
    }
  },
  mounted() {
    this.getProducts()
  }
}
</script>



