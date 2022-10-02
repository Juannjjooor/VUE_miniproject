<template>
  <div>
    <input type="text" v-model="task">
    <button @click="addTask">Añadir</button>

    <ul>
      <li v-for="(item,index) in todos">
        {{item}}
        <button @click="removeTask(index)">X</button>    
      </li>
    </ul>
  </div>
</template>



<script>
  export default {
    name: "MyTodoList",
    data(){
      return {
        task: "",
        todos: [
          "Tarea1",
          "Tarea2",
          "Tarea3",
          "Tarea4",
          "Tarea5",
        ]
      }
    },
    methods: {
      addTask(){
        this.todos.push(this.task)
        this.task = ""
      },
      removeTask(index) {
        this.todos.splice(index)
      }

    }
  }

</script>

<style scoped>

</style>