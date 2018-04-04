<template>
  <div>
    <div class="row">
      <div v-bind:class="{ error: hasError }" class="input-wrapper pad full-width">
        <input
          autofocus
          class="full-width text-input"
          type="text"
          placeholder="Try typing something..."
          v-model="text"
          v-on:keyup.13="addToDo"
        >
      </div>
      <div class="pad">
        <span v-on:click="addToDo" class="fa fa-plus"></span>
      </div>
    </div>
    <div class="row" v-for="toDo, i in toDos">
      <div class="pad">
        <input v-bind:id="'item' + i" type="checkbox">
        <label v-bind:for="'item' + i">{{ toDo }}</label>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: '',
      toDos: [],
      hasError: false
    }
  },
  methods: {
    addToDo() {
      if (this.text) {
        this.hasError = false;
        this.toDos.unshift(this.text);
        this.text='';
      } else {
        this.hasError = true;
      }
    }
  }
}
</script>
