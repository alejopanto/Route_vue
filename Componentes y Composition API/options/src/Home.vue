<template>
  <div>
    <h1>{{ fullName }}</h1>
  </div>
  <div>
    <h1>{{ username }}</h1>
  </div>
</template>

<script>
import { toRefs, computed, inject } from "vue";

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

    return {
      fullName,
      username,
    };
  },
};
</script>
