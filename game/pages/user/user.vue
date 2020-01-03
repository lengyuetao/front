<template>
	<view class="page">
		<!--账户中心-->
		<view>
			<!-- 一般用法 -->
			<uni-card title="账户中心" mode='basic' :is-shadow="true" >
			    <!-- 一般用法 -->
			    <uni-grid :column="3" 	>
			        <uni-grid-item>
			            <text class="text">个人资料</text>
			        </uni-grid-item>
			        <uni-grid-item>
			            <text class="text">充值</text>
			        </uni-grid-item>
			        <uni-grid-item>
			            <text class="text">提现</text>
			        </uni-grid-item>
			    </uni-grid>
			    
			</uni-card>
		</view>
		<!--账单记录-->
		<view>
			<!-- 一般用法 -->
			<uni-card title="账单记录" mode='basic' :is-shadow="true" >
			    <!-- 一般用法 -->
			    <uni-grid :column="3" >
			        <uni-grid-item>
			            <text class="text">充值记录</text>
			        </uni-grid-item>
			        <uni-grid-item>
			            <text class="text">红包记录</text>
			        </uni-grid-item>
			        <uni-grid-item>
			            <text class="text">账户明细</text>
			        </uni-grid-item>
			    </uni-grid>
			    
			</uni-card>
		</view>
		
		
		<!--其它服务-->
		<view>
			<!-- 一般用法 -->
			<uni-card title="其它服务" mode='basic' :is-shadow="true" >
			    <!-- 一般用法 -->
			    <uni-grid :column="3" >
			        <uni-grid-item>
			            <text class="text">代理中心</text>
			        </uni-grid-item>
			        <uni-grid-item>
			            <text class="text">推广赚钱</text>
			        </uni-grid-item>
			        <uni-grid-item>
			            <text class="text">玩法规则</text>
			        </uni-grid-item>
			    </uni-grid>
				
			    <uni-grid :column="3" >
			        <uni-grid-item>
			            <text class="text">帮助中心</text>
			        </uni-grid-item>
			        <uni-grid-item>
			            <text class="text">消息中心</text>
			        </uni-grid-item>
			        <uni-grid-item>
			            <text class="text">设置</text>
			        </uni-grid-item>
			    </uni-grid>
			</uni-card>
		</view>
	</view>
</template>

<script>
	import {uniGrid,uniGridItem,uniCard} from "@dcloudio/uni-ui"
	export default {
		components: {uniGrid,uniGridItem,uniCard},
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>


text{
	text-align: center;
	margin-top: 44px;
}

</style>
