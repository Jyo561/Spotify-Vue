<template>
<div class="menuContainer">
	<p class="title">
		<span class="pol">Menu</span>
		<ul>
			<li v-for="menu in MenuList" :key="menu" @click="changeMenu(menu.id)" :class="{active:menu.ac}">
				<a href="#" >
					<i><component v-bind:is="menu.icon"></component></i>  
					<span> {{ menu.name }} </span>
				</a>
			</li>
		</ul>
	</p>
</div>	
</template>
<script>
import { Icon } from '@iconify/vue';
	export default{
		name:'MeNu',
		data (){
			return{
				MenuList : [
					{
						id: 1,
						ac:false,
						icon: <Icon icon="bxs:home-alt-2" />,
						name: "Home",
					},
					{
						id: 2,
						ac:false,
						icon: <Icon icon="bx:pulse" />,
						name: "Discover",
					},
					{
						id: 3,
						ac:false,
						icon: <Icon icon="fa-solid:broadcast-tower" class="bt" />,
						name: "Radio",
					},
					{
						id: 4,
						ac:false,
						icon: <Icon icon="fa:microphone" class="ar" />,
						name: "Artist",
					},
					{
						id: 5,
						ac:false,
						icon: <Icon icon="ion:journal-sharp" />,
						name: "Albums",	
					},
					{
						id: 6,
						ac:false,
						icon: <Icon icon="fa:podcast" class="to" />,
						name: "Podcasts",
					},
				]
			}
		},
		methods : {
			changeMenu(e){
				var n=this.MenuList.length;
				for(var i=0;i<n;i++){
					if(this.MenuList[i].id==e){
						this.MenuList[i].ac=true;
					}
					else{
						this.MenuList[i].ac=false;
					}
				}

			}
		}
	}
</script>

<style>

</style>