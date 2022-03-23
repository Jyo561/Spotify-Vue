<template>
	<div class="trackList">
		<div class="top">
			<img src="../img/track.png" alt="">
			<p class="trackName">
				Sample Name <span class="trackSpan">Artist</span>
			</p>
		</div>
		<div class="bottom">
			<i>
				<Icon icon="bi:volume-up-fill" />
			</i>
			<input type="range">
			<i>
				<Icon icon="bi:music-note-list" />
			</i>
			<i>
				<Icon icon="fa-solid:desktop" />
			</i>
		</div>
	</div>
</template>
<script>
	import { Icon } from '@iconify/vue';
	
	export default{
		name: 'TrackList',
		components:{
			Icon,

		}
		
	}
</script>
<style>
	
</style>