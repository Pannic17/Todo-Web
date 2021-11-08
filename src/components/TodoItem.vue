<template>
  <div class="todo_item">
    <label>
      <input type="checkbox" />
      TODO
      <span class="check_button"></span>
    </label>
  </div>
</template>

<script>
export default {
  name: "TodoItem"
}
</script>

<style>
.todo_item {
  background: white;
  padding: 16px;
  border-radius: 8px;
  color: #626262;

}
.todo_item label {
  position: relative;
  display: flex;
  align-items: center;
  cursor: pointer;
}
.todo_item.done label {
  text-decoration: line-through;
  font-style: italic;
}
.todo_item label span.check_button {
  position: absolute;
  top: 0;
}
.todo_item label span.check_button::before,
.todo_item label span.check_button::after {
  content: "";
  display: block;
  position: absolute;
  width: 18px;
  height: 18px;
  border-radius: 50%;
}
.todo_item label span.check_button::before {
  border: 1px solid #b382f9;
}
.todo_item label span.check_button::after {
  transition: 0.4s;
  background: #b382f9;
  transform: translate(1px, 1px) scale(0.8);
  opacity: 0;
}
.todo_item input {
  margin-right: 16px;
  opacity: 0;
}
.todo_item input:checked + span.check_button::after {
  opacity: 1;
}
</style>