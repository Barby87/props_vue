<template>
  <div>
      <span>{{title}}</span>
      <input v-model="newTask" @keyup.enter="addTask" placeholder="Ingresa nuevas tareas">
      <input @click="addTask" type="submit" value="Agregar">

    <ul>
      <li v-for="task in tasks" :key="task">
        {{task}}
        <button @click="deleteTask(task)">Eliminar</button>
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
      addTask() {
         this.tasks.push(this.newTask);
            // Limpiar input luego de agregar tarea
            this.newTask = '';
      },

      deleteTask(task) {
        this.tasks.splice(this.tasks.indexOf(task), 1);
      }

    }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
