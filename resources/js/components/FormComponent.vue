<template>
    <div class="container">

        <form action="" v-on:submit.prevent="nuevoInmueble()">

            <div class="form-group">
                <label for="inmueble">Inmueble</label>
                <input type="text" class="form-control-lg" name="inmueble" v-model="nombre" >
            </div>

            <button type="submit" class="btn btn-primary">Enviar</button>

        </form>

    </div>
</template>

<script>
    export default {
        

        data: function () {
        return {
            nombre: ''
        }
        },

        mounted() {
            console.log('Component mounted.')
        },

        methods: 
        {
            nuevoInmueble()
            {
                let inmueble = 
                {
                    id:2,
                    nombre: this.nombre,
                    fecha: '11/22/3333'
                };

                this.$emit('new', inmueble);
              
            }
        }

    }
</script>