<template>
  <div class="container pad">
    <app-base></app-base>
  </div>
</template>

<script>
import base from './components/base.vue'

export default {
  name: 'app',
  components: {
    'app-base': base
  },
  data () {
    return {

    }
  }
}
</script>
