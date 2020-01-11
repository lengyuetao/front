<template>
	<view class="chatPage">
		<view class="uni-flex uni-row" style="height: 100%;">
			<scroll-view scroll-y="true" scroll-top="scrollTop" @scroll="scroll"  :style="{height:iStatusBarHeight+'px'}" scroll-with-animation="true">
				<view   v-for="(row,index) in msgList" :key="index" >
					<!--左侧消息-->
					<view class="uni-flex uni-row" v-if="row.type=='friend'">
						<view style="border-radius: 100%;">
							<image src="../../static/icon/group.png" style="width: 60rpx;height: 60rpx;margin-top: 30rpx;"></image>
						</view>
						<view class="uni-card" style="margin-left: 30rpx;background-color:#FFFFFF;padding: 15rpx;margin-right: 30rpx;font-size: 35rpx;">
							<rich-text :nodes="row.content" style="align-content: center;align-items: center;">
							</rich-text>
						</view>
					</view>
					
					
					<!--右侧消息-->
					<view v-else-if="row.type=='user'" class="uni-flex uni-row" style="-webkit-justify-content: flex-end;justify-content: flex-end;">
						<view class="uni-card" style="margin-right: 30rpx;background-color:#FFFFFF;padding: 15rpx;margin-left: 30rpx;font-size: 35rpx;">
							<rich-text :nodes="row.content" style="align-content: center;align-items: center;">
							</rich-text>
						</view>
						<view style="border-radius: 100%;">
							<image src="../../static/icon/group.png" style="width: 60rpx;height: 60rpx;margin-top: 30rpx;"></image>
						</view>
					</view>
				</view>
			</scroll-view>
		</view>
		
		<view class="uni-flex uni-row messsageBox">
			<view style="margin-left: 8px;">
				<uni-icons type="plus" size="35" ></uni-icons>
			</view>
			<view class="uni-textarea" style="">
				<textarea style="height: 35px;margin-top: 10px;font-size: 35rpx;" placeholder="" v-model="msgContent"  auto-height/>
			</view>
			<view style="margin-right: 8px;">
				<uni-icons type="paperplane" size="35" @click='sendMsg'></uni-icons>
			</view>
		</view>
		
	</view>
</template>

<script>
	import {uniPopup,uniIcons} from "@dcloudio/uni-ui"
	export default {
		components: {uniPopup,uniIcons },
		data() {
			return {
				scrollTop:0,
				iStatusBarHeight:0,
				old: {
				        scrollTop: 0
				     },
				msgList:[],
				msgContent:''
			}
		}, 
		onLoad:function(e){
			const { windowWidth, windowHeight } = uni.getSystemInfoSync();	
			this.iStatusBarHeight=windowHeight-50;
			uni.connectSocket({
				url:"ws://192.168.0.149:8081/chat/20"
			})
		},
		onHide:function(){
			console.log('页面隐藏')
		},
		onUnload:function(){
			console.log('关闭socket')
			//关闭socket
			uni.closeSocket();
		},
		methods: {
			scroll:function(event){
				this.scrollTop = event.detail.scrollTop
			},
			sendMsg:function(e){
				let self=this;
				
				if(''==this.msgContent){
					return;
				}
				let msgData={
					'fromUser':20,
					'toUser':1,
					'content':this.msgContent
				};
				this.msgList.push({'content':this.msgContent,'type':'user'});
				
				uni.sendSocketMessage({
					data: this.msgContent
				});
				console.info(this.msgContent);
				this.msgContent='';
				
				//监听服务器返回的消息
				uni.onSocketMessage(function (res) {
				  self.msgList.push({'content':res.data,'type':'friend'});
				});
			}
		}
	}
</script>

<style>
	.chatPage{
		background-color: #F2F2F2;
	}
	
	.messsageBox{
		bottom: 0px;
		display: flex;
		width: 100%;
		position: fixed;
		background-color: #F4F5F6;
		border: 1upx solid #F4F5F6;
	}
</style>
