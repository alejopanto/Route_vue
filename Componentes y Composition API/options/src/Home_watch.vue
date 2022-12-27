<template>
  <div>
    <h1>{{ obj }}</h1>
  </div>
</template>

<script>
import { reactive, watch } from "vue";

export default {
  setup() {
    const obj = reactive({ counter: 0 });

    setInterval(() => obj.counter++, 500);

    watch(
      () => obj.counter,
      (value, oldValue) => {
        console.log(value, oldValue);
      }
    );

    return {
      obj,
    };
  },
};
</script>
