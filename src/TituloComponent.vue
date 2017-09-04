<template>
  <div>
    <center><h2>{{ tituloMayusculas() }}</h2></center><!-- Si quieres quitar el error, necesitas quitar la funcion y cambiarlo por titulo-->
    <center><h3>{{ subtitulo }} {{numTareas}}</h3></center>
    <!-- DATO CURIOSO: No puedes tener dos cosas juntas como el h2 y h3... para solucionarlo se mete en un div y borralo! -->
  </div>
</template>

<script>
export default {
  data(){
    // return {
    //   titulo: 'Lista de Tareas', //Con esto envias el titulo deseado
    // }
  },
  props: {//Recibe el objeto u dato enviado desde componente padre (App.vue)
    titulo:{
      type: String,
      default: 'Tareas'//Si no le llega nada, por defecto le ponemos eso
    },
    subtitulo:{
      type: String,
      default:'Cosas que tienes por hacer:'//si no le llega nada por defecto le damos esto
    },
    numTareas:{
      type:Number,
      default: 0
    }
  },
  methods:{
    tituloMayusculas(){
      return this.titulo.toUpperCase();//Con esto los titulos que se reciban seran en mayusculas
    }
  }
}
</script>