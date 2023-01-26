<template>
  <div class="about">
    <h1>This is form tags</h1>
  </div>
  <div>
    <label for="text"> text : </label>
    <input type="text" name="text" id="text" v-model="text" />
  </div>
  <div v-for="chk in checked" v-bind:key="chk">
    <label> {{ chk }} : </label>
    <input type="checkbox" v-model="reacti.chk" v-bind:value="chk" />
  </div>
  <!-- <input type="checkbox" value="chk1" v-model="checked" />
    <input type="checkbox" value="chk2" v-model="checked" />
    <input type="checkbox" value="chk3" v-model="checked" /> -->
  <div>
    <label> radio O: </label>
    <input type="radio" v-model="reacti.OX" value="O" />
    <label> radio X: </label>
    <input type="radio" v-model="reacti.OX" value="X" />
  </div>
  <div>
    <label> textarea : </label>
    <textarea v-model="textA"></textarea>
  </div>
  <div>
    <select v-model="reacti.select">
      <option v-for="select in selects" :key="select">{{ select }}</option>
    </select>
  </div>
  <h2>{{ reacti }}</h2>
</template>
<script>
import { reactive } from "vue";
export default {
  // data() {
  //   return {
  //     text: "text",
  //     checked: ["chk1", "chk2", "chk3"],
  //   };
  // },
  setup() {
    const textA = "메모를 입력해주세요";
    const text = "text";
    const chk = ["chk1"]; //checkbox 에 checked된 애들만 담는 공간
    const checked = ["chk1", "chk2", "chk3"];
    const OX = "O";
    const select = "select1";
    const selects = ["select1", "select2", "select3"];
    const reacti = reactive({
      select,
      chk,
      OX,
    });

    return { selects, text, checked, chk, reacti, OX, textA };
  },
};
</script>
<style scoped>
</style>
