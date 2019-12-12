<template>
  <div class="photographers" id="photographers">
    <Photographer
      v-for="(photographer, index) in photographers"
      :key="index"
      :photographer="photographer"
    />
  </div>
</template>

<script>
import Photographer from "./Photographer"
import photographersData from "../assets/photographersData"
export default {
  name: "photographers",
  data() {
    return {
      photographers: photographersData
    }
  },
  components: {
    Photographer
  }
}
</script>

<style lang="scss">
@import "../assets/scss/mixins.scss";

.photographers {
  padding: 12rem 5.8rem 5.8rem 5.8rem;
  .photographer {
    @include flex(stretch, center, row);
  }
  .photographer:nth-child(2) {
    .avatar {
      order: 2;
    }
  }
  .photographer:first-child,
  .photographer:nth-child(2) {
    margin-bottom: 2rem;
  }
  .photographer:first-child,
  .photographer:last-child {
    text-align: right;
    .avatar {
      margin-right: 2rem;
    }
  }
  .photographer:nth-child(2) {
    .avatar {
      margin-left: 2rem;
    }
  }
}

@media (max-width: 768px) {
  .photographers {
    padding: 3.5rem 0;
    .photographer {
      padding: 2rem;
      .avatar {
        display: none;
      }
    }
  }
}
</style>