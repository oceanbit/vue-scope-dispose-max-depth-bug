<template>
  <div class="app-container">
    <Comp />
  </div>
</template>

<script>
import {
  defineComponent,
} from 'vue';
import Comp from './Comp.vue';

export default defineComponent({
  name: 'App',
  components: {
    Comp
  }
});
</script>
