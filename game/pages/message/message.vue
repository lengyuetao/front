<template>
	<view>
		<!-- 带描述信息 -->
		<uni-list>
		    <uni-list-item title="标题文字" note="描述信息"></uni-list-item>
		    <uni-list-item title="标题文字" note="描述信息" :show-badge="true" badge-text="12"></uni-list-item>
		</uni-list>
	</view>
</template>

<script>
	import {uniList ,uniListItem} from "@dcloudio/uni-ui"
	
	export default {
		components: {uniList,uniListItem},
		data() {
			return {
				lists:[
					'sdss',
					'aaa',
					'bbb'
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
