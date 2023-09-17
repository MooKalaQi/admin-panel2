<template>
  <Header name="Setting"></Header>
  <div class="container">
    <p>Dark mode :</p>
    <button @click="ChangeTheme()">Dark Mode</button>
  </div>
</template>
<script>
import { watch } from 'vue';
import Header from '../components/Header.vue';
import sourceData from '../data.json';
export default {
  data() {
    return {
      darkmode:localStorage.getItem("theme")
    };
  },
  components: {
    Header,
  },
  methods: {
    ChangeTheme() {
      this.darkmode = !this.darkmode;
      console.log(this.darkmode);
      localStorage.setItem("theme" , JSON.stringify(this.darkmode))
      return this.darkmode;

    },
  },


};
</script>
<style scoped>
  button{
    padding:1rem;
    border: none;
    background-color: #ff8400;
    box-shadow: -2px 2px 10px 2px #0000004d;
  }
</style>
