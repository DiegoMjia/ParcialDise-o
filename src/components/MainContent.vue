<template>
  <div>
    <main class="main-content">
        <div class="contenedor">
        <div class="gridContent" v-for="emisoras in emisora" :key="emisoras.id">
            <img :src="emisoras.imagen" alt="">
        </div>
      </div>
    </main>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'MainContent',

  data() {
    return {
      emisora: []
    }
  },

  methods: {
    getPelis: async function () {
      const urlGet = 'https://cobuses.com.co/APIV2/model/radio.php?dato=getallemisoras';
      const vue = this;
      
      await axios
      .get(urlGet)
      .then((response) => {
        vue.emisora = response.data;
      })
      .catch((error)=> console.log("Hubo un error.", error))
      .finally(()=> {
        console.log("La consulta termino");
      })
    }
  },

  created: function () {
    this.getPelis();
  }
};
</script>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  background-color: #1c313a;
}

.main-content {
  background-color: #1c313a;
  width: 70%;
}


.contenedor {
  display: grid;
  grid-template-rows:repeat(1fr, 6);
  grid-template-columns: repeat(1fr, 3);

}
</style>
