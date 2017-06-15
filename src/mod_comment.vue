<template>
	<div class="mod_comment">
		<h2 class="comment__tit c_txt1">精彩评论</h2>
		<div class="comment__bd">
			<newpin_cont :arr="hotArr" title="热评">
				<div class="comment_add">
					<div class="comment_add__input_box c_bg2">
						<input class="comment_add__input c_txt1 js_cmt_input" type="text" placeholder="添加评论">
					</div>
					<a class="comment_add__btn c_txt3 js_cmt_btn" href="javascript:;">发布</a>
				</div>
			</newpin_cont>
			<newpin_cont :arr="newArr" title="最新评论"></newpin_cont>
		</div>
	</div>
</template>
<script>
	import axios from 'axios'
	import newpin_cont from './newpin_cont.vue'
	export default {
		data () {
			return {
				hotArr: [],
				newArr: []
			}
		},
		created(){
			var _this = this
			axios.get('//www.easy-mock.com/mock/593f5d088ac26d795ff1213e/hit-time9/comment')
				.then(function (response) {
					_this.hotArr = response.data.comment.splice(0, 5);
					_this.newArr = response.data.comment;
				})
				.catch(function (error) {
					console.log(error);
				});
		},
		components: {
			newpin_cont,
		}
	}
</script>
<style>
	.c_txt3 {
		color: #2B2321;
	}
	.comment_add {
		display: none
	}
	.comment__null {
		margin-top: 16px;
		font-size: 16px;
		text-align: center;
		opacity: .5
	}
	.comment_list__item {
		position: relative;
		padding: 20px 0 20px 60px;
		zoom: 1;
		border-bottom: 1px solid #EDEDED;
		font-size: 13px
	}
	.comment_list__avatar {
		position: absolute;
		left: 0;
		top: 20px;
		width: 44px;
		height: 44px
	}
	.comment_list__avatar img {
		display: block;
		width: 35px;
		height: 35px;
		border-radius: 44px
	}
	.comment_list__avatar .pic_mask {
		position: absolute;
		top: 0;
		left: 0;
		z-index: 1
	}
	.comment_list__name {
		margin-bottom: 2px;
		font-weight: 400;
		overflow: hidden;
		clear: both;
		height: 20px;
		white-space: nowrap;
		text-overflow: ellipsis
	}
	.comment_list__name a, .comment_list__name span {
		float: left;
		font-size: 13px
	}
	.comment_list__name a {
		opacity: .5
	}
	.comment_list__name span {
		color: #999;
		margin-right: 5px
	}
	.comment_list__name .c_tx_normal {
		color: #444
	}
	.comment_list__name .vip_icon {
		position: relative;
		top: -2px
	}
	.comment_list__name .vip_icon img {
		max-height: 24px
	}
	.comment_list__text {
		overflow: hidden;
		word-break: break-all;
		word-wrap: break-word;
		text-align: justify;
		font-size: 13px;
		color: #000
	}
	.comment_list__text a, .comment_list__text span {
		color: #31C27C
	}
	.comment_list__text em {
		font-style: normal;
		opacity: .5
	}
	.comment_list__text img {
		position: relative;
		vertical-align: middle;
		top: -2px
	}
	.comment_list__text--history {
		position: relative;
		margin-top: 15px;
		padding: 16px 20px;
		border: 1px solid #EDEDED
	}
	.comment_opt {
		position: relative
	}
	.comment_opt__item {
		position: absolute;
		right: 0;
		top: -20px;
		font-size: 0
	}
	.comment_list__date {
		margin-bottom: 8px;
		font-size: 13px;
		color: #000;
		opacity: .5
	}
	.comment_opt__del {
		display: none;
		margin-left: 20px;
		font-size: 13px;
		opacity: .5
	}
	.comment_list__item:hover .comment_opt__del {
		display: inline
	}
	.comment_opt__zan {
		display: inline-block;
		margin-right: 20px
	}
	.comment_opt__zan--on {
		color: #000
	}
	.comment__opt_icon {
		display: inline-block;
		vertical-align: -2px;
		margin-right: 10px;
		width: 16px;
		height: 16px;
		stroke-width: 0;
		stroke: none;
		fill: currentColor;
		opacity: .5
	}
	.comment_opt__zan--on .comment__opt_icon {
		opacity: 1
	}
	.comment_opt__txt {
		display: inline-block;
		width: 32px;
		font-size: 13px;
		opacity: .5
	}
	.comment_opt__zan .comment__opt_icon {
		/*background: url(img/comment_sprite.png) no-repeat 0 -20px\0*/
	}
	.comment_opt__zan--on .comment__opt_icon {
		fill: #31C27C;
		/*background: url(img/comment_sprite.png) no-repeat -20px -20px\0*/
	}
	.comment_opt__feedback .comment__opt_icon {
		margin-right: 0;
		/*background: url(img/comment_sprite.png) no-repeat -40px -20px\0*/
	}
	.comment_type__hd {
		padding-bottom: 14px;
		overflow: hidden;
		border-bottom: 1px solid #EDEDED
	}
	.comment_type__tit {
		float: left;
		font-size: 14px;
		color: #000;
		font-weight: 400
	}
	.comment_type__num {
		font-size: 12px;
		color: #000;
		opacity: .5
	}
	.comment__intro {
		position: relative;
		text-align: center;
		line-height: 24px;
		font-size: 13px;
		color: #000;
		margin: 20px 0;
		opacity: .5
	}
	.comment__intro p {
		position: relative
	}
	.comment__intro_txt {
		position: relative;
		display: inline-block;
		padding: 0 2px 0 10px;
		z-index: 10;
		background-color: #FFF
	}
	.comment__intro_line {
		position: absolute;
		left: 50%;
		margin-left: -150px;
		top: 50%;
		width: 300px;
		height: 1px;
		background-color: #EDEDED;
		overflow: hidden
	}
	.comment__intro_link {
		position: relative;
		z-index: 10;
		display: inline-block;
		padding: 0 10px 0 2px;
		color: #000;
		background-color: #FFF
	}
	.comment_input__tool_btn {
		display: block;
		float: left;
		padding: 0 12px;
		height: 28px;
		line-height: 28px;
		margin-left: 8px;
		font-size: 14px;
		text-overflow: ellipsis;
		white-space: nowrap;
		overflow: hidden;
		border-radius: 4px;
		background-color: transparent;
		border: 1px solid #31C27C;
		border-color: currentColor;
		color: #31C27C
	}
	.comment_input__tool_btn.disable {
		border: 1px solid grey;
		color: grey;
		cursor: default
	}
	.mod_comment {
		overflow: hidden
	}
	.comment__tit {
		margin-bottom: 12px;
		font-size: 24px;
		color: #000;
		font-weight: 400;
	}
	.mod_page_nav {
		clear: both;
		text-align: center;
		margin: 30px 0;
		font-size: 0
	}
	.comment_loading {
		display: none
	}
	@media screen and (max-width: 738px) {
		.comment__tit {
			display: none;
		}
		.comment__bd {
			margin: 0 16px
		}
		.comment_input {
			display: none
		}
		.comment_type__hd {
			margin-bottom: 14px;
			padding-bottom: 0;
			border-bottom: none
		}
		.comment_type__tit {
			font-size: 20px
		}
		.comment_type__num {
			vertical-align: -8px
		}
		.comment__opt_icon {
			margin-right: 5px
		}
		.comment_list__item {
			padding: 10px 0 10px 40px;
			border-bottom: none
		}
		.comment_list__item::after {
			content: "";
			position: absolute;
			bottom: 0;
			left: 40px;
			right: -16px;
			z-index: 1;
			-webkit-box-sizing: border-box;
			height: 0;
			border-bottom: solid 1px #E5E5E5
		}
		.comment_list__avatar {
			top: 15px
		}
		.comment_list__name a, .comment_list__name span {
			font-size: 14px
		}
		.comment_list__date {
			margin-bottom: 0;
			font-size: 12px
		}
		.comment_list__text {
			font-size: 14px
		}
		.comment_list__text--history {
			margin-top: 5px;
			padding: 10px
		}
		.comment_opt__zan {
			margin-right: 24px
		}
		.comment_opt__del {
			display: block;
			color: #000
		}
		.comment__null {
			font-size: 14px
		}
		.comment_add {
			display: -webkit-box;
			-webkit-box-align: center;
			margin-bottom: 4px;
			width: 100%;
			-webkit-box-sizing: border-box
		}
		.comment_add--fixed {
			position: fixed;
			bottom: 0;
			left: 0;
			right: 0;
			z-index: 100
		}
		.comment_add__input_box {
			position: relative;
			-webkit-box-flex: 1;
			height: 30px;
			overflow: hidden;
			border-radius: 2px;
			background-color: #E5E5E5
		}
		.comment_add__input {
			width: 100%;
			height: 30px;
			-webkit-box-sizing: border-box;
			padding: 0 10px;
			font-size: 14px;
			border: none;
			background-color: transparent
		}
		::-webkit-input-placeholder {
			color: currentColor
		}
		.comment_add__btn {
			position: relative;
			display: block;
			width: 60px;
			height: 30px;
			margin-left: 10px;
			line-height: 28px;
			overflow: hidden;
			text-align: center;
			font-size: 16px;
			color: #31C27C;
			text-align: center;
			border-radius: 2px;
			-webkit-box-sizing: border-box;
			border: solid 1px #31C27C;
			border-color: currentColor
		}
		.comment_list__item .comment_add {
			margin: 10px 0 4px
		}
		@media only screen and (-webkit-min-device-pixel-ratio: 2) {
			.comment_list__item::after {
				-webkit-transform: scaleY(.5)
			}
			.comment_list__text--history li::after {
				-webkit-transform: scaleX(.5)
			}
		}

		/*.mod_page_nav {*/
		/*display: none*/
		/*}*/
		.comment_loading {
			display: block;
			margin: 4px 0;
			text-align: center
		}
		.comment_loading__txt {
			display: inline-block;
			font-size: 14px;
			color: #000;
			line-height: 40px;
			opacity: .5
		}
		.comment_loading__txt::after {
			content: "";
			display: inline-block;
			margin-left: 4px;
			vertical-align: 2px;
			width: 8px;
			height: 8px;
			border-bottom: solid 1px currentColor;
			border-left: solid 1px currentColor;
			-webkit-transform: rotate(-45deg)
		}
	}
	.comment_type {
		margin-bottom: 20px
	}
	.comment_type__tit {
		position: relative;
		display: -webkit-box;
		-webkit-box-align: center;
		-webkit-box-pack: center;
		float: none;
		font-size: 15px
	}
	.comment_type__tit::after, .comment_type__tit::before {
		content: "";
		display: block;
		margin: 0 15px;
		width: 23px;
		height: 2px;
		background-color: currentColor;
		opacity: .1
	}

</style>