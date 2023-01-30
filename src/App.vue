<template>
  <tab />
  <headerc />
  <intro />
  <about />
  <project />
  <cloning id="Webclon" />
  <contact />
</template>

<script>
import tab from "./components/tab.vue";
import headerc from "./components/headerC.vue";
import intro from "./components/intro.vue";
import about from "./components/about.vue";
import project from "./components/project.vue";
import cloning from "./components/cloning.vue";
import contact from "./components/contact.vue";

export default {
  name: "App",
  components: {
    tab,
    intro,
    about,
    project,
    cloning,
    contact,
    headerc,
  },
  // data() {
  //   return {
  //     isScrollDown: false, // v-show를 통해 맨위로 버튼을 등장시키는 변수
  //     scrollTop: 0, // 스크롤 값 저장용
  //     target: null, // 이벤트가 등록되는 변수
  //   };
  // },

  // // 1번 가상 돔 마운트 시, 이벤트 등록
  // mounted() {
  //   this.target = document.querySelector("#target");
  //   this.target.addEventListener("scroll", this.handleScroll);
  // },

  // // 3번 마운트 해제 전, 이벤트 삭제하기
  // beforeUnmount() {
  //   this.target.removeEventListener("scroll", this.handleScroll);
  // },
  // methods: {
  //   // 2번 이벤트 액션
  //   handleScroll: function (e) {
  //     this.scrollTop = e.target.scrollTop;
  //     if (this.scrollTop > 400) {
  //       this.isScrollDown = true;
  //     } else {
  //       this.isScrollDown = false;
  //     }
  //   },
  // },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
