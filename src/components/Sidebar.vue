<template>
  <div class="sidebar" :class="{'sidebar-active': this.isOpen}">
    <a href="#home" @click="toggleSidebar(false)">Home</a>
    <a href="#gallery" @click="toggleSidebar(false)">Gallery</a>
    <a href="#photographers" @click="toggleSidebar(false)">Photographers</a>
    <a href="#contact" @click="toggleSidebar(false)">Contact</a>
  </div>
</template>

<script>
export default {
  name: "sidebar",
  props: ["isOpen", "toggleSidebar"]
}
</script>

<style lang="scss">
@import "../assets/scss/variables.scss";

.sidebar {
  z-index: 1;
  transform: translateX(-100%);
  transition: transform 0.5s;
  width: 100%;
  height: 100vh;
  position: fixed;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  background: rgba($lighter-purple-rgb, 0.8);

  a {
    width: 100%;
    text-align: center;
    color: #fff;
    font-weight: bold;
    text-transform: uppercase;
    font-size: 1.5rem;
    padding: 1rem 0;
  }
}

.sidebar-active {
  transform: translateX(0);
}
</style>