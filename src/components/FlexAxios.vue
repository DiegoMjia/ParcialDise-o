<template>
  <div>
    <div class="ContenedorTitle">
        <div class="genero">
            <div v-for="dato in datos" :key="dato.id">
                {{ dato.nombre }}
            </div>
        </div>
    </div>
  </div>
</template>

<script>

import axios from 'axios';

export default {
name: 'FlexAxios',

data() {
    return {
        datos: [],
    }
},

methods: {
    getGeneros: async function () {
        const urlGet = 'https://cobuses.com.co/APIV2/model/radio.php?dato=getallgeneros';

        const vue = this;
        await axios.get(urlGet)
        .then((response) => {
            console.log("Respuesta axios", response.data);
            vue.datos = response.data;
        })
        .catch(()=> {
            console.log("Hubo un error");
        })
        .finally(()=> {
            console.log("Termino.")
        })
    }
},

created: function () {
    this.getGeneros();
  }
}
</script>

<style>
.ContenedorTitle {
    background-color: #21404B;
}
.genero {
    background-color: #455A64;
    height: auto;
    width: 30%;
    color: #fff;
    float: right;
}
</style>