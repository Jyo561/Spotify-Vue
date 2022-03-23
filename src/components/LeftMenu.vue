<template>
  <div class="leftMenu">
    <div class="logoContainer">
      <i><Icon icon="mdi:spotify" /></i>
       <h2>Spotify</h2>
       <i><Icon icon="mdi:dots-horizontal" class="rtw"/></i>
    </div>
    <div class="searchBox">
       <input type="text" placeholder="Search...">
       <i class="searchIcon">
        <Icon icon="bi:search" />
       </i>      
      </div>

      <Menu />
      <MenuPlay />
      <Tracklist />
  </div>
</template>

<script>
import '../Styles/LeftMenu.css';
import { Icon } from '@iconify/vue';
import Menu from './Menu.vue';
import MenuPlay from './MenuPlayList.vue';
import Tracklist from './TrackList.vue';
export default {
  name: 'LeftMenu',
  components:{
      Icon,
      Menu,
      MenuPlay,
      Tracklist
  }
}
</script>

<style scoped>

</style>
