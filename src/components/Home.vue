<template>
  <div class="home" id="home">
    <div class="container">
      <section>
        <h1>Keen Eyes</h1>
        <h2>
          Photographers all around the world are sharing their creation to our
          community.
        </h2>
        <p>Explore our gallery of photographs taken by talented people.</p>
        <a href="#gallery">
          Explore
          <i class="fas fa-sort-down"></i>
        </a>
      </section>
      <aside></aside>
    </div>
  </div>
</template>

<script>
export default {
  name: "home"
}
</script>

<style lang="scss">
@import "../assets/scss/mixins.scss";
@import "../assets/scss/variables.scss";

.home {
  height: 100vh;
  padding: 5.8rem;
  .container {
    height: 100%;
    background: #fff;
    box-shadow: 5px 5px 18px rgba(0, 0, 0, 0.5);
    @include flex(center, stretch, row);
    section,
    aside {
      flex: 1;
    }
    section {
      @include flex(center, flex-start, column);
      h1,
      h2,
      p,
      a {
        margin-left: 6rem;
        margin-right: 6rem;
      }
      h1 {
        color: $blue;
        font-size: 3.2rem;
        margin-bottom: 1.5rem;
      }
      h2 {
        font-weight: normal;
        margin-bottom: 1.5rem;
      }
      p {
        margin-bottom: 1.5rem;
        line-height: 1.3;
      }
      a {
        letter-spacing: 0.05rem;
        text-transform: uppercase;
        font-weight: bold;
        padding: 0.8rem 2.5rem;
        background: $blue;
        color: #fff;
        border-radius: 2px;
        box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5);
        transition: background 0.5s;
        &:hover,
        &:active {
          background: darken($lighter-purple, 10%);
        }
        i {
          transform: translateY(-3px);
          margin-left: 0.5rem;
        }
      }
    }
    aside {
      background: #503d9a;
      background: url("/images/homebg.jpeg") no-repeat center/cover;
      position: relative;
      &:after {
        content: "";
        height: 100%;
        width: 100%;
        position: absolute;
        background: #503d9a;
        opacity: 0.4;
      }
    }
  }
}

@media (max-width: 768px) {
  .home {
    padding: 3.5rem 0;
    .container {
      padding: 0 1rem;
      section {
        h1,
        h2,
        p,
        a {
          margin-left: 0;
          margin-right: 0;
        }
        h1 {
          font-size: 3rem;
        }
        h2 {
          font-size: 1.3rem;
        }
      }
      aside {
        display: none;
      }
    }
  }
}
</style>
