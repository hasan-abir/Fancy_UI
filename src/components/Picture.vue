<template>
  <div>
    <div @click="toggleModal(true)" class="picture">
      <img :src="'/images' + this.picture.url" alt />
    </div>
    <ImgModal :isOpen="isOpen" :picture="this.picture" :toggleModal="toggleModal" />
  </div>
</template>

<script>
import ImgModal from "./ImgModal"

export default {
  name: "picture",
  data() {
    return {
      isOpen: false
    }
  },
  methods: {
    toggleModal(value) {
      this.isOpen = value
    }
  },
  components: {
    ImgModal
  },
  props: ["picture"]
} 
</script>

<style>
</style>