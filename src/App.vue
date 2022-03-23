<template>
 <div class="App">
   <LeftMenu />
   <MainContainer />
   <RightMenu />

   <div class="background">
     
   </div>
 </div>
</template>

<script>
import './App.css'
import LeftMenu from "./components/LeftMenu.vue";
import MainContainer from "./components/MainContainer.vue";
import RightMenu from "./components/RightMenu.vue";

export default {
  name: 'App',
  components: {
    LeftMenu,
    MainContainer,
    RightMenu
  }
}
</script>

<style>
.app {
  
  color: #333;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen-Sans, Ubuntu, Cantarell, "Helvetica Neue", sans-serif;
  
}
</style>
