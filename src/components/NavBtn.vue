<template>
  <div>
    <button
      @click="toggleSidebar(!isOpen)"
      class="nav-btn hamburger hamburger--slider"
      :class="{'is-active' : isOpen}"
    >
      <span class="hamburger-box">
        <span class="hamburger-inner"></span>
      </span>
    </button>
    <Sidebar :isOpen="isOpen" :toggleSidebar="toggleSidebar" />
  </div>
</template>

<script>
import "hamburgers/dist/hamburgers.min.css"
import Sidebar from "./Sidebar"

export default {
  name: "navBtn",
  components: {
    Sidebar
  },
  data() {
    return {
      isOpen: false
    }
  },
  methods: {
    toggleSidebar(value) {
      this.isOpen = value
    }
  }
}
</script>

<style lang="scss">
@import "../assets/scss/variables.scss";

.nav-btn {
  display: none;
  position: fixed;
  top: 0;
  right: 0;
}

@media (max-width: 768px) {
  .nav-btn {
    padding: 0.8rem;
    display: block;
    background: rgba($lighter-purple-rgb, 0.8);
    transition: background 0.5s;
    border-radius: 0 0 0 5px;
    z-index: 5;
    .hamburger-inner {
      background: #fff !important;
      &:after,
      &:before {
        background: #fff !important;
      }
    }
  }
}
.hamburger:hover {
  opacity: 1 !important;
}
.is-active {
  background: rgba(255, 255, 255, 0);
  .hamburger-inner {
    background: #fff !important;
    &:after {
      background: #fff !important;
    }
  }
}
</style>