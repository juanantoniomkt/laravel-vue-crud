<template>
    <div class="row">

        <form-component @new="agregarPensamiento"></form-component>
        <pensamiento-component 
            v-for="pensamiento in pensamientos" 
            :key="pensamiento.id"
            :pensamiento="pensamiento"
            >
        </pensamiento-component>

    </div>
</template>

<script>
    export default {

        data(){
            return{
                pensamientos:[
                    {
                    'id':'1',
                    'nombre': 'quiero ir a la playa',
                    'fecha': '01/08/1990'
                    },

                    {
                    'id':'2',
                    'nombre': 'quiero beber agua',
                    'fecha': '01/08/2001'
                    },

                    {
                    'id':'3',
                    'nombre': 'no quiero cenar',
                    'fecha': '01/08/2002'
                    }
                ]
            }
        },

        methods:
        {

            agregarPensamiento(pensamiento)
            {
                this.pensamientos.unshift(pensamiento);
            }

        },

        mounted() {
            console.log('Component mounted.')
        }
    }
</script>