<template>
    <div class="Product">
        <div class="container">
            <div class="row">
                <h3> {{producto.nombre}}</h3>
            </div>
            <div class="row">
                <div class="col-12 col-sm-6 col-md-4 ">
                    <img class="img-fluid" :src="producto.imagen" alt="" width="100%">
                </div>
                <div class="col-12 col-sm-6  col-md-8">
                    <h6><span v-html="producto.descripcion"></span></h6>
                    <div class="p-3 mb-2 text-white" :style="precioEstilos">
                        Precio: {{producto.precio}} BOB
                    </div>
                    <h5>Color</h5>
                    <div>
                        <div class="color-box clic" v-for="color in producto.colores" :style="`background:${color}`"
                            v-on:click="pedido.color=color;selectColor(color)"></div>
                    </div>
                    <h5>Cantidad</h5>
                    <div class="quantity">
                        <button v-on:click="pedido.cantidad=restartCounter(pedido.cantidad)">-</button>
                        <div>{{pedido.cantidad}}</div> <button v-on:click="pedido.cantidad += 1">+</button>
                    </div>
                    <div class="buy-box">
                        <button type="button" class="btn btn-primary" v-on:click="buyDrone(pedido, producto.id)" :disabled="pedido.color==null">Comprar</button>
                    </div>

                </div>
            </div>
        </div>
    </div>
</template>
  
<script>
import { stringLiteral } from '@babel/types';

export default {
    name: 'Product',
    props: {
        producto: { type: Object },
        precioEstilos: { type: Array }
    },
    data()
    {
        return {
            pedido:
            {
                id: null,
                cantidad: 1,
                color: null
            }
        }
    },
    methods: {
        restartCounter: function (cantidad) {
            if (cantidad > 1) {
                cantidad -= 1
                return cantidad
            }
            else {
                alert("La cantidad no puede ser menor a 1")
                return cantidad
            }
        },


        buyDrone: function (pedido, id) {
            pedido.id = id
            alert("{ \"id\" " + pedido.id + ", \"cantidad\" " + pedido.cantidad + ", \"color\" " + pedido.color + " }")
        },

        selectColor: function (color) {
            alert("Seleciono el color: " + color)
        }

    }

}
</script>


