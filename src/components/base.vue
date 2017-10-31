<template>
  <div class="pad-2">
    <div class="pad">
      <input
        class="full-width"
        type="text"
        placeholder="Try typing something..."
        v-model="text"
        v-on:blur="isNull"
        v-on:focus="isNull"
        v-bind:class="{ hide: isEmpty }"
      >
    </div>
    <div class="pad text-center">
      <span v-on:click="addTodo" class="fa fa-plus"></span>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      text: '',
      isEmpty: false
    }
  },
  methods: {
    addTodo (ev) {
      
    },
    isNull () {
      if (this.text) {
        this.isEmpty = !this.isEmpty
      }
    }
  }
}
</script>
