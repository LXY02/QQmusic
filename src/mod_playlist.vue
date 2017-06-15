<template>
    <article class="mod_playlist js_mod_gedan">
        <header class="mod_tit c_txt1">
            <!--可以自定义标题内容-->
            <h2 class="tit__txt">推荐歌单</h2>
            <!--或上传标题图来显示
            <img src="http://y.gtimg.cn/mediastyle/mobile/event/template_variety_show_v2/extra/tit_3.png" class="tit__img" alt="推荐歌单">-->
        </header>
        <section class="playlist__bd">
            <ul class="qui_equal_col qui_equal_col--3 js_songlist">
                <li v-for="item in arr" class="qui_equal_col__item js_jumpList" data-id="1764225166" disstid="1764225166"><a
                        class="qui_equal_col__box" href="javascript:;">
                    <div class="qui_equal_col__media"><img class="qui_equal_col__img"
                                                           :alt="item.dissname"
                                                           :src="item.logo">
                        <div class="qui_equal_col__count"><i class="qui_equal_col__listen"></i><span
                                class="qui_equal_col__number">9.74万</span></div>
                        <i class="qui_equal_col__play js_playList" :songid="item.disstid"></i></div>
                    <h3 class="qui_equal_col__tit qui_equal_col--row_2 c_txt1">{{item.dissname}}</h3></a></li>
            </ul>
            <a href="javascript:;" class="playlist__more c_txt1 js_moreGedan js_dlg_show" data-dlg="gedan"
               data-tj="moreGedan">更多歌单 &gt;</a>
        </section>
    </article>
</template>

<script>
    import axios from 'axios'
    export default {
        data () {
            return {
                arr: []
            }
        },
        created(){
            var _this = this;
            axios.get('//www.easy-mock.com/mock/593f5d088ac26d795ff1213e/hit-time9/playlist_list').then(function (response) {
                var newArr = response.data.cdlist.slice(0, 3);
                _this.arr = newArr;
            }).catch(function (error) {
                console.log(error);
            });
        }
    }
</script>

<style>
    .mod_playlist {
        margin: 0 10px 32px
    }

    .playlist__bd {
        overflow: hidden
    }

    .playlist__more {
        display: table;
        margin: 0 auto;
        font-size: 12px;
        color: #000;
        opacity: .8
    }

    .popup_history__txt em {
        margin-right: 14px;
        font-size: 18px;
        font-style: normal
    }

    .popup_history__intro p {
        margin: 0 43px;
        padding: 4px 0;
        font-size: 12px;
        color: #000;
        opacity: .8
    }

    .mod_tit {
        margin-bottom: 14px;
        color: #000;
        text-align: center;
        line-height: 1
    }

    .tit__txt {
        font-size: 20px;
        font-weight: 400
    }

    .qui_equal_col {
        margin: 0 -1px;
        overflow: hidden
    }

    .qui_equal_col__item {
        float: left;
        margin-bottom: 15px
    }

    .qui_equal_col__box {
        display: block;
        margin: 0 1px;
        overflow: hidden
    }

    .qui_equal_col__media {
        position: relative;
        overflow: hidden;
        background-repeat: no-repeat;
        background-size: cover
    }

    .qui_equal_col__media::after {
        content: "";
        display: block;
        padding-top: 100%
    }

    .qui_equal_col__img {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        z-index: 1
    }

    .qui_equal_col__play {
        position: absolute;
        bottom: 0;
        right: 0;
        width: 40px;
        height: 40px;
        z-index: 3
    }

    /*.qui_equal_col__play::after {
        content: "";
        position: absolute;
        bottom: 5px;
        right: 5px;
        width: 22px;
        height: 22px;
        background: url(./assets/tubiao.png) no-repeat;
        background-size: 22px
    }
*/
    .qui_equal_col__play.pause::after {
        background-position: 0 -22px
    }

    .qui_equal_col__count {
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
        z-index: 2;
        display: -webkit-box;
        -webkit-box-align: center;
        padding: 5px;
        color: rgba(255, 255, 255, .8);
        background: -webkit-linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, .6))
    }

    .qui_equal_col__count i {
        font-style: italic;
    }

    .qui_equal_col__listen {
        display: block;
        width: 10px;
        height: 9px;
        background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABMAAAARBAMAAADNtor0AAAAIVBMVEUAAAD////////////////////////////////////////PIev5AAAAC3RSTlMAzJkRqnczIruIZqJ6XmUAAABsSURBVAjXY2BgYF/U2LScAQSYAwWBIBjELBEMMzALFCkACjq6gxQ5OjMwcAqBlTFJMjAkCkN0CCYwBAaAmSDaMQHCTHRgaDSAMA0bGASFwGwjQQEGQUEFEFMRzBQAMQWJYSqCtYEpI7BhIAoABhUPtWDPqGoAAAAASUVORK5CYII=) no-repeat;
        background-size: cover
    }

    .qui_equal_col__watch {
        display: block;
        width: 12px;
        height: 8px;
        background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAQBAMAAAD+CqKmAAAAJFBMVEUAAAD///////////////////////////////////////////+0CY3pAAAADHRSTlMAzGaqRLsiEZl3M4jn7qnPAAAAYElEQVQI12PgMhQEgcgCBiBY2KQEAqoGII4FAxiwiTAwODMIQThAulIQwWEzNERwFK0U4RxB6QIER9SBAcERXoDEERRC4ghNNEPisAQaIlmaLIjkHKAeR4RD2RlYkLwAAOvJDltoOHoGAAAAAElFTkSuQmCC) no-repeat;
        background-size: cover
    }

    .qui_equal_col__number {
        display: block;
        margin-top: 2px;
        margin-left: 2px;
        -webkit-transform: scale(.85)
    }

    .qui_equal_col__tit {
        margin: 0 8px;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis

    }

    .qui_equal_col__tit {
        margin-top: 5px;
        font-weight: 400
    }

    .qui_equal_col__desc {
        height: 18px
    }

    .qui_equal_col--no_tit .qui_equal_col__item {
        margin-bottom: 2px
    }

    .qui_equal_col--center {
        text-align: center
    }

    .qui_equal_col--row_2 {
        display: -webkit-box;
        -webkit-box-orient: vertical;
        -webkit-line-clamp: 2;
        height: 36px;
        white-space: normal
    }

    .qui_equal_col--1 .qui_equal_col__item {
        width: 100%
    }

    .qui_equal_col--2 .qui_equal_col__item {
        width: 50%
    }

    .qui_equal_col--3 .qui_equal_col__item {
        width: 33.33333%
    }

    .qui_equal_col--4 .qui_equal_col__item {
        width: 25%
    }

    .qui_equal_col--5 .qui_equal_col__item {
        width: 20%
    }

    .qui_equal_col--2 .qui_equal_col__tit {
        font-size: 14px
    }

    .qui_equal_col--row_2 {
        margin-left: 0
    }

    .qui_equal_col__tit {
        color: #000
    }

    h1, h2, h3, h4, h5, h6 {
        font-size: 100%
    }
</style>