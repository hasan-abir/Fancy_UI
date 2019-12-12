<template>
  <div class="navbar">
    <nav>
      <a href="#home">Home</a>
      <a href="#gallery">Gallery</a>
      <a href="#photographers">Photographers</a>
      <a href="#contact">Contact</a>
    </nav>
  </div>
</template>

<script>
export default {
  name: "navbar"
}
</script>

<style lang="scss">
@import "../assets/scss/mixins.scss";

.navbar {
  @include flex(center, center, row);
  background: #fff;
  position: fixed;
  top: 110px;
  z-index: 10;
  left: 50%;
  transform: translate(-50%, 0);
  width: 520px;
  border-radius: 2px;
  box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.5);
  nav {
    @include flex(center, center, row);
    a {
      flex: 1;
      color: #000;
      text-transform: uppercase;
      font-size: 0.9rem;
      padding: 1rem 0.8rem;
      transition: text-shadow 0.5s;
      &:hover,
      &:active {
        text-shadow: 0px 0px 0 #000, 1px 0px 0 #000, 0px 1px 0 #000,
          1px 1px 0 #000;
      }
    }
  }
}

@media (max-width: 768px) {
  .navbar {
    display: none;
  }
}
</style>