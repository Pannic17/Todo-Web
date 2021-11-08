<template>
  <div class="todo_list">
    <TodoItem v-for="n in 3" :key="n"></TodoItem>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem";

export default {
  name: "TodoList",
  components: { TodoItem }
}
</script>

<style scoped>
.todo_list {
  display: grid;
  row-gap: 14px;
}


</style>