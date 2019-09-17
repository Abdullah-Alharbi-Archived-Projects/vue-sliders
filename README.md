# vue-sliders

**simple slider component**

## how to use ?

```
<template>
  <div id="app">
    <!-- in x seconds change the slide -->
    <slider seconds="4" :sliders="sliders" />
  </div>
</template>


<script>
import Slider from "./components/Slider.vue";

export default {
  name: "app",
  components: {
    Slider
  },
  data() {
    return {
      sliders: [
        "https://cdn.pixabay.com/photo/2015/05/15/14/27/eiffel-tower-768501_1280.jpg", // image url
        MyHeader // custom component
      ]
    };
  }
};
</script>
```
