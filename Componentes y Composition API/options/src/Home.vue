<template>
  <div>
    <h1>{{ fullName }}</h1>
  </div>
  <div>
    <h1>{{ username }}</h1>
  </div>
  <button ref="btn">Click!</button>
</template>

<script>
import { ref, toRefs, computed, watch, inject } from "vue";

export default {
  props: {
    firstName: String,
    lastName: String,
  },
  setup(props) {
    const { firstName, lastName } = toRefs(props);

    const fullName = computed(() => {
      return `${firstName.value} ${lastName.value}`;
    });

    const username = inject("username");

    const btn = ref(null);

    watch(btn, (val) => {
      console.log(val);
    });

    return {
      fullName,
      username,
      btn,
    };
  },
};
</script>
