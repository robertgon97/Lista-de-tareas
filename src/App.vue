<template>
  <div id="app" class="container">
    <div id="app" class="jumbotron">
      <center><img src="./assets/logo.png"></center>
      <titulo :titulo="titulo" :numTareas="numTareas"></titulo> <!--Aqui se supone que deberias recibir el titulo -->
      <nueva-tarea v-bind:tareas="tareas" v-bind:aumentarTarea="aumentarTarea"></nueva-tarea>
      <lista-tareas v-bind:tareas="tareas" v-bind:quitarTarea="quitarTarea"></lista-tareas>
      <h6>Numero de Tareas: {{numTareas}}</h6>
    </div>
  </div>
</template>

<script>
import titulo from './TituloComponent.vue'
import NuevaTarea from './NuevaTareaComponent.vue'
import ListaTareas from './ListaTareasComponent.vue'
export default {
  components: {//Listado de componentes de la pagina
    titulo, 
    NuevaTarea,
    ListaTareas
  },
  data(){
    return {
      titulo: 'Lista de Tareas',//Esto es tu titulo
      numTareas:1,
      tareas: [{
        texto: 'Limpiar Cuarto',
        terminada: false
      }]
    }
  },
  methods:{
    aumentarTarea(){
      this.numTareas++
    },
    quitarTarea(){
      this.numTareas--
    }
  }
}
</script>

<style></style>
