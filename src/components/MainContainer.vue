<template>
  <div class="mainContainer">
    <Banner />
    <div class="menuList2">
      <ul>
        <li v-for="men in menu" :key="men" @click="changeval(men.id)" :class="{active:men.ac}">
                 <a href="#">{{ men.value }}</a>
        </li>
      </ul>
      <p><i><Icon icon="gridicons:multiple-users" /></i>
        12.3M <span>Followers</span>
      </p>
    </div>
    <AudioList />
  </div>
</template>

<script>
import { Icon } from '@iconify/vue';
import '../Styles/MainContainer.css';
import AudioList from "./AudioList.vue";
import Banner from "./Banner.vue";
export default {
  name: 'MainContainer',
  components:{
    Banner,
    AudioList,
    Icon
  },
  data (){
    return{
      menu:[
        {
          id: 1,
          ac:false,
          value:"Popular",
        },
        {
          id: 2,
          ac:false,
          value: "Albums",
        },
        {
          id: 3,
          ac:false,
          value: "Songs",
        },
        {
          id: 4,
          ac:false,
          value:"Fans",
        },
        {
          id: 5,
          ac:false,
          value:"About",
        }
      ]
    }
  },
  methods:{
    changeval(e){
      var n=this.menu.length;
      for(var i=0;i<n;i++){
        if(this.menu[i].id===e){
          this.menu[i].ac=true;
        }
        else{
          this.menu[i].ac=false;
        }
        
      }
    }
  }
}
</script>

<style scoped>

</style>
