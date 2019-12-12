<template>
  <div class="photographer">
    <div class="avatar">
      <img :src="'/images' + this.photographer.avatar" alt />
    </div>
    <div class="text">
      <h1>{{this.photographer.name}}</h1>
      <p>{{this.photographer.description}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "photographer",
  props: ["photographer"]
}
</script>

<style lang="scss">
@import "../assets/scss/variables.scss";
@import "../assets/scss/mixins.scss";

.photographer {
  background: #fff;
  box-shadow: 5px 5px 18px rgba(0, 0, 0, 0.5);
  padding: 3.75rem;

  .avatar {
    width: 200px;
    height: 200px;
    overflow: hidden;
    @include flex(center, center, column);
    border-radius: 50%;
  }
  .text {
    flex: 2;
    h1 {
      color: $blue;
    }
    p {
      margin-bottom: 0;
    }
  }
}
</style>