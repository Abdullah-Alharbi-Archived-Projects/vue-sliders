<template>
  <div id="app">
    <slider seconds="8" :sliders="sliders" />
  </div>
</template>

<script>
import Slider from "./components/Slider.vue";
import MyHeader from "./components/MyHeader.vue";

export default {
  name: "app",
  components: {
    Slider
  },
  data() {
    return {
      sliders: [
        MyHeader,
        "https://cdn.pixabay.com/photo/2015/05/15/14/27/eiffel-tower-768501_1280.jpg"
      ]
    };
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
html,
body {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
