<template>
  <div class="rightMenu">
    <div class="goPro">
      <i><Icon icon="jam:crown-f" />
        <p>Go <span>Pro</span></p>
      </i>
      <i><Icon icon="jam:bell-f" /></i>
      <i><Icon icon="jam:heart" /></i>
    </div>
    <div class="profile">
      <i><Icon icon="jam:sun-f" /></i>
      <i><Icon icon="jam:cogs-f" /></i>
      <div class="profileImage">
        <img src="../img/profile.jpg" alt="">
      </div>
    </div>
  </div>
</template>

<script>
  import '../Styles/RightMenu.css';
  import { Icon } from '@iconify/vue';
export default {
  name: 'RightMenu',
  components:{
    Icon
  }
}
</script>

<style scoped>

</style>
