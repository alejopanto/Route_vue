<template>
  <div>
    {{ text }}
    <strong>{{ algo }}</strong>
  </div>
</template>

<script>
import base from "./mixins/base";

export default {
  name: "App",
  mixins: [base],
  components: {},
  data() {
    return {
      text: "hola",
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.fade-leave-active,
.fade-enter-active {
  transition: opacity 0.5s ease;
}
</style>
