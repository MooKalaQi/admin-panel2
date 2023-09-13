<template>
  <div class="d-flex flex-row justify-content-between align-items-center p-5"
  :class="[darkmode? 'darkmode' :'']">
    <div>
      <h1>{{ name }}</h1>
    </div>
    <div>
      <div class="search_bar">
        <form>
          <label for="search"
            ><i class="fa-solid fa-magnifying-glass"></i
          ></label>
          <input type="text" />
        </form>
      </div>
    </div>
  </div>
</template>
<script>
import sourceData from '../data.json'
export default {
    props:{
        name: String
    },
    data(){
        return{
            darkmode : sourceData.darkMode
        }
    }
}
</script>
<style scoped>
.p-5{
    border-bottom: 5px solid #777;
}
.search_bar{
    height: 3rem;
}
form{
    height: 100%;
    background-color:rgb(238, 238, 238) ;
}
label{
    background-color: inherit;
}
i{
    background-color: inherit;
}
input{
    border: none;
    background-color: rgb(238, 238, 238);
    height: 100%;
} 
.darkmode > *,.darkmode{
    background-color: #1f1f1f;
}
.darkmode > * > h1{
    background-color: inherit;
    color: white;
}
.darkmode>div>.search_bar>form{
    background-color: rgb(156, 156, 156);
}
.darkmode>div>.search_bar>form>*{
    background-color: inherit;
    color: white;
}

</style>
