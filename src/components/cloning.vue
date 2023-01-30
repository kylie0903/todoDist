<template>
  <div>
    <h1>web clone</h1>
    <div id="test">
      <div>
        <a :href="dosirac">test</a>
      </div>
    </div>
  </div>
</template>
<script>
import { onMounted } from "@vue/runtime-core";
export default {
  data() {
    return {
      dosirac: "./src/assets/dosirac/index.html",
    };
  },
  setup() {
    onMounted(() => {
      const test = document.querySelector("#test");
      console.log(test);
      const dd = window.location.href;
      console.log(dd);
    });
    // const test = document.querySelector("#test");
    // console.log(test);

    // return { test };
  },
};
</script>
<style scoped>
div {
  width: 100%;
  height: 800px;
  background-color: rebeccapurple;
}
</style>