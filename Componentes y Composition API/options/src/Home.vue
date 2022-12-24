<template>
  <div>
    <h1>{{ obj }}</h1>
  </div>
</template>

<script>
import { reactive } from "vue";

export default {
  setup() {
    const obj = reactive({ counter: 0 });

    setInterval(() => obj.counter++, 500);

    return {
      obj,
    };
  },
};
</script>
