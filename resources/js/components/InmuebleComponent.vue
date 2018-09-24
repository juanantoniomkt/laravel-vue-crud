<template>

            <div class="card col-12">
                
                <p>{{inmueble.id}} - Publicado el {{inmueble.fecha}}</p>

                <p>{{inmueble.nombre}}</p>

                <button class="btn btn-primary col-3">Editar inmueble</button>
                <button class="btn btn-danger col-3">Borrar inmueble</button>
            </div>

</template>

<script>
    export default {

        props: ['inmueble'],

        data(){
            return{}
        },


        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
