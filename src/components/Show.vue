<template>
	<div>
		<div style="padding:8px 0;line-height:28px;color:#666;">
			<div class="video" v-if="data.video_url">
				<video style="width:100%;" height="240" controls>
					<source :src="data.video_url" type="video/mp4">
					您的浏览器不支持Video标签。
				</video>
			</div>
			<div v-if="data.images">
				<div v-for="(item,index) in data.images" :key="index">
					<img :src="item" style="width:100%;" alt="">
				</div>
			</div>
			<van-row>
				<van-panel title="活动展示"></van-panel>
			</van-row>
			<div v-html="data.content"></div>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'show',
		props: ['data'],
		mounted: function () {
			console.log(this.data)
		}
	}
</script>

<style scoped>
</style>
