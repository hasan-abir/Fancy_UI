<template>
  <div class="contact" id="contact">
    <div class="container">
      <section>
        <div class="wrapper">
          <h1>Keep In Touch</h1>
          <form>
            <label>Name</label>
            <input type="text" />
            <label>Email Address</label>
            <input type="email" />
            <label>Message</label>
            <textarea row="8"></textarea>
            <button>
              Send
              <i class="fas fa-paper-plane"></i>
            </button>
          </form>
          <div class="icons">
            <a href="#">
              <i class="fab fa-instagram"></i>
            </a>
            <a href="#">
              <i class="fab fa-snapchat"></i>
            </a>
            <a href="#">
              <i class="fab fa-twitter"></i>
            </a>
          </div>
        </div>
      </section>
      <aside>
        <Map />
      </aside>
    </div>
  </div>
</template>

<script>
import Map from "./Map"

export default {
  name: "contact",
  components: {
    Map
  }
}
</script>

<style lang="scss">
@import "../assets/scss/mixins.scss";
@import "../assets/scss/variables.scss";
.contact {
  padding: 5.8rem;
  height: 100vh;
  .container {
    background: #fff;
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
      .wrapper {
        width: 100%;
        padding: 0 6rem;
        h1 {
          font-size: 3.2rem;
          color: $blue;
          margin-bottom: 1rem;
        }
        form {
          label {
            font-weight: bold;
          }
          input,
          textarea {
            margin-top: 0.5rem;
            margin-bottom: 1rem;
            width: 100%;
            border: 2px solid #000;
            border-radius: 2px;
            padding: 0.5rem;
          }
          button {
            width: 100%;
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
        .icons {
          margin-top: 2.5rem;
          @include flex(center, center, row);
          a {
            color: $lightest-purple;
            i {
              font-size: 2rem;
              padding: 0 0.5rem;
            }
            &:hover,
            &:active {
              color: $lighter-purple;
            }
          }
        }
      }
    }
  }
  aside {
    background: $lightest-purple;
    overflow: hidden;
  }
}

@media (max-width: 768px) {
  .contact {
    padding: 3.5rem 0;
    .container {
      section {
        .wrapper {
          padding: 1rem;
          h1 {
            font-size: 2rem;
          }
          .icons {
            margin-top: 1rem;
          }
        }
      }
      aside {
        display: none;
      }
    }
  }
}
</style>
