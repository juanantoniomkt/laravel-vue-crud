<template>
    <div class="container">

        <form action="" v-on:submit.prevent="nuevoPensamiento()">

            <div class="form-group">
                <label for="pensamiento">Pensamiento</label>
                <input type="text" class="form-control-lg" name="pensamiento" v-model="nombre" >
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
            nuevoPensamiento()
            {


                const params = 
                {
                    nombre: this.nombre
                }

                this.nombre = '';

                axios.post('/pensamientos', params).then((response) => 
                {
                    const pensamiento = response.data;
                    this.$emit('new', pensamiento);

                });
                              
            }
        }

    }
</script>