<template>
	<div class="banner">
		<img src="../img/artist.jpg" class="bannerImg" alt="" />
		<div class="content">
			<div class="breadCrump">
				<p>
					Home <span>/Popular Artist</span>
				</p>
				<i>
					<Icon  icon="fe:elipsis-h" />
				</i>
			</div>
			<div class="artist">
				<div class="left">
					<div class="name">
						<h2>A-Ha</h2>
						<img src="../img/check.png" alt="">
					</div>
					<p>
						<i>
							<Icon icon="charm:headphones" />
						</i>
						11,184,1811 <span>Monthly listeners</span>
					</p>
				</div>
				<div class="right">
					<a href="#">Play</a>
					<a href="">
						<i>
							<Icon icon="fa-solid:check" />
						</i>
						Following
					</a>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
	import { Icon } from '@iconify/vue';
	export default{
		name: 'BanNer',
		components:{
			Icon
		}
	}
</script>
<style>
	
</style>