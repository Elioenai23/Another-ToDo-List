<template>
  <form @submit.prevent="onSubmit">
    <h2 class="label-wrapper">
      <label for="new-todo-input" class="label_lg"> What needs to be done? </label>
    </h2>
    <input
      type="text"
      id="new-todo-input"
      name="new-todo"
      autocomplete="off"
      v-model="label"
      class="input_lg"
    />
    <button type="submit" class="btn btn_primary btn_lg">Add</button>
  </form>
</template>

<script>
export default {
  methods: {
    onSubmit() {
      if (this.label === '') {
        return
      }
      this.$emit('todo-added', this.label)
      this.label = ''
    }
  },
  data() {
    return {
      label: ''
    }
  }
}
</script>
