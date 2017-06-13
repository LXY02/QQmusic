<template>
    <section class="mod_hit">
        <ul class="hit_list hit_list--special js_song_list" data-songids="202715897,202715902,202715903,202715900,202715901,202715898,202715899">
            <li class="hit_list__item c_bor1 js_curlist_song js_playsongcon" data-id="202715898" data-mid="003Y6iQH23fbk8">
            <span class="hit_list__index c_txt3 js_order_index">1</span>
            <a class="hit_list__avatar">
                <img src="//y.gtimg.cn/music/common/upload/t_tv_songShow_songs/108416.jpg?max_age=2592000" class="hit_list__avatar_img" alt="">
            </a>
            <div class="hit_list__bd">
                <div class="hit_list__info">
                    <div class="hit_list__txt">
                        <h3 class="hit_list__tit c_txt1">一样的月光</h3>
                        <p class="hit_list__desc c_txt1">金志文</p>
                    </div>

                    <div class="hit_list__other js_hit_div">
                        <a href="javascript:;" class="hit_list__btn c_txt1 js_hitbtn" data-voted="0" data-id="202715898" data-mid="003Y6iQH23fbk8" data-no="509">投票</a>
                        <span class="hit_list__count c_txt1 js_vote_num" data-id="202715898" data-num="149583">149583票</span>
                    </div>

                </div>
                <div class="hit_list__control">
                    <a href="javascript:;" class="hit_list__control_item c_txt1 js_playsong" title="播放" data-id="202715898">
                        <svg class="icon_svg c_txt1 icon_play_r">
                            <use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#play"></use>
                        </svg>
                    </a>

                    <a href="javascript:;" class="hit_list__control_item c_txt1 js_downsong" title="下载" data-id="202715898">
                        <svg class="icon_svg c_txt1">
                            <use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#download"></use>
                        </svg>
                    </a>
                    <a href="javascript:;" class="hit_list__control_item c_txt1 js_share" title="分享" data-title="一样的月光-金志文" data-songid="202715898" data-desc="一样的月光">
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
            return {}
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