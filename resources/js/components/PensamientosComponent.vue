<template>
    <div class="row">

        <form-component @new="agregarPensamiento"></form-component>
        <pensamiento-component 
            v-for="(pensamiento, index) in pensamientos" 
            :key="pensamiento.id"
            :pensamiento="pensamiento"
            @update="actualizarPensamiento(index, ...arguments)"
            @delete="borrarPensamiento(index)"
            >
        </pensamiento-component>

    </div>
</template>

<script>
    export default {

        data(){
            return{
                pensamientos:
                [

                ]
            }
        },

        mounted() 
        {
            axios.get('/pensamientos').then((response) =>
            {

            this.pensamientos = response.data;

            } );
        },

        methods:
        {

            agregarPensamiento(pensamiento)
            {
                this.pensamientos.unshift(pensamiento);
                
            },

            borrarPensamiento(index)
            {
                this.pensamientos.splice(index,1);
            },

            actualizarPensamiento(index, pensamiento)
            {

   

                this.pensamientos[index] = pensamiento;
            }

    

        },

    }
</script>