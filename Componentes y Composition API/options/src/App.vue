<template>
  <div>
    <Home first-name="Alejandro" last-name="Pantoja" />
  </div>
</template>

<script>
import Home from "./Home.vue";
import { provide } from "vue";
export default {
  name: "App",
  components: { Home },
  setup() {
    provide("username", "Aletop");
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
