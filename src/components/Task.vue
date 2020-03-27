<template>
  <div>
    <form @submit.prevent="addTask">
      <span>{{title}}</span>
      <input v-model="newTask" placeholder="Ingresa nuevas tareas">
      <button type="submit">Añadir</button>
    </form>

    <ul>
      <li v-for="task in tasks" :key="task">
        {{task}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'Tarea:',
      tasks: [],
      newTask: ''
    }
  },
  methods: {
      addTask(e) {
         this.tasks.push(this.newTask);
            // Limpiar input luego de agregar tarea
            this.newTask = '';
      }
    }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
