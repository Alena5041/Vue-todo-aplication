<template>
  <li>
    <span v-bind:class="{done: todo.completed}" class="justify-content-between">
      <input type="checkbox" v-on:change="todo.completed = !todo.completed">
      <strong>{{index + 1}}</strong>
      {{todo.title}}
    </span>
    <b-button variant="transparent" v-on:click="$emit('remove-todo', todo.id)">
      <b-icon icon="trash" aria-hidden="true"></b-icon>
    </b-button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true
    },
    index: Number
  }
}
</script>

<style scoped>
  li {
    list-style: none;
    border-bottom: 1px dotted #ccc;
    text-indent: 25px;
    height: auto;
    padding: 10px 10px 10px 0;
    text-transform: capitalize;
    display: flex;
    justify-content: space-between;
  }
  li:last-child {
    border-bottom: none;
  }
  li:hover {
    background-color: #f0f0f0;
    transition: all 0.2s;
  }
  input {
    margin-right: 40px;
  }
  strong:before {
    content: '';
    position: absolute;
    top: 0;
    left: 60px;
    width: 4px;
    height: 100%;
    border-left: 1px solid #ffaa9f;
    border-right: 1px solid #ffaa9f;
  }
  .done {
    text-decoration: line-through;
  }
</style>
