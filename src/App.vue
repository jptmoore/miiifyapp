<template>
  <div>
    <img id="desk" src="./assets/desk.jpg" />
  </div>
  <link
    rel="stylesheet"
    href="https://cdn.jsdelivr.net/npm/@recogito/annotorious@2.5.10/dist/annotorious.min.css"
  />
  <Footer />
</template>


<script>
import Footer from './components/Footer'

import { Annotorious } from "@recogito/annotorious";

export default {
  name: "App",
  components: {
    Footer,
  },
  data() {
    return {
      anno: {},
    };
  },
  mounted() {
    this.anno = new Annotorious({
      image: document.getElementById("desk"),
    });
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
