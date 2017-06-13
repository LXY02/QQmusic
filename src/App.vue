<template>
	<div id="app">
		<section class="wrap js_warp">
			<mod_top></mod_top>
			<mod_hit></mod_hit>
			<mod_vote></mod_vote>
			<mod_rank></mod_rank>
			<mod_playlist></mod_playlist>
			<mod_friendlink></mod_friendlink>
			<mod_comment></mod_comment>
		</section>
	</div>
</template>

<script>
	import modTop from './mod_top.vue'
	import modHit from './mod_hit.vue'
	import modVote from './mod_vote.vue'
	import modRank from './mod_rank.vue'
	import modPlaylist from './mod_playlist.vue'
	import modFriendlink from './mod_friendlink.vue'
	import modComment from './mod_comment.vue'
	export default {
		name: 'app',
		data () {
			return {

			}
		},
		components: {
			modTop,
			modHit,
			modVote,
			modRank,
			modPlaylist,
			modFriendlink,
			modComment
		}
	}
</script>

<style>
	/*自由配置项_S*/
	.c_txt3{color:#2b2321;}/*高亮字色、镂空按钮色*/
	.c_bg1{background-color:#f1ece6;}/*页面背景色*/
	/*自由配置项_E*/


	/*浅底配色_S*/
	.c_txt1{color:#2b2322;}/*常应用于正文字色*/
	.c_bor1,
	.c_bor1::after{border-color:rgba(43,35,34,.1);}
	.c_bg2{background-color:rgba(0,0,0,.1);}/*常应用于内容块底色*/
	/*浅底配色_E*/


	.popup_history__cont{-webkit-overflow-scrolling: touch;margin-top: 32px;overflow: scroll;overflow-x: hidden;height: 100%}
</style>
