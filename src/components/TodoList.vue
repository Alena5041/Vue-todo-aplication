<template>
    <div>
      <ul>
        <TodoItem
          v-for="(todo, i) of todos"
          :todo="todo"
          :key="i"
          v-bind:index="i"
          v-on:remove-todo="removeTodo"
        />
      </ul>
    </div>
</template>

<script>
import TodoItem from '@/components/TodoItem'
export default {
  props: ['todos'],
  components: {
    TodoItem
  },
  methods: {
    removeTodo (id) {
      this.$emit('remove-todo', id)
    }
  }
}
</script>

<style scoped>
  ul {
    color: #555;
    font-size: 22px;
    padding: 0;
    margin: 0;
    font-family: courier, monospace;
    list-style: none;
  }
</style>
