<template>
    <ul class="list-group">
        <li v-for="(tarea, indice) of tareas" class="list-group-item" v-bind:class="{terminada: tarea.terminada}">
        {{ tarea.texto }}
        <span class="pull-right">
            <button type="button" class="btn btn-success btn-xs glyphicon glyphicon-ok" v-on:click="tarea.terminada = !tarea.terminada"></button>
            <button type="button" class="btn btn-danger btn-xs glyphicon glyphicon-remove" v-on:click="borrar(indice)"></button>
        </span>
        </li>
    </ul>
</template>

<script>
export default {
  props: ['tareas','quitarTarea'],//recibe paramentros del padre
  methods: {
    borrar(indice){
      this.tareas.splice(indice,1)
      this.quitarTarea()//Con esto llamas la funcion del padre
    }
  }
}
</script>

<style scoped>
.terminada{/*scoped significa que este estilo aplica solamente para este componente */
  color: gray;
  text-decoration: line-through;
}
</style>
