<template>
  <div>
    <Navbar />
    <NavBtn />
    <Home />
    <Gallery />
    <Photographers />
    <Contact />
  </div>
</template>

<script>
import Navbar from "./components/Navbar"
import NavBtn from "./components/NavBtn"
import Home from "./components/Home"
import Gallery from "./components/Gallery"
import Photographers from "./components/Photographers"
import Contact from "./components/Contact"

export default {
  name: "app",
  components: {
    Home,
    Gallery,
    Photographers,
    Contact,
    Navbar,
    NavBtn
  }
}
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Montserrat:400,700&display=swap");
@import "./assets/scss/variables.scss";

* {
  box-sizing: border-box;
  font-family: "Montserrat", sans-serif;
}
html {
  scroll-behavior: smooth;
}
body {
  margin: 0;
  overflow-x: hidden;
  background-attachment: fixed;
  background: linear-gradient(to top right, #252857, #56365b);
  background-repeat: no-repeat;
}

body.img-modal {
  overflow: hidden;
}
h1,
h2,
h3,
h4,
h5,
h6,
p {
  margin-top: 0;
}
a {
  text-decoration: none;
  cursor: pointer;
}
button {
  cursor: pointer;
  font-size: 1rem;
  display: block;
  border: 0;
  &:focus {
    outline: none;
  }
}
input,
textarea,
select {
  font-size: 1rem;
  display: block;
  &:focus {
    outline: none;
  }
}
textarea {
  resize: none;
}
img {
  width: 100%;
  display: block;
}

.leaflet-control {
  display: none;
}
</style>
