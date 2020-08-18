<template>
  <div class="hello">
    <button @click="addNumber">toggle</button>
    <transition-group tag="ul">
      <li v-for="number in numbers" :key="number">
        {{ number }}
      </li>
    </transition-group>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      numbers: [9, 8, 7, 6, 5, 4, 3, 2, 1],
    };
  },
  methods: {
    addNumber() {
      this.numbers.splice(0, 0, this.numbers[0] + 1);
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
.v-enter, .v-leave-to {
  opacity: 0;
}

li {
  list-style: none;
  padding: 10px 0;
  border-bottom: 1px solid #ccc;
}

.v-move {
  transition: transform 0.5s;
}
</style>
