<template>
    <div id="twoWay">
        <h1> Two Way Data Binding</h1>
        <p>Tiene sentido en componentes de formularios</p>
        <input type="text" v-model="nombre" >
        <h2 id="contenido">{{  nombre  }}</h2>
        <button v-on:click="cambiarNombre">Cambia el modelo</button>
        <hr>
    </div>
</template>

<script>
export default{
    name: 'two-way-component',
    data: function(){
        return {
            nombre: ''
        }
    },
    methods:{
        cambiarNombre: function(){
            this.nombre = 'cambiamos el modelo de datos';
        }
    },
}
</script>


<style scoped>
#twoWay{
    background-color: goldenrod;
}
#contenido{
    background-color: coral;
    color:blueviolet;
    font-size: 19px;
}
</style>