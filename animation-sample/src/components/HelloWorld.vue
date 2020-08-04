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
.v-enter-active, .v-leave-active {
  transition: opacity .5s;
}
.v-enter, .v-leave-to /* .fade-leave-active below version 2.1.8 */ {
  transition: opacity .5s;
  opacity: 0;
}
</style>
