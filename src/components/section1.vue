<template>
  <div class="section1">
    <div class="sec_wrap">
      <div class="p50all b_beige left">
        <div class="top">
          <h1>SEWON<span class="blue">'S</span></h1>
          <h1>PORTFOLIO</h1>
        </div>
        <div class="bottom">
          <p>김세원_SEWON KIM</p>
          <p>TEL : 010 5754 8799</p>
          <p>E-MAIL : sewon0076@naver.com</p>
        </div>
      </div>
      <div class="p50all b_black">
        <div class="circle_wrap">
          <div v-on:click="gosection" data-target="intro" class="circle">
            <div class="b_beige">
              <h3>INTRODUCTION</h3>
            </div>
          </div>
          <div class="circle">
            <div class="b_yellow">
              <h3 @click="gosection" data-target="projects">PROJECTS</h3>
            </div>
          </div>
          <div @click="gosection" data-target="experiences" class="circle">
            <div class="b_red"><h3>EXPEREIENCES</h3></div>
          </div>
          <div @click="gosection" data-target="contact" class="circle">
            <div class="b_green"><h3>CONTACT</h3></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  methods: {
    gosection(e) {
      console.log(e.target.dataset.target);
      if (!e.target.matches(".circle")) return;
      e.preventDefault();
      const section = document.getElementById(e.target.dataset.target);
      if (section) {
        section.scrollIntoView({ behavior: "smooth" });
      }
    },
    // goIntro() {
    //     const intro = document.querySelector("#intro");
    //     if (intro) {
    //         intro.scrollIntoView({
    //             behavior: "smooth",
    //         });
    //     }
    // },
    goProjects() {
      const projects = document.querySelector("#projects");
      if (projects) {
        projects.scrollIntoView({
          behavior: "smooth",
        });
      }
    },
    goExperiences() {
      const experiences = document.querySelector("#experiences");
      if (experiences) {
        experiences.scrollIntoView({
          behavior: "smooth",
        });
      }
    },
    goContact() {
      const contact = document.querySelector("#contact");
      if (contact) {
        contact.scrollIntoView({
          behavior: "smooth",
        });
      }
    },
  },
};
</script>
<style scoped>
.circle_wrap {
  padding: 50px 0;
  box-sizing: border-box;
  display: flex;
  flex-wrap: wrap;
  gap: 25px;
}
.circle {
  width: calc(50% - 12.5px);
  height: auto;
}
.circle > div {
  position: relative;
  width: 100%;
  padding-top: 100%;
  box-sizing: border-box;
  border-radius: 50%;
}
.circle h3 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate3d(-50%, -50%, 0);
}
.left {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
</style>
