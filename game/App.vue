<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	@import "./common/uni.css";
	/*每个页面公共css */
	.page{
		width: 100%;
		height: 100%;
		background-color:#F1F1F1;
		position: relative;
	}
</style>
