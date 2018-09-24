<template>

            <div class="card col-12">
                
                <p>{{pensamiento.id}} - Publicado el {{pensamiento.fecha}}</p>

                <p>{{pensamiento.nombre}}</p>

                <button class="btn btn-primary col-3">Editar pensamiento</button>
                <button class="btn btn-danger col-3">Borrar pensamiento</button>
            </div>

</template>

<script>
    export default {

        props: ['pensamiento'],

        data(){
            return{}
        },


        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
