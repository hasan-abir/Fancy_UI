<template>
  <div class="gallery" id="gallery">
    <div class="container">
      <section>
        <Picture v-for="(picture, index) in sectionOne" :key="index" :picture="picture" />
      </section>
      <section>
        <Picture v-for="(picture, index) in sectionTwo" :key="index" :picture="picture" />
      </section>
      <section>
        <Picture v-for="(picture, index) in sectionThree" :key="index" :picture="picture" />
      </section>
    </div>
  </div>
</template>

<script>
import galleryData from "../assets/galleryData"
import Picture from "./Picture"

export default {
  name: "gallery",
  components: {
    Picture
  },
  data() {
    return {
      sectionOne: [],
      sectionTwo: [],
      sectionThree: []
    }
  },
  created() {
    const sectionTwo = galleryData

    const sectionOne = sectionTwo.splice(0, sectionTwo.length / 3)
    const sectionThree = sectionTwo.splice(
      sectionTwo.length / 3 + 1,
      sectionTwo.length
    )

    this.sectionOne = sectionOne
    this.sectionTwo = sectionTwo
    this.sectionThree = sectionThree
  }
}
</script>

<style lang="scss">
.gallery {
  padding: 5.8rem;
  @import "../assets/scss/mixins.scss";
  @import "../assets/scss/variables.scss";
  .container {
    background: #fff;
    box-shadow: 5px 5px 18px rgba(0, 0, 0, 0.5);
    padding: 8rem 5.8rem 5.8rem 5.8rem;
    @include flex(center, flex-start, row);
    section {
      flex: 1;
      .picture {
        margin-bottom: 1rem;
        cursor: pointer;
        position: relative;
        &:hover:after,
        &:active:after {
          background: rgba($lighter-purple, 0.5);
        }
        &:after {
          content: "";
          position: absolute;
          top: 0;
          left: 0;
          width: 100%;
          height: 100%;
          background: transparent;
          transition: background 0.5s;
        }
      }
    }
    section:first-child,
    section:nth-child(2) {
      margin-right: 1rem;
    }
  }
}
@media (max-width: 768px) {
  .gallery {
    padding: 3.5rem 0;
    .container {
      display: block;
      padding: 3rem 1rem;
      section:first-child,
      section:nth-child(2) {
        margin-right: 0;
      }
    }
  }
}
</style>