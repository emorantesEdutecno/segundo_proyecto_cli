<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <hr>
    <!-- la notación de mustaches es para hacer one way data binding en los contenidos de las etiquetas-->
    <p id="parrafo1">{{ info  }}</p>
    <!-- la notación de la directiva v-bind es para hacer one way data binding con los atributos de una etiquta html-->
    <input id="cajaTexto1" type="text" v-bind:value="mensaje"><br>
    <!-- cuando se coloca @ en una ruta , significa que el recurso se comienza a buscar desde la raiz src
    <img src="@/assets/img/matrix.jpg" alt="matrix">
    -->
    <!-- one way data binding con una imagen que es tratada como un módulo con la función require-->
    <img v-bind:src="rutaImagen" v-bind:alt="nombreImagen">
    <hr>
    <!-- Utilizamos en la aplicación principal los componentes creados como si fueran etiquetas html-->
    <TwoWayComponent></TwoWayComponent>
<hr>
    <IfDirectiveComponent />
<hr>
  <ForDirectiveComponent></ForDirectiveComponent>
<hr>
  </div>
</template>

<script>
// importar el componente recien creado y le damos un nombre
import TwoWayComponent from '@/components/TwoWay.vue';
import IfDirectiveComponent from '@/components/IfDirective.vue';
import ForDirectiveComponent from '@/components/ForDirective.vue';

export default {
  name: 'App',
  // registramos el componente recien importado en la sección components
  components: {
    TwoWayComponent,
    IfDirectiveComponent,
    ForDirectiveComponent
}, 
  data: function(){
      return{
        info: 'One Way Data Binding usando mustaches',
        mensaje: 'usando directiva v-bind',
        // cualquier imagen traida directamente desde la web se pueda alojar en una propiedad del modelo de datos
        // rutaImagen: 'https://scottmanning.com/wp-content/uploads/2003/07/merovingian-800x400.jpg',
        rutaImagen: require('@/assets/img/matrix.jpg') ,
        nombreImagen:'matrix',
      }
  },
  methods:{
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#parrafo1{
  background-color: aquamarine;
  color:purple;
  font-size: 25px;
}

#cajaTexto1{
  background-color: orange;
  color:blue;
  font-size: 18px;
}
</style>
