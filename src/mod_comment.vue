<template>
    <div class="mod_comment">
        <h2 class="comment__tit c_txt1">精彩评论</h2>
        <div class="comment__bd">
            <newpin_cont :arr="hotArr" title="热评"></newpin_cont>
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
            var _this=this
            axios.get('https://www.easy-mock.com/mock/593f5d088ac26d795ff1213e/hit-time9/comment')
                .then(function (response) {
                    _this.hotArr=response.data.comment.splice(0,5);
                    _this.newArr=response.data.comment;
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
    /*@charset "utf-8";html {*/
    /*-webkit-text-size-adjust: 100%;*/
    /*-webkit-tap-highlight-color: rgba(0,0,0,0)*/
    /*}*/

    a, img {
        -webkit-touch-callout: none
    }

    body, dd, dl, form, h1, h2, h3, h4, h5, h6, input, ol, p, td, textarea, th, ul {
        margin: 0;
        padding: 0
    }

    h1, h2, h3, h4, h5, h6 {
        font-size: 100%
    }

    li {
        list-style: none
    }

    table {
        border-collapse: collapse;
        border-spacing: 0
    }

    button:focus, input:focus, textarea:focus {
        outline: 0
    }

    a, a:hover {
        text-decoration: none
    }

    button, input, select, textarea {
        font-family: inherit;
        font-size: 100%
    }

    body {
        font: 12px/1.5 FZLTXIHJW--GB1-0, "hiragino sans gb", "Helvetica Neue", Helvetica, STHeiTi, Arial, sans-serif
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

    @media screen and (-webkit-min-device-pixel-ratio: 2) {
        .hit_list__bd::after, .hit_list__item::after {
            -webkit-transform: scaleY(.5)
        }
    }

    .vote_list__play .icon_svg {
        position: absolute;
        top: 6px;
        right: 0;
        width: 20px;
        height: 20px;
        fill: currentColor;
        opacity: .3
    }

    .rank_list__item:nth-child(2) .rank_list__box {
        border-top-color: #93938d
    }

    .rank_list__item:nth-child(3) .rank_list__box {
        border-top-color: #a18a6e
    }

    .rank_list__item:first-child .rank_list__index {
        top: 50px;
        font-size: 40px
    }

    .rank_list__item:first-child .rank_list__avatar {
        left: 8px;
        width: 75px;
        height: 75px
    }

    .qui_equal_col--no_tit .qui_equal_col__item {
        margin-bottom: 2px
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
        border-bottom: 1px solid #ededed;
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
        color: #31c27c
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
        border: 1px solid #ededed
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
        fill: #31c27c;
        /*background: url(img/comment_sprite.png) no-repeat -20px -20px\0*/
    }

    .comment_opt__feedback .comment__opt_icon {
        margin-right: 0;
        /*background: url(img/comment_sprite.png) no-repeat -40px -20px\0*/
    }

    .comment_type__hd {
        padding-bottom: 14px;
        overflow: hidden;
        border-bottom: 1px solid #ededed
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
        background-color: #fff
    }

    .comment__intro_line {
        position: absolute;
        left: 50%;
        margin-left: -150px;
        top: 50%;
        width: 300px;
        height: 1px;
        background-color: #ededed;
        overflow: hidden
    }

    .comment__intro_link {
        position: relative;
        z-index: 10;
        display: inline-block;
        padding: 0 10px 0 2px;
        color: #000;
        background-color: #fff
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
        border: 1px solid #31c27c;
        border-color: currentColor;
        color: #31c27c
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

    .mod_page_nav__item {
        opacity: .5
    }

    .mod_page_nav strong, .mod_page_nav__item {
        font-size: 16px;
        font-weight: 400;
        display: inline-block;
        line-height: 50px;
        margin: 0 5px;
        padding: 0 21px;
        box-sizing: border-box;
        min-width: 24px
    }

    .mod_page_nav__item--current {
        opacity: 1;
        color: #31c27c;
        border: solid 1px #31c27c;
        border-color: currentColor
    }

    .mod_page_nav__next, .mod_page_nav__prev {
        font-size: 0
    }

    .mod_page_nav__next_icon, .mod_page_nav__prev_icon {
        display: inline-block;
        width: 6px;
        height: 11px;
        /*background-image: url(img/comment_sprite.png);*/
        background-repeat: no-repeat
    }

    .mod_page_nav__prev_icon {
        background-position: -10px 0
    }

    .mod_page_nav__next_icon {
        background-position: 0 0
    }

    .mod_page_nav__prev:hover .mod_page_nav__prev_icon {
        background-position: -30px 0
    }

    .mod_page_nav__next:hover .mod_page_nav__next_icon {
        background-position: -20px 0
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
            border-bottom: solid 1px #e5e5e5
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
            background-color: #e5e5e5
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
            color: #31c27c;
            text-align: center;
            border-radius: 2px;
            -webkit-box-sizing: border-box;
            border: solid 1px #31c27c;
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

        .mod_page_nav {
            display: none
        }

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

    .mod_lead_flow {
        display: none
    }

    @media screen and (max-width: 738px) {
        .mod_lead_flow {
            position: relative;
            z-index: 100;
            display: block;
            height: 60px
        }

        .lead_flow__cont {
            position: fixed;
            bottom: 0;
            left: 0;
            z-index: 100;
            padding: 0 16px;
            width: 100%;
            height: 60px;
            -webkit-box-sizing: border-box;
            display: -webkit-box;
            -webkit-box-align: center;
            background-color: rgba(0, 0, 0, .8)
        }

        .lead_flow__logo {
            display: block;
            margin-right: 10px;
            width: 40px;
            height: 40px;
            text-indent: -999em;
            background-image: url(//y.gtimg.cn/mediastyle/mod/operation/import/img/logo_qqmusic.png?max_age=2592000);
            background-size: 100%;
            background-repeat: no-repeat
        }

        .lead_flow__bd {
            -webkit-box-flex: 1
        }

        .lead_flow__tit {
            font-size: 18px;
            color: #fff;
            font-weight: 400
        }

        .lead_flow__txt {
            font-size: 12px;
            color: #fff
        }

        .lead_flow__btn {
            display: block;
            padding: 0 25px;
            min-width: 80px;
            height: 28px;
            line-height: 26px;
            font-size: 14px;
            color: #fff;
            text-align: center;
            border: solid 1px #fff;
            -webkit-box-sizing: border-box;
            border-radius: 28px;
            background-color: transparent
        }
    }

    .qui_dialog__box {
        border-top: solid 4px currentColor
    }

    .qui_dialog__para {
        color: #777
    }

    .qui_equal_col--row_2 {
        margin-left: 0
    }

    .qui_equal_col__tit {
        color: #000
    }

    .qui_equal_col__play::after {
        content: "";
        position: absolute;
        bottom: 5px;
        right: 5px;
        width: 22px;
        height: 22px;
        /*background: url(slice/2x/icon_play.png) no-repeat;*/
        background-size: 100%
    }

    .qui_equal_col__play.pause::after {
        /*background-image: url(sprite/index@2x.png?max_age=2592000&v=4e14150394a39c6e27062033f5bb29aa);*/
        background-position: 0 0;
        background-size: 45px !important;
        background-position: 0
    }

    .mod_playlist {
        margin: 0 10px 32px
    }

    playlist__bd {
        overflow: hidden
    }

    .playlist__more {
        display: table;
        margin: 0 auto;
        font-size: 12px;
        color: #000;
        opacity: .8
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

    .popup_history {
        position: fixed;
        bottom: -100%;
        left: 0;
        z-index: 100;
        width: 100%;
        height: 100%;
        overflow: hidden;
        background-color: #fff
    }

    .popup_history--show {
        bottom: 0;
        -webkit-transition: all .3s linear
    }

    .popup_history__close {
        position: absolute;
        top: 0;
        right: 0;
        width: 40px;
        height: 40px;
        text-indent: -999em
    }

    .popup_history__close::after, .popup_history__close::before {
        content: "";
        position: absolute;
        top: 19px;
        left: 4px;
        width: 32px;
        height: 2px;
        background-color: currentColor;
        opacity: .5
    }

    .popup_history__close::before {
        -webkit-transform: rotate(45deg)
    }

    .popup_history__close::after {
        -webkit-transform: rotate(-45deg)
    }

    .popup_history__cont {
        margin-top: 32px;
        overflow: hidden
    }

    .popup_history__tit {
        margin-bottom: -4px;
        font-size: 16px;
        color: #31c27c;
        font-weight: 400
    }

    .popup_history__grid {
        margin-bottom: 14px;
        padding-left: 52px
    }

    .history_list__item {
        position: relative;
        padding: 8px 16px 8px 0
    }

    .history_list__item::after {
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
        border-color: currentColor
    }

    .history_list__box {
        display: -webkit-box;
        -webkit-box-align: center
    }

    .popup_history__bd {
        -webkit-box-flex: 1
    }

    .popup_history__txt {
        font-size: 14px;
        color: #000
    }

    .popup_history__txt em {
        margin-right: 14px;
        font-size: 18px;
        font-style: normal
    }

    .popup_history__desc {
        font-size: 14px;
        color: #000;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
        opacity: .8
    }

    .popup_history__arr {
        display: block;
        width: 8px;
        height: 8px;
        border-top: solid 1px currentColor;
        border-right: solid 1px currentColor;
        -webkit-transform: rotate(45deg);
        -webkit-box-sizing: border-box;
        opacity: .3
    }

    .popup_history__intro {
        position: relative;
        margin: 36px 10px 28px
    }

    .popup_history__intro p {
        margin: 0 43px;
        padding: 4px 0;
        font-size: 12px;
        color: #000;
        opacity: .8
    }

    .popup_history__intro::after, .popup_history__intro::before {
        content: "";
        position: absolute;
        top: 0;
        width: 30px;
        height: 100%;
        border: solid 8px #000;
        border-color: currentColor;
        -webkit-box-sizing: border-box;
        opacity: .05;
        background-color: transparent
    }

    .popup_history__intro::before {
        left: 0;
        border-right: none
    }

    .popup_history__intro::after {
        right: 0;
        border-left: none
    }

    @media screen and (-webkit-min-device-pixel-ratio: 2) {
        .history_list__item::after {
            -webkit-transform: scaleY(.5)
        }
    }


</style>