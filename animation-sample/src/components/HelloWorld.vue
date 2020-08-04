<template>
  <div class="hello">
    <button @click="toggleShow">toggle</button>
    <transition>
      <p v-show="isShown">Hello World</p>
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
.v-enter-active {
  transition: opacity 0.5s;
}
.v-leave-active {
  transition: all 1.5s;
}
.v-enter  /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
.v-leave-to {
  opacity: 0;
  transform: translateX(20px);
}
</style>
