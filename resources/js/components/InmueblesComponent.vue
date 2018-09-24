<template>
    <div class="row">

        <form-component @new="agregarInmueble"></form-component>
        <inmueble-component 
            v-for="inmueble in inmuebles" 
            :key="inmueble.id"
            :inmueble="inmueble"
            >
        </inmueble-component>

    </div>
</template>

<script>
    export default {

        data(){
            return{
                inmuebles:[
                    {
                    'id':'1',
                    'nombre': 'piso en ronda',
                    'fecha': '01/08/1990'
                    },

                    {
                    'id':'2',
                    'nombre': 'apartamento en arriate',
                    'fecha': '01/08/2001'
                    },

                    {
                    'id':'3',
                    'nombre': 'loft en torremolinos',
                    'fecha': '01/08/2002'
                    }
                ]
            }
        },

        methods:
        {

            agregarInmueble(inmueble)
            {
                this.inmuebles.unshift(inmueble);
            }

        },

        mounted() {
            console.log('Component mounted.')
        }
    }
</script>