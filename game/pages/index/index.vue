<template>
    <view>
        <view class="uni-padding-wrap">
            <view class="page-section swiper">
                <view class="page-section-spacing">
                    <swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
                        <swiper-item>
                            <view class="swiper-item uni-bg-red"><cover-image src="/static/image/1.jpg"/></view>
                        </swiper-item>
                        <swiper-item>
                            <view class="swiper-item uni-bg-green"><cover-image src="/static/image/2.jpg"/></view>
                        </swiper-item>
                        <swiper-item>
                            <view class="swiper-item uni-bg-blue"><cover-image src="/static/image/3.jpg"/></view>
                        </swiper-item>
                    </swiper>
                </view>
            </view>
        </view>
		<view>
			<uni-card :is-full="true" title="" thumbnail="https://img-cdn-qiniu.dcloud.net.cn/new-page/uni.png" extra="2018.12.12" >
			    <image src="/static/image/a.png" style="width: 100%;height: 150rpx;" @click="chatPage()">
					
				</image>
			</uni-card>
			
			<uni-card :is-full="true" title="" thumbnail="https://img-cdn-qiniu.dcloud.net.cn/new-page/uni.png" extra="2018.12.12" >
			    <image src="/static/image/a.png" style="width: 100%;height: 150rpx;" @click="chatPage()"></image>
			</uni-card>
			
			
			<uni-card
			    title="标题文字"
			    mode="style"
			    :is-shadow="true"
			    thumbnail="https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/cbd.jpg"
			    extra="Dcloud 2019-05-20 12:32:19"
			    note="Tips"
				@click="toLogin()"
			>
			        那是一个秋意盎然、金风送爽的日子，我和父母一起来到了位于上师大旁的康健园。一踏进公园，一股浓郁的桂香扑鼻而来，泌人心脾,让我心旷神怡，只见一朵朵开得正烈的金色桂花，迎风而立，仿佛在向我招手。我们追着这桂香，走进了清幽的公园。
			</uni-card>
		</view>
		
	</view>
	
</template>

<script>
	import {uniCard} from '@dcloudio/uni-ui'
	export default {
		components: {uniCard},
	    data() {
	        return {
	            background: ['color1', 'color2', 'color3'],
	            indicatorDots: true,
	            autoplay: true,
	            interval: 2000,
	            duration: 500
	        }
	    },
	    methods: {
	        chatPage(){
				uni.navigateTo({
					url:"../chat/chat"
				})
			},
			toLogin(){
				uni.navigateTo({
					url:"../login/login"
				})
			}
	    }
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
	
	swiper-item cover-image{
		height: 150px;
	}
</style>
