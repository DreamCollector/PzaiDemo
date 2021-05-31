<template>
	<view>
		<scroll-view scroll-y class="page">
			<image src="/static/loginBg.png" mode="widthFix" class="response"></image>
			<view class="container">
				<view class="box login" :style="{'transform':login}">
					<view class="form-content">
						<view class="avtar">
							<view class="pic">
								<image src="/static/logo.png" alt="">
							</view>
						</view>
						<h1>Welcome Login</h1>
						<view>
							<view class="cu-form-group">
								<text class="cuIcon-people"></text>
								<input class="margin-left-xs" placeholder="请输入账户" name="input"></input>
							</view>
							<view class="cu-form-group">
								<text class="cuIcon-lock"></text>
								<input class="margin-left-xs" placeholder="请输入密码" name="input"></input>
							</view>
							<view class="padding flex flex-direction">
								<button class="cu-btn bg-blue lg">登陆</button>
							</view>

							<view class="text-center">
								还没有账户? <text @click="toSign()" class="signupbtn">注册</text>
							</view>
						</view>
					</view>
				</view>
				<view class="box signup" :style="{'transform':signup}">
					<view class="form-content">
						<view class="avtar">
							<view class="pic">
								<image src="/static/logo.png" alt="">
							</view>
						</view>
						<h1>Let's work together</h1>
						<view>
							<view class="cu-form-group">
								<text class="cuIcon-people"></text>
								<input class="margin-left-xs" placeholder="请输入账户" name="input"></input>
							</view>
							<view class="cu-form-group">
								<text class="cuIcon-phone"></text>
								<input class="margin-left-xs" placeholder="请输入手机号" name="input"></input>
							</view>
							<view class="cu-form-group">
								<text class="cuIcon-lock"></text>
								<input class="margin-left-xs" placeholder="请输入密码" name="input"></input>
							</view>
							<view class="padding flex flex-direction">
								<button class="cu-btn bg-blue lg">注册</button>
							</view>

							<view class="text-center">
								已经有账号了 ? <text @click='tologin()' class="loginbtn">登陆</text>
							</view>
						</view>
					</view>
				</view>
			</view>
			<view class="cu-tabbar-height"></view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				login: '',
				signup: 'transform: rotateY(-108deg);'

			};
		},
		methods: {
			toSign() {
				this.login = 'rotateY(180deg)';
				this.signup = 'rotateY(0deg)';

			},
			tologin() {
				this.login = 'rotateY(0deg)';
				this.signup = 'rotateY(-180deg)';

			}
		}
	}
</script>

<style lang="scss">
	.page {
		height: 100vh;
	}

	.container {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		width: 20rem;
		height: 28rem;
		perspective: 1500px;
		-webkit-perspective: 1500px;
		-moz-perspective: 1500px;
	}

	.box {
		position: absolute;
		top: 0;
		left: 0;
		width: 20rem;
		height: 28rem;
		border-radius: 10px;
		cursor: pointer;
		backface-visibility: hidden;
		transition: all 0.5s;
		user-select: none;
	}

	.signup {
		transform: rotateY(-108deg); //解決切换闪烁问题
	}

	.container .form-content {
		position: relative;
		width: 100%;
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-wrap: wrap;
		box-shadow: 0 0 1upx #3399ff;
		border-radius: 30upx;
		background-color: #fff;
	}

	.container .form-content h1 {
		margin-bottom: -50upx;
	}

	.container .form-content .avtar {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 100%;
	}

	.container .form-content .avtar .pic {
		position: relative;
		width: 160upx;
		height: 160upx;
		overflow: hidden;
		border-radius: 50%;
		border: 1upx solid #3399ff;
	}

	.container .form-content .avtar .pic image {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
	}

	.loginbtn,
	.signupbtn {
		color: #0081ff;
	}
</style>
