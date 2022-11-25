<template>
  <div>
    <h1></h1>
    <button @click="toggleSidebar">Toggle Sidebar</button>
  </div>
</template>

<script>
import { collapsed, toggleSidebar } from "../components/sidebar/state";
export default {
  setup() {
    return { collapsed, toggleSidebar };
  },
  methods: {
    toggleBar() {
      console.log("entering tolle bar");
    },
  },
};
</script>

<style lang="scss" scoped></style>
