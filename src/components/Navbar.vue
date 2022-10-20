<template>
    <div class="Navbar">
        <nav class="navbar navbar-expand-lg " :style="`background-color: ${menuColor};`">
            <div class="container-fluid">
                <a class="navbar-brand" href="#">{{ titulo }}</a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                    data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false"
                    aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarSupportedContent">
                    <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                        <li v-for="menu in menus">
                            <a :href="menu.url" class="nav-link">{{ menu.etiqueta }}</a>
                        </li>

                    </ul>
                </div>
            </div>
        </nav>
    </div>
  </template>
  
  <script>
import { stringLiteral } from '@babel/types';

    export default {
    name: 'Navbar',
    props: {
        titulo: {type: String},
        menuColor: {type: String},
        menus: {type: Array},
    }
    }
  </script>