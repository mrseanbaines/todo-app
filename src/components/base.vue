<template>
  <div>
    <div class="row" v-for="toDo in toDos">
      <div class="pad">
        <input type="checkbox" v-model="isDone">
      </div>
      <div class="pad full-width">
        <input
          class="full-width text-input"
          type="text"
          placeholder="Try typing something..."
          v-model="text"
          v-on:blur="toggleInput"
          v-on:focus="toggleInput"
          v-bind:class="{ hide: isEmpty, completed: isDone }"
        >
      </div>
    </div>
    <div class="pad text-center">
      <span v-on:click="toDos++" class="fa fa-plus"></span>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      text: '',
      isEmpty: false,
      toDos: 1,
      isDone: false
    }
  },
  methods: {
    toggleInput () {
      if (this.text) {
        this.isEmpty = !this.isEmpty
      }
    }
  },
  computed: {

  }
}
</script>
