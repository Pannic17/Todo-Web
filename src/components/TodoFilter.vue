<template>
  <div class="filters">
    <span class="filter_active">All</span>
    <span class="filter">Done</span>
    <span class="filter">Active</span>
  </div>
</template>

<script>
export default {
  name: "TodoFilter"
}
</script>

<style>
.filters {
  display: flex;
  margin: 24px 2px;
  color: #c0c2ce;
  font-size: 14px;
  cursor: pointer;
}
.filters .filter {
  margin-right: 20px;
  transition: 0.8s;
}
.filters .filter_active {
  margin-inline: 24px;
  color: #6b729c;
  transform: scale(1.2);
}
</style>