<template>
	<div class="playListContainer">
		<div class="nameContainer">
			<p>Playlist</p>
			<i>
				<Icon icon="akar-icons:plus" />
			</i>
		</div>
		<div class="playListScroll">
			<div class="playList" v-for="playl in Playlist" :key="playl">
				<i class="list"><Icon icon="bi:music-note-list" /></i>
			<p> {{ playl.name }} </p>
			<i class="trash"><Icon icon="bi:trash-fill" /></i>
			</div>
		</div>
	</div>			
</template>
<script>
	import { Icon } from '@iconify/vue';
	export default{
		name: 'MenuPlay',
		components:{
			Icon
		},
		data(){
			return{
				Playlist:[
					{
						id:1,
						name: "Top Hit 2021-USA",
					},
					{
						id:2,
						name: "Dance",
					},
					{
						id:3,
						name: "Relaxing Music",
					},
					{
						id:4,
						name: "Instrumental",
					},
					{
						id:5,
						name: "Hip Pop",
					},
					{
						id:6,
						name: "Workout Music",
					},
					{
						id:7,
						name: "Top",
					}

				]
			}
		}
	}
</script>
<style>
	
</style>