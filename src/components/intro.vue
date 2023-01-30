<template>
  <h1 id="Intro">intro page</h1>
  <div
    v-motion
    :initial="{
      opacity: 0,
      y: 100,
    }"
    :enter="{
      opacity: 1,
      y: 0,
    }"
  >
    test box
  </div>
  <div>
    <button @click="arco = !arco">click</button>
    <transition name="fade">
      <h2 v-if="arco">show contents</h2>
    </transition>
  </div>
</template>
<script>
export default {
  data() {
    return {
      arco: false,
    };
  },
};
</script>
<style scoped>
div {
  width: 100%;
  height: 800px;
  background-color: burlywood;
}
h2 {
  widows: 300px;
  height: 50px;
  background-color: red;
}
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: opacity 1s ease-in-out;
}
.fade-enter-to {
  opacity: 1;
}

.fade-leave-active {
  transition: opacity 1s ease-in-out;
}
.fade-leave-to {
  opacity: 0;
}
</style>