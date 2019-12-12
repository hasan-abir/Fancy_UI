<template>
  <div class="img-modal" :class="{'img-modal-active': isOpen}">
    <div>
      <img :src="'/images/' + this.picture.url" alt />
    </div>
    <button class="closer" @click="toggleModal(false)"></button>
  </div>
</template> 

<script>
export default {
  name: "imgModal",
  props: ["isOpen", "picture", "toggleModal"]
}
</script>

<style lang="scss">
@import "../assets/scss/mixins.scss";
@import "../assets/scss/variables.scss";

.img-modal {
  height: 100vh;
  background: rgba(0, 0, 0, 0.5);
  color: #fff;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 10;
  opacity: 0;
  transition: opacity 0.5s;
  pointer-events: none;
  @include flex(center, center, column);
  div {
    max-height: 100%;
    max-width: 80%;
    opacity: 0;
    transform: scale(0.8);
    transition: opacity 0.5s 0.2s, transform 0.2s 0.2s;
    overflow: hidden;
    @include flex(center, center, column);
    z-index: 2;
    img {
      width: auto;
      height: 100%;
      object-fit: cover;
    }
  }
  .closer {
    height: 100vh;
    width: 100%;
    position: fixed;
    background: transparent;
    cursor: default;
  }
}
.img-modal-active {
  opacity: 1;
  pointer-events: all;
  div {
    opacity: 1;
    transform: scale(1);
  }
}

@media (max-width: 768px) {
  .img-modal {
    div {
      img {
        width: 100%;
        height: auto;
      }
    }
  }
}
</style>