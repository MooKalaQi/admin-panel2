<template>
    <Header name="Welcome"></Header>
    <div class="d-flex flex-column align-items-center p-5">
        <h1>Hello User</h1> 
        <span>
            Welcome to our bank system !
           if You want learn more about us 
           use this 
           <router-link to="about"><span>LINK</span></router-link>  
        </span>
    </div>
</template>
<script>
import Header from '../components/Header.vue'
import about from '../components/About.vue'
export default {
    components:{
    Header
    }
}
</script>