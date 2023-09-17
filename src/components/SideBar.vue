<template>
  <div class="d-flex flex-column" :class="[darkmode ? 'darkmode' : '']">
    <div class="p-5">
      <router-link to="/home">
        <h1><i class="fa-solid fa-crown fs-1"></i>DevBank</h1>
      </router-link>
    </div>
    <div class="items_container ps-5" v-for="item in data" :key="item.id">
      <router-link :to="item.slug">
        <h3>{{ item.name }}</h3>
      </router-link>
    </div>
  </div>
</template>
<script>
import sourceData from '../data.json';
export default {
  data() {
    return {
      data: sourceData.sidemenu,

      darkmode: sourceData.darkMode,
    };
  },
  methods: {
    // theme(){
    //    this.darkmode = localStorage.getItem("theme")
    //    return this.darkmode;
    // }
  },
};
</script>
<style lang="scss" scoped>
a, a > * {
  text-decoration: none;
  background: inherit;
  color: inherit;
}
h1 > i {
  color: red;
}
h3{
   &:hover{
      transform: scale(0.8);
      transition: 0.2s;
   }
}

.darkmode {
  background-color: #1f1f1f;
  i{
   background-color: inherit;
   color: gold;
  }

}

.items_container {
  margin: 1rem 0;
}
</style>
