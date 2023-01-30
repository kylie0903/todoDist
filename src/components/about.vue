<template>
  <h1 id="About">About page</h1>
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
</template>
<script>
import { useMotion } from "@vueuse/motion";
export default {
  //   setup(){
  // const target = ref<HTMLElement>()
  // const motionInstance = useMotion(target, {
  //     initial: {
  //         opacity: 0,
  //         y: 100
  //     },
  //     enter: {
  //         opacity: 1,
  //         y: 0
  //     }
  // })
  //   }
};
</script>
<style scoped>
div {
  width: 100%;
  height: 800px;
  background-color: aquamarine;
}
</style>