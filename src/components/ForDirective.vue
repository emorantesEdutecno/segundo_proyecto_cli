<template>
    <div id="forDirective">
        <h2>Mis conocimientos en programación web son</h2>
        <ul>
            <li v-for="habilidad in skills" :key="habilidad">{{ habilidad }}</li>
        </ul>
        <hr>
        <div id="seccionAdd">
            <input type="text" v-model="skill">
            <button v-on:click="addSkill"> Agregar Skill</button>
        </div>
    </div>
</template>

<script>
export default{
    name:'for-directive-component',
    data: function(){
        return{
            skills: ['HTML', 'CSS', 'JS'],
            skill: '',
        }
    },
    methods:{
        addSkill: function(){
            this.skills.push(this.skill);
            this.skill='';
        },
    },
}
</script>

<style scoped>
#forDirective{
    background-color:lemonchiffon;
    text-align: left;
}
#seccionAdd{
    text-align: right;
}
</style>