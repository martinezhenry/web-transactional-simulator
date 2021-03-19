<template>
  <header class="header">
    <Menu />
  </header>
</template>

<script>
import Menu from "./Menu";
export default {
  name: "Header",
  components: {
    Menu,
  },
};
</script>

<style lang="css" scoped>

.header {
    background: rgb(0, 0, 0);
    color: white;
}

</style>