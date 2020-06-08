<template>
	<view class="">
		<scroll-view class="scroll-h" scroll-x>
			<view v-for="(tab, index) in tabBars" :key="tab.id" class="uni-tab-item" :id="tab.id" :data-current="index" @click="ontabtap(index)">
				<text class="uni-tab-item-title" :class="{ active: tabIndex == index }">
					{{ tab.name }}
					<view class="swiper-tab-line"></view>
				</text>
			</view>
		</scroll-view>

		<!-- 左右滑动切换利用swiper做 -->
		<!-- 小点  自动切换  间隔  时长  -->
		<swiper class="swiper-box" :indicator-dots="false" :autoplay="false" :interval="3000" :duration="200">
			<!-- 循环出个横向轮播图页 -->
			<!-- v-for="(item, index) in newsList" :key="index" -->
			<swiper-item>
				<scroll-view scroll-y="true" class="list">
					<!-- 拿到item中的每一个对象，每一个对象中还有一个数组用.list选择出来 -->
					<!-- v-for="(items, index1) in item.list" :key="index1" -->
					<!-- <block> -->

					<!-- :item="item" :index="index1" -->
					<view class="index_list1">
						<!-- widthFix 保持宽高比不变 -->
						<view class="user_info">
							<image src="../../static/demo5.jpg" mode="widthFix" lazy-load class="user_icon"></image>
							<text>昵称</text>
						</view>
						<text>+关注</text>
					</view>
					<view class="index_list2"><text class="list2_title">这是标题这是标题这是标题这是标题</text></view>
					<view class="index_list3"><image src="../../static/datapic/11.jpg" mode="widthFix" lazy-load></image></view>
					<view class="index_list4">
						<view class="list4_left">
							<view>
								<view class="icon iconfont icon-icon_xiaolian-mian"></view>
								<text>878</text>
							</view>
							<view>
								<view class="icon iconfont icon-kulian"></view>
								<text>12</text>
							</view>
						</view>
						<view class="list4_right">
							<view>
								<view class="icon iconfont icon-pinglun"></view>
								<text>215</text>
							</view>
							<view>
								<view class="icon iconfont icon-zhuanfa"></view>
								<text>40</text>
							</view>
						</view>
					</view>

					<!-- </block> -->
				</scroll-view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
import indexList from '../../components/index/index-list.vue';
export default {
	data() {
		return {
			tabBars: [
				{ name: '关注', id: 'guanzhu' },
				{ name: '推荐', id: 'tuijian' },
				{ name: '体育', id: 'tiyu' },
				{ name: '热点', id: 'redian' },
				{ name: '财经', id: 'caijing' },
				{ name: '娱乐', id: 'yule' },
				{ name: '军事', id: 'junshi' },
				{ name: '历史', id: 'lishi' },
				{ name: '本地', id: 'bendi' }
			],
			tabIndex: 0, //当前选中横向滚动的index值
			newsList: [
				//滑动模块的内容，内部有几个对象就显示几个滚动块
				//数据有多少个就展示多少个滑动组件

				// newsList:[  数据结构
				// 	{
				// 		list:[{},{}]
				// 	},
				// 	{
				// 		list:[{},{}]
				// 	},
				// 	{
				// 		list:[{},{}]
				// 	}
				// ]

				{
					list: [
						//关注页模块数据
						{
							//图片样式
							userPic: 'https://p.qqan.com/up/2020-5/2020052617112649304.jpg',
							userName: 'coderlch',
							isguanzhu: false, //是否关注
							title: '标题标题标题标题标题标题标题标题标题标题标题标题',
							type: '', //是图片类型还是视频类型img/video
							titlePic: '../../static/datapic/11.jpg', //封面图
							praise: {
								index: 0, //笑脸为1，哭脸为2，用index来记录
								laughNum: 1054, //笑脸  只能点一次
								cry: 51 //哭脸  只能点一次
							},
							comment: 10, //评论
							transpond: 10 //转发
						},
						{
							//图片样式
							userPic: 'https://p.qqan.com/up/2020-5/2020052617112649304.jpg',
							userName: 'coderlch',
							isguanzhu: false, //是否关注
							title: '标题标题标题标题标题标题标题标题标题标题标题标题',
							type: '', //是图片类型还是视频类型img/video
							titlePic: '../../static/datapic/11.jpg', //封面图
							praise: {
								index: 0, //笑脸为1，哭脸为2，用index来记录
								laughNum: 1054, //笑脸  只能点一次
								cry: 51 //哭脸  只能点一次
							},
							comment: 10, //评论
							transpond: 10 //转发
						}
					]
				}
			]
		};
	},
	components: {
		indexList
	},
	onLoad() {},
	methods: {
		attention(index) {
			// this.$set(list[index].isguanzhu,      ,!this.list[index].isguanzhu);
		},
		ontabtap(e) {
			this.tabIndex = e;
		}
	}
};
</script>

<style lang="scss">
.scroll-h {
	width: 750rpx;
	height: 80rpx;
	line-height: 80rpx;
	flex-direction: row;
	white-space: nowrap;
	border-bottom: 1px solid #c8c7cc;
}
.uni-tab-item {
	//横向排列
	display: inline-block;
	flex-wrap: nowrap;
	padding-left: 34rpx;
	padding-right: 34rpx;
}
.active {
	//头部横向滚动激活时候
	color: #ffaa00;
	font-weight: 700;
}
.swiper-box {
	padding: 20rpx;
	height: 1000rpx;
	.index_list1 {
		display: flex;
		height: 120rpx;
		justify-content: space-between;
		align-items: center;
		.user_info {
			display: flex;
			align-items: center;
			.user_icon {
				margin-right: 10rpx;
				background-color: #007aff;
				width: 100rpx;
				height: 100rpx;
				border-radius: 50%;
			}
		}
		text {
			background-color: #b2b2b2;
		}
	}
	.index_list2 {
	}
	.index_list3 {
		image {
			border-radius: 10rpx;
			width: 100%;
		}
	}
	.index_list4 {
		display: flex;
		justify-content: space-between;
		.list4_left {
			display: flex;
			.iconfont {
				font-size: 34rpx;
			}
			view {
				display: flex;
				text {
					font-size: 28rpx;
				}
				view {
					margin-right: 10rpx;
				}
			}
		}
		.list4_right {
			display: flex;
			.iconfont {
				font-size: 34rpx;
			}
			view {
				display: flex;
				text {
					font-size: 28rpx;
					margin-left: 10rpx;
				}
				view {
				}
			}
		}
	}
	.index_list4 .list4_left > view:first-child {
		margin-right: 24rpx;
	}
	.index_list4 .list4_right > view:last-child {
		margin-left: 24rpx;
	}
}
</style>
