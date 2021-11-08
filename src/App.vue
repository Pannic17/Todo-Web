<template>
  <main>
    <div class="container">
      <h1>To-do App</h1>
      <TodoAdd :tid="todos.length" @addTodo="addTodo" />
      <TodoFilter />
      <TodoList :todos="todos" />
    </div>
  </main>
</template>

<script>
import TodoAdd from "@/components/TodoAdd"
import TodoFilter from "@/components/TodoFilter"
import TodoList from "@/components/TodoList";
import {ref} from "vue";

export default {
  name: 'App',
  components: { TodoAdd, TodoFilter, TodoList },
  setup() {
    const todos = ref([]);
    const addTodo = (todo) => todo.value.push(todo);
    return { todos, addTodo }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: Calibri, sans-serif;
}

main {
  width: 100vw;
  min-height: 100vh;
  display: grid;
  align-items: center;
  justify-items: center;
  background: rgb(203, 210, 240);
}

.container {
  width: 60%;
  max-width: 400px;
  box-shadow: 0 0 24px rgba(0,0,0,0.15);
  border-radius: 24px;
  padding: 48px 28px;
  background-color: rgb(245, 246, 252);
}

h1 {
  margin: 24px 0;
  font-size: 28px;
  color: #414873;
  text-align: center;
}






</style>
