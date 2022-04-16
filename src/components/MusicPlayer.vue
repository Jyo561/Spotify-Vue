<template>
	<div class="musicPlayer">
		<div class="songImage">
			<img :src="img" alt="">
		</div>
		<div class="songAttributes">
			<audio :src="son" preload="metadata" ref="audioPlayer" :onloadedmetadata="loadeddata" />
			
			<div class="top">
				<div class="left">
					<div class="loved" @click="changeheart">
						<i v-if="heart==true" >
							<Icon icon="heroicons-solid:heart" />
						</i>
						<i v-else>
							<Icon icon="heroicons-outline:heart" />
						</i>
					</div>
					<div class="download">
						<i>
							<Icon icon="bx:download" />
						</i>
					</div>
				</div>
				<div class="middle">
					<div class="back">
						<i><Icon icon="fa6-solid:backward-step" /></i>
						<i><Icon icon="fa6-solid:backward" /></i>
					</div>
					<div class="playPause" @click="changeplpau">
						<i v-if="playing==true">
							<Icon icon="fa6-solid:pause" />
						</i>
						<i v-else>
							<Icon icon="fa6-solid:play" />
						</i>
					</div>
					<div class="forward">
						<i><Icon icon="fa6-solid:forward" /></i>
						<i><Icon icon="fa6-solid:forward-step"/></i>
					</div>
				</div >
				<div class="right">
					<i><Icon icon="fa-solid:share-alt" /></i>
				</div>
			</div>
			<div class="bottom">
				<div class="currentTime">{{ CalculateTime(currentTime) }}</div>
				<input type="range" class="progressBar" min="0" max="100" ref="progressBar" :onchange="changeProgress">
				<div class="duration" v-if="duration && !isNaN(duration) && CalculateTime(duration)">{{ CalculateTime(duration) }}</div>
				<div class="duration" v-else>00:00</div>
			</div>
		</div> 
	</div>
</template>
<script>
	import '../Styles/MusicPlayer.css'
	import { Icon } from '@iconify/vue';
	export default{
		name:'MusicPlayer',
		props:[
			'son',
			'img'
		],
		components:{
			Icon
		},
		data (){
			return{
				heart: false,
				playing: false,
				audioPlayer: '',
				duration:0,
				currentTime: 0,
				animationRef: '',
			}
		},
		
		methods:{
			changeheart(){
				this.heart=!this.heart;
				console.log(this.$refs.audioPlayer.currentTime);
				
			},
			changeplpau(){
				const value=this.playing;
				if(!value){
					this.$refs.audioPlayer.play();
					this.animationRef = window.requestAnimationFrame(this.wplaying);

				}
				else{
					this.$refs.audioPlayer.pause();
					window.cancelAnimationFrame(this.animationRef);
				}
				this.playing=!this.playing;
			},
			loadeddata(e){
				this.duration=e.target.duration.toFixed(0);
			},
			CalculateTime(sec){
				const minutes = Math.floor(sec/60);

				const returnMin = minutes < 10 ? `0${minutes}` : `${minutes}`;
				const seconds = Math.floor(sec % 60);
				const returnSec = seconds < 10 ? `0${seconds}` : `${seconds}`;
				return `${returnMin}:${returnSec}`;
			},
			changeProgress(){
				this.$refs.audioPlayer.currentTime=this.$refs.progressBar.value;
				this.changeCTime();
			},
			wplaying(){
				this.$refs.progressBar.value = this.$refs.audioPlayer.currentTime;
				this.changeCTime();
				this.animationRef = window.requestAnimationFrame(this.wplaying);
			},
			changeCTime(){
				this.$refs.progressBar.style.setProperty("--player-played",`${(this.$refs.progressBar.value/this.duration)*100}%`);
				this.currentTime=this.$refs.progressBar.value;
			}
		}
	}
</script>
<style>
	
</style>