<template>
	<view>
		<web-view :src="page_url"></web-view>
		<view class="go-back" @click="goHome">
			<text>返回首页>></text>
		</view>
	</view>

</template>

<script>
	export default {
		data() {
			return {
				page_url: ''
			}
		},
		onLoad() {
			this.stop();
		},
		methods: {
			goHome() {
				uni.redirectTo({
					url: '/pages/lip/lip_index'
				});
			},
			stop() {
				var box = function(e) {
					passive: false;
				};
				document.body.style.overflow = 'hidden';
				document.addEventListener("touchmove", box, false);
			},
		}
	}
</script>

<style>
	.go-back {
		position: absolute;
		z-index: 9999;
		bottom: 30px;
		right: 30px;
		color: #fff;
	}
</style>