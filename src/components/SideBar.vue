<template>
  <div class="d-flex flex-column" :class="[darkmode ? 'darkmode' : '']">
   <div class="p-5">
      <router-link to="/home">
         <h1><i class="fa-solid fa-crown fs-1"></i>DevBank</h1>

      </router-link>
   </div>
    <div class="items_container ps-5" v-for="item in data" :key="item.id" >
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
      
      darkmode:sourceData.darkMode
    };
  },
  methods:{
   // theme(){
   //    this.darkmode = localStorage.getItem("theme")
      
   //    return this.darkmode;
   // }

  }
};
</script>
<style scoped>
a , a>*{
text-decoration: none;
background: inherit;
color: inherit;
}
h1>i{
   color:red;
}

.darkmode,.darkmode > *{
   background-color: #1f1f1f;
   color: #e8e8e8;

}
.darkmode > div > a{
   background-color: #1f1f1f;
   color: #e8e8e8;
}
.darkmode > div > a > h1>i{
   background-color: inherit;
   color: gold;
}
/* .darkmode > .items_container > a ,.darkmode > .items_container > a > h3  {
   background: #1f1f1f;
   color: #e8e8e8;
} */
.items_container{
   margin: 1rem 0 ;
}

</style>