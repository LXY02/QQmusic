<template>
    <section class="mod_hit">
        <svg style="position:absolute;width:0;height:0;overflow:hidden;" xmlns="http://www.w3.org/2000/svg">
            <defs>
                <symbol id="play" viewBox="0 0 54 54">
                    <title>播放</title>
                    <path d="M27,0C12.088,0,0,12.088,0,27c0,14.913,12.088,27,27,27s27-12.088,27-27S41.912,0,27,0z M27,51

			C13.745,51,3,40.256,3,27C3,13.745,13.745,3,27,3s24,10.745,24,24C51,40.256,40.255,51,27,51z M24.604,18.695

			c-0.897-0.896-2.353-0.896-3.25,0v16.61c0.897,0.896,2.353,0.896,3.25,0l11.85-6.106c0.897-0.896,0.897-2.352,0-3.25

			L24.604,18.695z"></path>
                </symbol>
                <symbol id="pause" viewBox="0 0 54 54">
                    <title>暂停</title>
                    <path d="M23,18h-4c-0.553,0-1,0.447-1,1v16c0,0.553,0.447,1,1,1h4c0.553,0,1-0.447,1-1V19

			C24,18.447,23.553,18,23,18z M27,0C12.088,0,0,12.088,0,27c0,14.911,12.088,27,27,27s27-12.089,27-27C54,12.088,41.912,0,27,0z

			 M27,50.563C13.986,50.563,3.438,40.013,3.438,27C3.438,13.986,13.986,3.437,27,3.437S50.563,13.986,50.563,27

			C50.563,40.013,40.014,50.563,27,50.563z M35,18h-4c-0.553,0-1,0.447-1,1v16c0,0.553,0.447,1,1,1h4c0.553,0,1-0.447,1-1V19

			C36,18.447,35.553,18,35,18z"></path>
                </symbol>
                <symbol id="mv" viewBox="0 0 54 54">
                    <title>mv</title>
                    <path d="M39.235,39.328c0,2.208-1.79,4-3.994,4H7.627c-2.208,0-3.994-1.787-3.994-4V14.633c0-2.208,1.79-4,3.994-4

	h27.614c2.208,0,3.994,1.787,3.994,4V39.328z M51.21,16.283l-8.342,5.491v-7.141c0-4.219-3.413-7.633-7.627-7.633H7.627

	C3.416,7,0,10.419,0,14.633v24.695c0,4.219,3.413,7.633,7.627,7.633h27.614c4.21,0,7.627-3.419,7.627-7.633v-7.112l8.301,5.203

	C52.737,38.402,54,37.699,54,35.856V17.784C54,15.938,52.751,15.268,51.21,16.283L51.21,16.283z M10.928,14.265H10.76

	c-1.933,0-3.494,1.563-3.494,3.49c0,1.924,1.564,3.49,3.494,3.49h0.168c1.933,0,3.494-1.563,3.494-3.49

	C14.422,15.832,12.857,14.265,10.928,14.265"></path>
                </symbol>
                <symbol id="download" viewBox="0 0 54 54">
                    <title>下载</title>
                    <path d="M26.983,50.403H10.732c-2.198,0-4.016-1.871-4.016-4.211H2.577c0,4.568,3.634,8.308,8.155,8.308H27.5h16.768

	c4.521,0,8.155-3.74,8.155-8.308h-4.139c0,2.34-1.818,4.211-4.016,4.211H26.983z M26.268,38.572h2.937L7.066,16.433L4.129,19.37

	l22.139,22.139l1.468,1.469l1.469-1.469L51.514,19.2l-2.937-2.937L26.268,38.572z M25.423,4.035v31.129

	c0,1.147,0.93,2.077,2.077,2.077s2.077-0.93,2.077-2.077V4.035V0.5h-4.154V4.035z"></path>
                </symbol>
                <symbol id="share" viewBox="0 0 54 54">
                    <title>分享</title>
                    <path d="M49.18,8.015L19.093,38.178l-3.059-3.051L46.265,4.82H34.06V0.5H53.5v19.44h-4.32V8.015

	z M49.18,29.209v14.498c0,3.577-2.895,6.473-6.477,6.473H10.297c-3.577,0-6.477-2.903-6.477-6.49V11.31

	c0-3.585,2.904-6.49,6.487-6.49h13.581V0.5H10.307C4.338,0.5-0.5,5.34-0.5,11.31v32.38c0,5.971,4.832,10.81,10.797,10.81h32.407

	c5.967,0,10.797-4.83,10.797-10.793V29.209H49.18z"></path>
                </symbol>
            </defs>
        </svg>
        <ul class="hit_list hit_list--special js_song_list" data-songids="202715897,202715902,202715903,202715900,202715901,202715898,202715899">
            <li class="hit_list__item c_bor1 js_curlist_song js_playsongcon" :data-id="item.Ftrack_id" :data-mid="item.Ftrack_mid" v-for="(item,index) in arr">
            <span class="hit_list__index c_txt3 js_order_index">{{index+1}}</span>
            <a class="hit_list__avatar">
                <img :src="item.Fh5_photo_url + '?max_age=2592000'" class="hit_list__avatar_img" alt="">
            </a>
            <div class="hit_list__bd">
                <div class="hit_list__info">
                    <div class="hit_list__txt">
                        <h3 class="hit_list__tit c_txt1">{{item.Ftrack_name}}</h3>
                        <p class="hit_list__desc c_txt1">{{item.Fsinger_name}}</p>
                    </div>
                    <div class="hit_list__other js_hit_div">
                        <a href="javascript:;" class="hit_list__btn c_txt1 js_hitbtn" data-voted="0" :data-id="item.Ftrack_id" data-mid="003Y6iQH23fbk8" data-no="509" @click="item.vote++">投票</a>
                        <span class="hit_list__count c_txt1 js_vote_num" :data-id="item.Ftrack_id" data-num="149583">{{item.vote}}票</span>
                    </div>

                </div>
                <div class="hit_list__control">
                    <a href="javascript:;" class="hit_list__control_item c_txt1 js_playsong" title="播放" :data-id="item.Ftrack_id" @click="onClick(item)">
                        <svg class="icon_svg c_txt1 icon_play_r">
                            <use xmlns:xlink="http://www.w3.org/1999/xlink" :xlink:href="item.isplaying ? '#pause' : '#play'"></use>
                        </svg>
                    </a>

                    <a href="javascript:;" class="hit_list__control_item c_txt1 js_downsong" title="下载" :data-id="item.Ftrack_id">
                        <svg class="icon_svg c_txt1">
                            <use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#download"></use>
                        </svg>
                    </a>
                    <a href="javascript:;" class="hit_list__control_item c_txt1 js_share" title="分享" data-title="一样的月光-金志文" :data-songid="item.Ftrack_id" data-desc="一样的月光">
                        <svg class="icon_svg c_txt1">
                            <use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#share"></use>
                        </svg>
                    </a>
                </div>
            </div>
        </li>
        </ul>
        <div class="hit__ft">
            <a href="javascript:;" class="hit__more c_txt1 js_dlg_show" data-dlg="toprule" data-tj="showhotrule">打榜规则 &gt;</a>
            <a href="javascript:;" class="hit__more c_txt1 js_showcalendar">往期回顾 &gt;</a>
        </div>
    </section>
</template>
<script>

    import axios from 'axios';
    export default {
        data () {
            return {
                arr:[]
            }
        },
        methods:{
            onClick:function(item){
                this.arr.forEach(function(curr){
                    if(item == curr){
                        curr.isplaying = !curr.isplaying
                    }else{
                        curr.isplaying= false;
                    }
                });
                this.$emit('curr.Ftrack_mid')
                console.log(item.Ftrack_mid);
            }
        },
        created(){
            var _this = this;
            axios.get('https://www.easy-mock.com/mock/593f5d088ac26d795ff1213e/hit-time9/hit_list',{
                params:{
                    jsonp_params_name:'callback'
                }
            })
                    .then(function(response){
                        response.data.songs.sort(function(a,b){
                            return b.vote - a.vote
                        })
                        response.data.songs.forEach(function(item){
                            item.isplaying = false;
                        })
                        _this.arr = response.data.songs;

                    })
                    .catch(function(error){
//                        console.log(error);
                    })
        }
    }
</script>

<style>
    .mod_hit {
        margin: 0 10px 32px
    }
    .hit__ft {
        margin-top: 10px;
        display: -webkit-box;
        -webkit-box-align: center;
        -webkit-box-pack: center
    }

    .hit__more {
        display: block;
        margin: 0 24px;
        font-size: 12px;
        color: #000;
        opacity: .8
    }

    .hit_list {
        margin: -1px 0
    }

    .hit_list__item {
        position: relative;
        display: -webkit-box;
        -webkit-box-align: stretch;
        padding: 1px 0
    }

    .hit_list__item::after {
        content: "";
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
        height: 0;
        z-index: 1;
        -webkit-box-sizing: border-box;
        pointer-events: none;
        border-style: solid;
        border-width: 0 0 1px 0;
        border-color: currentColor;
        display: none
    }

    .hit_list__index {
        display: -webkit-box;
        -webkit-box-align: center;
        width: 22px;
        font-size: 16px;
        color: #000
    }

    .hit_list__avatar {
        position: relative;
        display: block;
        margin-right: 8px;
        width: 60px;
        height: 60px
    }

    .hit_list__avatar_img {
        display: block;
        width: 100%;
        height: 100%
    }

    .hit_list__bd {
        position: relative;
        -webkit-box-flex: 1;
        display: -webkit-box;
        -webkit-box-pack: center;
        -webkit-box-orient: vertical
    }

    .hit_list__bd::after {
        content: "";
        position: absolute;
        bottom: 0;
        left: 0;
        right: -10px;
        height: 0;
        z-index: 1;
        -webkit-box-sizing: border-box;
        pointer-events: none;
        border-style: solid;
        border-width: 0 0 1px 0;
    }

    .hit_list__info {
        display: -webkit-box;
        -webkit-box-align: center
    }

    .hit_list__txt {
        margin-right: 4px;
        -webkit-box-flex: 1
    }

    .hit_list__tit {
        font-size: 16px;
        color: #000;
        font-weight: 400;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis
    }

    .hit_list__desc {
        font-size: 12px;
        color: #000;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
        opacity: .8
    }

    .hit_list__btn {
        display: block;
        width: 58px;
        height: 22px;
        line-height: 20px;
        font-size: 13px;
        color: #000;
        text-align: center;
        border: solid 1px currentColor;
        border-radius: 22px;
        -webkit-box-sizing: border-box;
        background-color: transparent
    }

    .hit_list__btn.disable {
        opacity: .3
    }

    .hit_list__count {
        display: block;
        margin-top: 2px;
        font-size: 12px;
        color: #000;
        text-align: center;
        opacity: .8
    }

    .hit_list__control {
        display: -webkit-box;
        -webkit-box-align: center
    }

    .hit_list__control_item {
        position: relative;
        display: block;
        margin-right: 2px;
        width: 40px;
        height: 26px;
        color: #000;
        opacity: .3
    }

    .hit_list__control_item .icon_svg {
        position: absolute;
        top: 9px;
        left: 0;
        width: 18px;
        height: 18px;
        fill: currentColor
    }

    .hit_list__control_item:last-child .icon_svg {
        top: 10px;
        width: 16px;
        height: 16px
    }

    .hit_list--special .hit_list__item {
        position: relative;
        padding: 6px 0
    }

    .hit_list--special .hit_list__item::after {
        display: block
    }

    .hit_list--special .hit_list__index {
        position: absolute;
        top: 0;
        left: 0;
        z-index: 1;
        padding-top: 12px;
        width: auto;
        height: 100%;
        font-size: 25px
    }

    .hit_list--special .hit_list__item:first-child .hit_list__index {
        margin: 0 0 0 -8px;
        font-size: 50px
    }

    .hit_list--special .hit_list__avatar {
        margin-right: 16px;
        width: auto;
        height: auto;
        zoom:.5}

    .hit_list--special .hit_list__bd::after {
        display: none
    }

    @media screen and (-webkit-min-device-pixel-ratio: 2) {
        .hit_list__bd::after,.hit_list__item::after {
            -webkit-transform:scaleY(.5)
        }
    }
</style>