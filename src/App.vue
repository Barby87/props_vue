<template>
  <div id="app">
     <span>{{title}}</span>
      <input v-model="newTask" @keyup.enter="addTask" placeholder="Ingresa nuevas tareas">
      <input @click="addTask" type="submit" value="Agregar">

    <Task :task="task" v-for="task in tasks" :key="task"/>
  </div>
</template>

<script>
// Importando componente
import Task from './components/Task.vue';

export default {
  name: 'App',
  components: {
    Task
  },

  data() {
    return {
      title: 'Tarea:',
      tasks: [],
      newTask: ''
    }
  },

  methods: {
     addTask() {
         this.tasks.push(this.newTask);
            // Limpiar input luego de agregar tarea
            this.newTask = '';
      },
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
