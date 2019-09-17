<template>
  <div class="slider full">
    <transition-group name="fade" class="full" tag="div">
      <div v-for="i in [currentIndex]" :key="i" class="full">
        <img v-if="typeof currentSlide == 'string'" :src="currentSlide" />
        <section v-if="typeof currentSlide == 'object'" class="full">
          <component :is="currentSlide"></component>
        </section>
      </div>
    </transition-group>
    <a class="prev" @click="prev" href="#">&#10094; Previous</a>
    <a class="next" @click="next" href="#">&#10095; Next</a>
  </div>
</template>

<script>
export default {
  name: "slider",
  data() {
    return {
      currentIndex: 0,
      timer: null
    };
  },
  props: {
    seconds: String,
    images: {
      type: Array
    },
    components: {
      type: Array
    },
    sliders: {
      type: Array
    }
  },
  methods: {
    startSlide() {
      const time = parseInt(this.seconds) * 1000;
      this.timer = setInterval(this.next, time);
    },
    next() {
      this.currentIndex += 1;
    },
    prev() {
      this.currentIndex -= 1;
    }
  },
  computed: {
    currentSlide() {
      return this.sliders[Math.abs(this.currentIndex) % this.sliders.length];
    }
  },
  mounted() {
    this.startSlide();
  }
};
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: all 0.9s ease;
  overflow: hidden;
  visibility: visible;
  position: absolute;
  width: 100%;
  opacity: 1;
}

.fade-enter,
.fade-leave-to {
  visibility: hidden;
  width: 100%;
  opacity: 0;
}

img {
  height: 100%;
  width: 100%;
}

.prev,
.next {
  cursor: pointer;
  position: absolute;
  top: 40%;
  width: auto;
  padding: 16px;
  color: rgba(0, 0, 0, 0.9);
  font-weight: bold;
  font-size: 18px;
  transition: 0.7s ease;
  border-radius: 0 4px 4px 0;
  text-decoration: none;
  user-select: none;
}

.next {
  right: 0;
}

.prev {
  left: 0;
}

.prev:hover,
.next:hover {
  background-color: rgba(0, 0, 0, 0.9);
}

.full {
  height: 100vh;
  width: 100%;
}
</style>