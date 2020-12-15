<template>
  <div>
    <b-form inline @submit.prevent="onSubmit" class="justify-content-between">
      <b-input-group>
        <b-form-input type="text" v-model="title"/>
      </b-input-group>
      <b-button variant="transparent" type="submit">
        <b-icon animation="fade" font-scale="1" icon="plus-circle" aria-hidden="true"></b-icon>
      </b-button>
    </b-form>
  </div>
</template>

<script>
export default {
  data () {
    return {
      title: ''
    }
  },
  methods: {
    onSubmit () {
      if (this.title.trim()) {
        const newTodo = {
          id: Date.now(),
          title: this.title,
          complited: false
        }
        this.$emit('add-todo', newTodo)
        this.title = ''
      }
    }
  }
}
</script>

<style scoped>
form {
  padding: 10px 10px 10px 80px;
  border-bottom: 1px dotted #ccc;
}
</style>
