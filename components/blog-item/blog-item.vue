<template>
	<view class="blogitem">
		<view class="head">
			<view class="userinfo">
				<view class="avatar">
					<image src="../../static/uni-center/avatar.png" mode="aspectFill"></image>
				</view>
				<view class="name">As We are </view>
				<view class="time">
					<uni-dateformat :date="Date.now()" format="MM月dd hh:mm" :threshold="[60000,3600000*24*30]"></uni-dateformat>
				</view>	
			</view>
			<view class="more" @click="sheetShow=true"> 
				<u-icon name="more-dot-fill"></u-icon>
			</view>
		</view>
		<view class="body">
			<view class="title">关于如何健康自检</view>
			<view class="text">
				<view class="t">
					
				</view>
			</view>
			<view class="piclist">
				<view class="pic" :class="picArr.length==1? 'only':''" v-for="(item,index) in picArr" :key="item">
					<image src="https://th.bing.com/th/id/OIG.reZPUb4G1stz0cb5WCJh?w=1024&h=1024&rs=1&pid=ImgDetMain" mode="aspectFill"></image>
				</view>
			</view>
		</view>
		<view class="info">
			<view class="box"><text class="aliiconfont aliicon-liulan">15</text></view>
			<view class="box"><text class="aliiconfont aliicon-xiaoxi">20</text></view>
			<view class="box"><text class="aliiconfont aliicon-dianzan">11</text></view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"blog-item",
		data() {
			return {
				picArr:[1]
			};
		}
	}
</script>

<style lang="scss" scoped>
.blogitem{
	.head{
		display:flex;
		font-size: 32rpx;
		align-items: center;
		justify-content: space-between;
		.userinfo{
			display: flex;
			align-items: center;
			.avatar{ 
				width: 60rpx;
				height: 60rpx;
				border-radius: 50%;
				border-radius: 50%;
				overflow: hidden;
				image{ 
					width: 100%;
					height: 100%;
					display: block;
				}
			}
			.name{				
				color:#222;				
				padding-left:10rpx;
			}
			.time{
				color:#888;
				font-size: 22rpx;
				padding-left:20rpx;
			}
		}
		.more{
			padding-right: 20rpx;
			.iconfont{ 
				font-size: 70rpx;
				color:#888;
			}
		}
	}
	.body{
		padding:15rpx 0 30rpx;
		.title{
			font-size: 44rpx;
			color:#000;
			font-weight: 600;	
			text-align: justify;
		}
		.text{
			padding-top:10rpx;
			padding-bottom:10rpx;
			font-size: 30rpx;
			text-align: justify;
			color:#888;				
			.t{
				text-overflow: -o-ellipsis-lastline;
				overflow: hidden;				
				text-overflow: ellipsis;		
				display: -webkit-box;			
				-webkit-line-clamp: 2;			
				line-clamp: 2;					
				-webkit-box-orient: vertical;	
			}
		}
		.piclist{
			display: flex;
			padding-top:20rpx;
			.pic{
				width: 225rpx;
				height: 225rpx;
				margin-right: 6rpx;
				overflow: hidden;
				image{
					width: 100%;
					height: 100%;
				}	
				&:first-child{
					border-radius: 20rpx 0 0 20rpx;					
				}
				&:last-child{
					border-radius: 0 20rpx 20rpx 0;					
				}
				&.only{
					border-radius: 20rpx;
				}
				
			}
			
		}
	}
	.info{
		display: flex;
		align-items: center;
		justify-content:space-around;
		font-size: 26rpx;	
		color:#333;
		.box{
			display: flex;
			align-items: center;			
			padding:15rpx 0 5rpx;
			flex:1;
			display: flex;
			justify-content: center;
			.iconfont{
				font-size: 40rpx;
				padding-right: 10rpx;
			}
		}
		
	}
}
</style>