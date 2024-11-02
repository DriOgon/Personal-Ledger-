<template>
	<view class="container">
		<view class="sa-user-info">
			<view class="sa-flex-x space desc">
				<view class="userinfo">
					<view class="nickname">用户_bwaUN</view>
					<view class="sign">更换个人信息</view>
				</view>
				<view class="cover">
					<image src="@/static/avatar.png" mode="aspectFill"></image>
				</view>
			</view>
		</view>
		<!-- 新增账本管理区域 -->
		<view class="sa-account-management">
			<button hover-class="" open-type="feedback">
			<view class="sa-flex-x space item brtop">
				<image src="@/static/icon/account-management.png" class="icon"></image>
				<view class="name">账本管理</view>
				<view class="drow">></view>
			</view>
			</button>
			<button hover-class="" open-type="feedback">
			<view class="sa-flex-x space item line">
				<image src="@/static/icon/category-expense.png" class="icon"></image>
				<view class="name">分类支出</view>
				<view class="drow">></view>
			</view>
			</button>
			<button hover-class="" open-type="feedback">
			<view class="sa-flex-x space item brbot line">
				<image src="@/static/icon/bill-export.png" class="icon"></image>
				<view class="name">账单导出</view>
				<view class="drow">></view>
			</view>
			</button>
		</view>
		<view class="sa-menu">
			<button hover-class="" open-type="feedback">
				<view class="sa-flex-x space item brtop">
					<image src="@/static/icon/help-feedback.png" class="icon"></image>
					<view class="name">帮助与反馈</view>
					<view class="drow">></view>
				</view>
			</button>
			<button hover-class="" open-type="share">
				<view class="sa-flex-x space item line">
					<image src="@/static/icon/share-friend.png" class="icon"></image>
					<view class="name">分享给好友</view>
					<view class="drow">></view>
				</view>
			</button>
			<button hover-class="" @click="url('index/article?id=1')">
				<view class="sa-flex-x space item brbot line">
					<image src="@/static/icon/add-desktop.png" class="icon"></image>
					<view class="name">添加到桌面</view>
					<view class="drow">></view>
				</view>
			</button>
			<button hover-class="" @click="url('index/article?id=0')">
				<view class="sa-flex-x space item about">
					<image src="@/static/icon/about-us.png" class="icon"></image>
					<view class="name">关于我们</view>
					<view class="drow">></view>
				</view>
			</button>
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad() {

		},
		methods: {
			url(url) {
				uni.navigateTo({url: `/pages/${url}`});
			}
		}
	}
</script>

<style lang="less">
	.sa-user-info {
		background-color: #fff;
		padding: 40rpx;
		margin: 0 20rpx 20rpx 20rpx;
		border-radius: 20rpx;
		.desc {
			.cover {
				width: 120rpx;
				height: 120rpx;
				background-color: #f3f3f3;
				border: 1px solid #fff;
				box-shadow: 2rpx 0 10rpx rgba(50, 50, 50, .2);
				border-radius: 50%;
				image {
					width: 100%;
					height: 100%;
					border-radius: 50%;
				}
			}
			.userinfo {
				width: 360rpx;
				.nickname {
					font-size: 34rpx;
					color: #333;
					font-weight: bold;
				}
				.sign {
					color: #999;
					font-size: 30rpx;
					margin-top: 5rpx;
				}
			}
		}
	}
	.sa-account-management {
		margin: 20rpx;
		.item {
			height: 120rpx;
			padding: 0 40rpx;
			background-color: #fff;
			display: flex;
			align-items: center;
			justify-content: flex-start; /* 文字紧贴图标 */
			cursor: pointer; /* 添加鼠标指针样式 */
			transition: background-color 0.3s;

			&:hover {
				background-color: #f0f0f0; /* 悬停时的背景颜色 */
			}

			.icon {
				width: 48rpx;
				height: 48rpx;
				margin-right: 20rpx; /* 进一步减小右边距，使文字更贴近图标 */
			}
			.name {
				font-size: 32rpx;
			}
			.drow {
				font-size: 32rpx;
				color: #999;
				margin-left: auto; /* 让箭头靠右 */
			}
			&.brtop {
				border-radius: 20rpx 20rpx 0 0;
			}
			&.brbot {
				border-radius: 0 0 20rpx 20rpx;
			}
			&.line:after {
				position: absolute;
				top: 0;
				left: 0;
				right: 0;
				width: 100%;
				height: 2rpx;
				content: '';
				background-image: linear-gradient(45deg, rgba(0,0,0,0), rgba(0,0,0,.1), rgba(0,0,0,0));
			}
		}
	}
	.sa-menu {
		margin: 20rpx;
		.item {
			height: 120rpx;
			padding: 0 40rpx;
			background-color: #fff;
			display: flex;
			align-items: center;
			justify-content: flex-start; /* 文字紧贴图标 */
			cursor: pointer; /* 添加鼠标指针样式 */
			transition: background-color 0.3s;

			&:hover {
				background-color: #f0f0f0; /* 悬停时的背景颜色 */
			}

			.icon {
				width: 48rpx;
				height: 48rpx;
				margin-right: 20rpx; /* 进一步减小右边距，使文字更贴近图标 */
			}
			.name {
				font-size: 32rpx;
			}
			.drow {
				font-size: 32rpx;
				color: #999;
				margin-left: auto; /* 让箭头靠右 */
			}
			&.brall {
				border-radius: 10rpx;
			}
			&.brtop {
				border-radius: 20rpx 20rpx 0 0;
			}
			&.brbot {
				border-radius: 0 0 20rpx 20rpx;
			}
			&.line:after {
				position: absolute;
				top: 0;
				left: 0;
				right: 0;
				width: 100%;
				height: 2rpx;
				content: '';
				background-image: linear-gradient(45deg, rgba(0,0,0,0), rgba(0,0,0,.1), rgba(0,0,0,0));
			}
			&.about {
				margin-top: 20rpx;
				border-radius: 20rpx;
			}
		}
	}
</style>