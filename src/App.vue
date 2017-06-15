<template>
	<div id="app">
		<section class="wrap js_warp">
			<mod_top></mod_top>
			<mod_hit @playMusic="playMusic" @pauseMusic="pauseMusic" @stopMusic="stopMusic"></mod_hit>
			<mod_vote></mod_vote>
			<mod_rank></mod_rank>
			<mod_playlist></mod_playlist>
			<mod_friendlink></mod_friendlink>
			<mod_comment></mod_comment>
		</section>
	</div>
</template>

<script type="text/ecmascript-6">
	import mod_top from './mod_top.vue'
	import mod_hit from './mod_hit.vue'
	import mod_vote from './mod_vote.vue'
	import mod_rank from './mod_rank.vue'
	import mod_playlist from './mod_playlist.vue'
	import mod_friendlink from './mod_friendlink.vue'
	import mod_comment from './mod_comment.vue'

	import { bus } from './bus.js'

	export default {
		name: 'app',
		data () {
			return {
				playList: []
			}
		},
		methods: {
			playMusic (Ftrack_mid) {
				if(typeof Ftrack_mid == 'string') {
					if(!this.audio.paused) {
						this.pauseMusic();
					}
					if(this.audio.Ftrack_mid != Ftrack_mid) {
						this.audio.src = 'http://isure.stream.qqmusic.qq.com/C100' + Ftrack_mid + '.m4a?fromtag=32';
					}
					this.audio.Ftrack_mid = Ftrack_mid;
					this.audio.play();
				} else {
					this.playList = Ftrack_mid;
					bus.$emit('playNext', this.playList.shift());
				}
			},
			pauseMusic () {
				this.audio.pause();
			},
			stopMusic() {
				this.audio.pause();
				this.audio.currentTime = 0;
			}
		},
		created () {
			this.audio = new Audio();
			this.audio.addEventListener('ended', () => {
				if(this.playList.length) {
					bus.$emit('playNext', this.playList.shift());
				}
			});
		},
		components: {
			mod_top,
			mod_hit,
			mod_vote,
			mod_rank,
			mod_playlist,
			mod_friendlink,
			mod_comment
		}
	}

</script>

<style>
	html { -webkit-text-size-adjust: 100%; -webkit-tap-highlight-color: rgba(0, 0, 0, 0) }
	a, img { -webkit-touch-callout: none }
	body, dd, dl, form, h1, h2, h3, h4, h5, h6, input, ol, p, td, textarea, th, ul { margin: 0; padding: 0 }
	h1, h2, h3, h4, h5, h6 { font-size: 100% }
	li { list-style: none }
	table { border-collapse: collapse; border-spacing: 0 }
	button:focus, input:focus, textarea:focus { outline: 0 }
	a, a:hover { text-decoration: none }
	button, input, select, textarea { font-family: inherit; font-size: 100% }
	body { font: 12px/1.5 FZLTXIHJW--GB1-0, "hiragino sans gb", "Helvetica Neue", Helvetica, STHeiTi, Arial, sans-serif }
	.hide { position: absolute; width: 0; height: 0; overflow: hidden; opacity: 0 }
	/*自由配置项_S*/
	.c_txt3 { color: #2B2321; }
	/*高亮字色、镂空按钮色*/
	.c_bg1 { background-color: #F1ECE6; }
	/*页面背景色*/
	/*自由配置项_E*/

	/*浅底配色_S*/
	.c_txt1 { color: #2B2322; }
	/*常应用于正文字色*/
	.c_bor1,
	.c_bor1::after { border-color: rgba(43, 35, 34, .1); }
	.c_bg2 { background-color: rgba(0, 0, 0, .1); }
	/*常应用于内容块底色*/
	/*浅底配色_E*/

	.popup_history__cont { -webkit-overflow-scrolling: touch; margin-top: 32px; overflow: scroll; overflow-x: hidden; height: 100% }

</style>
