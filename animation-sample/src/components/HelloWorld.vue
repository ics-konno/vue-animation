<template>
  <div class="hello">
    <button @click="toggleShow">toggle</button>
    <transition name="one">
      <p v-show="isShown">アニメーション１</p>
    </transition>
    <transition name="two">
      <p v-show="isShown">アニメーション２</p>
    </transition>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      isShown: false
    };
  },
  methods: {
    toggleShow() {
      this.isShown = !this.isShown;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.one-enter-active {
  transition: opacity 0.5s;
}
.one-leave-active {
  transition: all 1.5s;
}
.one-enter  /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
.one-leave-to {
  opacity: 0;
  transform: translateX(20px);
}

.two-enter-active {
  transition: opacity 1.5s;
}
.two-leave-active {
  transition: all 2.5s;
}
.two-enter  /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
.two-leave-to {
  opacity: 0;
  transform: translateX(20px);
}
</style>
