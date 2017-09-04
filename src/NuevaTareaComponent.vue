<template>
    <div class="input-group">
        <input type="text" placeholder="Escribe una nueva tarea" v-model="nuevaTarea" class="form-control" v-on:keyup.enter="agregarTarea">
        <span class="input-group-btn">
        <button type="button" v-on:click="agregarTarea" class="btn btn-primary">Agregar Tarea</button>
        </span>       
    </div>
</template>

<script>
export default {
    data(){//Enviando datos
        return{
            nuevaTarea: ''
        }
    },
    props: ['tareas', 'aumentarTarea'],//Recibir Datos
    methods: {
        agregarTarea(){
            var texto = this.nuevaTarea.trim();
            if(texto){
                this.tareas.push({
                texto: texto,
                terminada: false
                })

                //this.aumentarTarea()//Con esto le mandas algo al padre
            }
            this.nuevaTarea = '';
        }
    }
}
</script>