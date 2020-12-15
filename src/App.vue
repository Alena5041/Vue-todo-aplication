<template>
  <div id="app">
    <b-container>
      <h1>Todo application</h1>
      <b-row class="justify-content-md-center">
        <b-col lg="8" md="10" sm="12">
          <b-card
            no-body
            style="background: #f5f5f5"
          >
            <AddTodo
              @add-todo="addTodo"
            />
            <TodoList
              v-bind:todos="todos"
              @remove-todo="removeTodo"
            />
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import TodoList from '@/components/TodoList'
import AddTodo from '@/components/AddTodo'
export default {
  name: 'app',
  data () {
    return {
      todos: [
        { id: 1, title: 'first', completed: false },
        { id: 2, title: 'second', completed: false },
        { id: 3, title: 'third', completed: false }
      ]
    }
  },
  methods: {
    removeTodo (id) {
      this.todos = this.todos.filter(t => t.id !== id)
    },
    addTodo (todo) {
      this.todos.push(todo)
    }
  },
  components: {
    TodoList, AddTodo
  }
}
</script>

<style>
#app {
  text-align: center;
  margin-top: 60px;
}
h1 {
  color: #cd0000;
  letter-spacing: -2px;
}
</style>
