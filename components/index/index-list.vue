<template>
	<view>
		<block v-for="(item, index) in item" :key="index">
			<view class="index-list1">
				<view>
					<image class="head" 
					:src="item.userPic" mode="widthFix" lazy-load ></image>
					<text class="name">{{ item.userName }}</text>
				</view>
				<view>
					<view :class="[item.isguanzhu === true ? 'attentionfalse' : 'attentiontrue']" @tap="attention(index)">
						<view class="icon iconfont icon-zengjia" v-show="item.isguanzhu"></view>
						<text>关注</text>
					</view>
				</view>
			</view>
			<view class="index-list2">标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题</view>
			<view class="index-list3">
				<image src="../../static/datapic/11.jpg" mode="widthFix" lazy-load></image>
				<view class="index-list-play icon iconfont icon-bofang"></view>
				<view class="index-list-playinfo">20w次播放量&nbsp;2:47</view>
			</view>
			<view class="index-list4">
				<view>
					<view class="flex mr">
						<view class="icon iconfont icon-icon_xiaolian-mian"></view>
						<text>16530</text>
					</view>
					<view class="flex">
						<view class="icon iconfont icon-kulian"></view>
						<text>3250</text>
					</view>
				</view>
				<view>
					<view class="flex">
						<view class="icon iconfont icon-pinglun"></view>
						<text class="ml">11650</text>
					</view>
					<view class="flex ml">
						<view class="icon iconfont icon-zhuanfa"></view>
						<text class="ml">15620</text>
					</view>
				</view>
			</view>
		</block>
	</view>
</template>

<script>
export default {
	data() {
		return {};
	},
	props: {
		item: Object,
		index: Number
	},
	onLoad() {
		console.log('页面加载');
	},
	onShow() {
		console.log('页面显示');
	},
	onReady() {
		console.log('页面初次显示');
	},
	onHide() {
		console.log('页面隐藏');
	}
};
</script>

<style lang="scss">
.index-list {
	padding: 20rpx;
	border-bottom: 1rpx solid #cccccc;
	.index-list1 > view:first-child {
		display: flex;
		align-items: center; /*垂直居中*/
	}
	.index-list1 > view:last-child {
		display: flex;
		align-items: center;
	}
	.index-list1 {
		display: flex;
		justify-content: space-between; /*左右靠两边*/
		align-items: center; /*垂直居中*/
		.head {
			width: 120rpx;
			height: 120rpx;
			border-radius: 50%;
			margin-right: 15rpx;
		}
		.name {
			color: #969599;
		}
		.attentionfalse {
			display: flex;
			padding-left: 10rpx;
			border-radius: 10rpx;
			background-color: #eeeeee;
			justify-content: space-between;
			padding-right: 6rpx;
			text {
				line-height: 60rpx;
			}
		}
		.attentiontrue {
			display: flex;
			background-color: #ff1317;
			padding-left: 10rpx;
			border-radius: 10rpx;
			justify-content: space-between;
			padding-right: 6rpx;
			text-align: center;
			color: #ffffff;
			padding: 0 8rpx;
			font-weight: 500;
			text {
				line-height: 60rpx;
			}
		}
	}

	.index-list2 {
		flex: 1;
		height: 100rpx;
		width: 87%;
		line-height: 100rpx;
		overflow: hidden;
		white-space: nowrap;
		text-overflow: ellipsis;
		font-size: 30rpx;
		font-weight: 500;
	}
	.index-list3 {
		position: relative;
		.index-list-play {
			position: absolute;
			top: 50%;
			left: 50%;
			transform: translate(-50%, -50%);
			color: #ffffff;
			font-size: 100rpx;
		}
		.index-list-playinfo {
			position: absolute;
			bottom: 30rpx;
			right: 18rpx;
			text-align: center;
			border-radius: 100rpx;
			padding: 0 18rpx;
			height: 40rpx;
			background-color: rgba(51, 51, 51, 0.72);
			font-size: 24rpx;
			padding-top: 6rpx;
			padding-bottom: 6rpx;
			color: #ffffff;
		}
	}
	.index-list3 image {
		width: 100%;
		border-radius: 10rpx;
	}
	.index-list4 {
		display: flex;
		justify-content: space-between; /*左右靠两边*/
		align-items: center; /*垂直居中*/
		text,
		view {
			font-size: 32rpx;
			color: #969599;
		}
		.flex {
			display: flex;
		}
		.icon-icon_xiaolian-mian,
		.icon-kulian {
			margin-right: 15rpx;
		}
		.ml {
			margin-left: 15rpx;
		}
		.mr {
			margin-right: 20rpx;
		}
		.ml {
			margin-left: 20rpx;
		}
	}
	.index-list4 > view {
		display: flex;
	}
}






	.index-list1 > view:first-child {
		display: flex;
		align-items: center; /*垂直居中*/
	}
	.index-list1 > view:last-child {
		display: flex;
		align-items: center;
	}
	.head {
		width: 120rpx;
		height: 120rpx;
		border-radius: 50%;
		margin-right: 15rpx;
	}
	.index-list4 > view {
		display: flex;
	}
	.flex {
		display: flex;
	}
	.icon-icon_xiaolian-mian,
	.icon-kulian {
		margin-right: 15rpx;
	}
	.ml {
		margin-left: 15rpx;
	}
	.mr {
		margin-right: 20rpx;
	}
	.ml {
		margin-left: 20rpx;
	}
</style>
