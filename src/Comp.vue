<template>
  <div></div>
</template>

<script>
import {defineComponent, onScopeDispose, ref} from 'vue';

// Placing this + "setup()" in "App" does not
// have the same bug
const counter = ref(0);

export default defineComponent({
  name: 'Comp',
  setup() {
    counter.value += 1;
    console.log("MOUNTED", counter.value);

    console.log("COMMENT/UNCOMMENT TO REFRESH & SHOW BUG");

    // `onUnmounted` doesn't have the same bug
    onScopeDispose(() => {
      counter.value -= 1;
      console.log("UNMOUNTED", counter.value);
    })
  }
});
</script>
