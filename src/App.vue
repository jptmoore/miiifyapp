<template>
  <Header />
  <div class="container">
    <div>
      <img id="desk" src="./assets/desk.jpg" />
    </div>
    <link
      rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@recogito/annotorious@2.5.10/dist/annotorious.min.css"
    />
  </div>
  <Footer
    @button-load="loadAnnotations"
    @button-save="saveAnnotations"
    title="annotations"
  />
</template>

<script>
import Header from "./components/Header";
import Footer from "./components/Footer";

import { Annotorious } from "@recogito/annotorious";

const axios = require("axios");

export default {
  name: "App",
  components: {
    Header,
    Footer,
  },
  data() {
    return {
      anno: [],
    };
  },
  methods: {
    async loadAnnotations() {
      console.log("loadAnnotations");
      try {
        const res = await axios.get("/annotations/demo/");
        self.anno.setAnnotations(res.data.first.items);
      } catch (err) {
        // Handle Error Here
        console.error(err);
      }
    },
    async saveAnnotations() {
      console.log("saveAnnotations");
      const annotation = self.anno.getAnnotations()[0];
      console.log(annotation);
      try {
        const res = await axios.put("/annotations/demo/test1", annotation);
        console.log(res);
      } catch (err) {
        // Handle Error Here
        console.error(err);
      }
    },
  },
  mounted() {
    self.anno = new Annotorious({
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
.container {
  /* max-width: 500px; */
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  background: rgb(9, 77, 155);
  color: rgb(22, 128, 199);
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

.btn {
  box-shadow: inset 0px 1px 0px 0px #ffffff;
  background: linear-gradient(to bottom, #ffffff 5%, #f6f6f6 100%);
  background-color: #ffffff;
  border-radius: 6px;
  border: 1px solid #dcdcdc;
  display: inline-block;
  cursor: pointer;
  color: #666666;
  font-family: Arial;
  font-size: 15px;
  font-weight: bold;
  padding: 6px 24px;
  text-decoration: none;
  text-shadow: 0px 1px 0px #ffffff;
}
.btn:hover {
  background: linear-gradient(to bottom, #f6f6f6 5%, #ffffff 100%);
  background-color: #f6f6f6;
}
.btn:active {
  position: relative;
  top: 1px;
}
</style>
