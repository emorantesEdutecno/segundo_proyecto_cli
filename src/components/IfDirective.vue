<template>
    <div id="IfDirective">
            <h2>Contador de Likes {{ likes }}</h2>
            <div v-if="likes ===0"><p>No hay likes</p></div>
            <div v-else-if="likes < 10"><p>Vamos por los 10 likes</p></div>
            <div v-else-if="likes <20"><p>Vamos por los 20 likes</p></div>
            <div v-else><p>Eres una estrella de los likes</p></div>
            <hr>
            <button v-on:click="addLike">Agregar Likes</button>
            <button v-on:click="removeLike">Quitar Likes</button>
    </div>
</template>

<script>
export default{
    name:'if-directive-component',
    data: function(){
        return{
            likes:0,
        }
    },
    methods: {
        addLike:function(){
            this.likes++;
        },
        removeLike:function(){
            if(this.likes > 0){
                this.likes--;
            }
        },
    },

}
</script>


<style scoped>
#IfDirective{
    background-color: darkolivegreen;
    color:bisque;
}
</style>