<template>
  <h1>header</h1>
  <nav>
    <ul>
      <li v-on:click="gosection" data-target="Intro" class="gotosec">Intro</li>
      <li v-on:click="gosection" data-target="About" class="gotosec">About</li>
      <li v-on:click="gosection" data-target="Project" class="gotosec">
        Project
      </li>
      <li v-on:click="gosection" data-target="Webclon" class="gotosec">
        Webclon
      </li>
      <li v-on:click="gosection" data-target="Contact" class="gotosec">
        Contack
      </li>
    </ul>
  </nav>
  <div></div>
</template>
<script>
export default {
  methods: {
    gosection(e) {
      if (!e.target.matches(".gotosec")) return;
      e.preventDefault();
      const sec = document.getElementById(e.target.dataset.target);
      if (sec) {
        sec.scrollIntoView({ behavior: "smooth" });
        sec.classList.add("test");
      }
    },
  },
};
</script>