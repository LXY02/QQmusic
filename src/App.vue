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

</style>
