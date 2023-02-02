<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>

import CursosLista from './components/CursosLista.vue'

import api from './services/api.js'

export default {
  data: () => {
  },
  name: 'App',
  components: {
    CursosLista,
  },
  mounted(){
    api.get('/cursos').then(response => {
      console.log(response)
    })
  }
}
</script>
