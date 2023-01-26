<template>
  <div>
    <h1>This id a project page</h1>
    <ul>
      <li v-for="ramen in ramens" :key="ramen">
        {{ ramen.name }}의 값은 {{ ramen.price }} 입니다.
      </li>
    </ul>
    <table>
      <tr>
        <th v-for="head in f_head" :key="head">{{ head }}</th>
      </tr>
      <tr v-for="f_list in fruits" :key="f_list">
        <td
          v-for="fruit in f_list"
          :key="fruit"
          v-bind:colspan="fruit.colspan || 1"
        >
          {{ fruit.data }}
        </td>
      </tr>
    </table>
  </div>
</template>
<script>
export default {
  data() {
    return {
      ramens: [
        { name: "신라면", price: "1200원" },
        { name: "진라면", price: "1000원" },
        { name: "참깨라면", price: "1480원" },
        { name: "너구리", price: "1200원" },
      ],
      f_head: ["fruit", "fruit", "fruit"],
      fruits: [
        [{ data: "apple" }, { data: "banana" }, { data: "strawberry" }],
        [{ data: "tomato" }, { data: "pear" }, { data: "melon" }],
        [{ data: "grape", colspan: 2 }, { data: "orange" }],
      ],
    };
  },
};
</script>
<style scoped>
table,
td,
th {
  border-collapse: collapse;
  border: 1px solid red;
  padding: 20px;
}
</style>
