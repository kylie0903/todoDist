<template>
  <div id="tab">
    <ul>
      <li
        v-for="(tab, index) in tabs"
        :key="index"
        :class="{ active: current === index }"
        @click="currents(index)"
      >
        <h2>{{ tab.name }}</h2>
        <div>{{ index }}</div>
      </li>
    </ul>
    <input v-model="current" />
    <div>
      <div v-for="(tab, index) in tabs" :key="index" v-show="current == index">
        {{ tab.desc }}
      </div>
    </div>
  </div>
</template>
<script>
import { ref } from "vue";
export default {
  setup() {
    let current = ref(0);
    const tabs = [
      { name: "tab1", desc: "tab1 desc" },
      { name: "tab2", desc: "tab2 desc" },
      { name: "tab3", desc: "tab3 desc" },
    ];
    function currents(index) {
      current.value = index;
      console.log(current);
    }
    return {
      tabs,
      current,
      currents,
    };
  },
};
</script>