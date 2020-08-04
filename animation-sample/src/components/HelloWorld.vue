<template>
  <div class="hello">
    <button @click="addNumber">toggle</button>
    <transition-group>
      <span v-for="number in numbers" :key="number">
        {{ number }}
      </span>
    </transition-group>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      isShown: false,
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9],
      nextNum: 10
    };
  },
  methods: {
    addNumber() {
      this.numbers.splice(0, 0, this.nextNum);
      this.nextNum++;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s;
}
.v-enter, .v-leave-to  /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
