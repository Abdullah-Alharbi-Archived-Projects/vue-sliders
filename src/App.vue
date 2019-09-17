<template>
  <div id="app">
    <slider seconds="4" :sliders="sliders" />
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
        "https://cdn.pixabay.com/photo/2015/05/15/14/27/eiffel-tower-768501_1280.jpg",
        MyHeader
      ]
    };
  }
};
</script>

<style>
html,
body {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
