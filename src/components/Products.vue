<template>
    <div class="card" style="width: 18rem;">
        <div class="card-body">
            <h5 class="card-title">{{producto.nombre}}</h5>
            <img :src="producto.imagen" alt="" width="100%">
            <p class="card-text">{{producto.descripcion}}</p>
            <div class="producto-relacionado-precio">Precio: {{producto.precio}} BOB</div>
            <div>
                <div>
                    <div class="color-box clic" v-for="color in producto.colores" :style="`background:${color}`"></div>
                </div>
            </div>
        </div>

    </div>
</template>
  
<script>
import { stringLiteral } from '@babel/types';

export default {
    name: 'Products',
    props: {
        producto: { type: Object }
    }
}
</script>

