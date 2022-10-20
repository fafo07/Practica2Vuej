<template>
    <div class="footer">
        <footer :style="`background-color: ${color}`">

        </footer>
    </div>
  </template>
  
  <script>
import { stringLiteral } from '@babel/types';

    export default {
    name: 'Footer',
    props: {
        color: {type: String},
    }
    }
  </script>