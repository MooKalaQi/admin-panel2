<template>
  <div class="d-flex flex-row h-100">
    <div class="col-2">
      <SideBar></SideBar>
    </div>
    <div class="col-10">
     <router-view></router-view>
    </div>
  </div>
</template>
<script>
import SideBar from './components/SideBar.vue';
import data from './data.json';
export default {
  data() {
    return {
      data,
    };
  },
  components: {
    SideBar,
  },
};
</script>

<style scoped>
.col-2 {
  border-right: 5px solid #777777;
}
</style>
