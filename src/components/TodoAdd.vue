<template>
  <div class="input_add">
    <input type="text" name="todo" v-model="todoContent" @keyup.enter="emitAddTodo"/>
    <button @click="emitAddTodo">
      <i class="plus"></i>
    </button>
  </div>
</template>

<script>
import {ref} from "vue";

export default {
  name: "TodoAdd",
  props: ["tid"],
  setup(props, context) {
    return triggerEmitAddTodo(props.tid, context.emit);
  }
}

function triggerEmitAddTodo(tid, emit){
  const todoContent = ref("");
  const emitAddTodo = () => {
    const todo = {
      id: tid,
      content: todoContent.value,
      completed: false,
    };
    emit("addTodo", todo)
    todoContent.value = "";
  };
  return {
    todoContent,
    emitAddTodo,
  };
}
</script>

<style>
.input_add {
  position: relative;
  display: flex;
  align-items: center;
}

.input_add input {
  padding: 16px 52px 16px 18px;
  border-radius: 48px;
  border: none;
  outline: none;
  box-shadow: 0 0 24px rgba(0,0,0,0.08);
  width: 100%;
  font-size: 16px;
  color: #626262;
}

.input_add button {
  width: 46px;
  height: 46px;
  border-radius: 50%;
  background: linear-gradient(#c0a5f3, #7f95f7);
  border: none;
  outline: none;
  color: white;
  position: absolute;
  right: 0;
  cursor: pointer;
}
.input_add .plus {
  display: block;
  width: 100%;
  height: 100%;
  background: linear-gradient(#fff, #fff), linear-gradient(#fff, #fff);
  background-size: 50% 2px, 2px 50%;
  background-position: center;
  background-repeat: no-repeat;
}
</style>
