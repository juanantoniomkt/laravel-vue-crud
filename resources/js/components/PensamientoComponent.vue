<template>

            <div class="card col-12">
                
                <p>{{pensamiento.id}} - Publicado el {{pensamiento.fecha}}</p>

                <input v-if="editMode" class="form-control" type="text" v-model="pensamiento.nombre" name="pensamientoEdit" id="pensamientoEdit">
                <p v-else>{{pensamiento.nombre}}</p>

                <button v-if="editMode" class="btn btn-success col-3" v-on:click='onClickUpdate()'>Guardar cambios</button>
                <button v-else class="btn btn-primary col-3" v-on:click='onClickEdit()'>Editar pensamiento</button>


                <button class="btn btn-danger col-3" v-on:click='onClickDelete()'>Borrar pensamiento</button>
            </div>

</template>

<script>
    export default {

        props: ['pensamiento'],

        data: function () 
        {
        return {

            editMode: false

            }
        },


        mounted() {
            console.log('Component mounted.')
        },

        methods: 
        {
            onClickDelete()
            {


                axios.delete(`/pensamientos/${this.pensamiento.id}`).then((data) =>
                {

                    console.log(data);

                    this.$emit('delete');

                });
                
            },

            onClickEdit()
            {
                this.editMode= true;
            },

            onClickUpdate()
            {

                const params =
                {
                    nombre : this.pensamiento.nombre
                };

                axios.put(`/pensamientos/${this.pensamiento.id}`, params).then((response) =>
                {
                    
                    this.editMode = false;

                    const pensamiento = response.data;

                    this.$emit('update', pensamiento);

                });


            }
        }
    }
</script>
