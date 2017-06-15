<template>
    <div class="comment_type js_newpin_cont">
        <div class="comment_type__hd c_bor1"><h2 class="comment_type__tit c_txt1">{{ title }}</h2></div>
        <slot></slot>
        <p class="comment__null c_txt1 c_txt2 js_newpin_nodata" style="display: none;">还没有人评论, 来抢沙发吧</p>
        <ul class="comment_list js_newping">
            <li v-for="(item, index) in arr" class="comment_list__item c_bor1 js_repingContent">
                <div class="comment_list__avatar">
                    <a href="javascript:;">
                    <img src="//y.gtimg.cn/mediastyle/music_v13/img/avatar_mask.png?max_age=2592000" class="pic_mask">
                    <img :src="item.avatarurl">
                    </a>
                </div>
                <h4 class="comment_list__name"><a href="javascript:;" class="c_txt1 c_txt2">{{item.nick}}</a></h4>
                <div class="comment_opt">
                    <div class="comment_opt__item">
                        <a data-id="album_2104892_3349177274_1497020743" href="javascript:;" title="点赞" class="comment_opt__zan c_txt1 js_cmt_praise">
                        <svg class="comment__opt_icon">
                            <use xmlns:xlink="//www.w3.org/1999/xlink" xlink:href="#icon_praise"></use>
                        </svg>
                        <span class="comment_opt__txt c_txt1 c_txt2">{{item.praisenum}}</span>
                        </a>
                        <a href="javascript:;" title="回复" class="comment_opt__feedback c_txt1 js_cmt_reply">
                        <svg class="comment__opt_icon">
                            <use xmlns:xlink="//www.w3.org/1999/xlink" xlink:href="#icon_comment"></use>
                        </svg>
                        </a>
                    </div>
                </div>
                <p class="comment_list__date c_txt1 c_txt2" v-if="index >=5">6月9日 23:05</p>
                <p class="comment_list__text c_txt1">
                    {{item.rootcommentcontent}}
                </p>
                <div class="comment_add js_cmt_reply_input" style="display: none;">
                    <div class="comment_add__input_box c_bg2">
                        <input type="text" placeholder="在此写下你的回复吧" class="comment_add__input c_txt1 js_reply_content">
                    </div>
                    <a href="JavaScript:;" data-id="album_2104892_3349177274_1497020743" data-user="我的心，你的世界" class="comment_add__btn c_txt3 js_reply_send">发布</a>
                </div>
            </li>
        </ul>
        <!--<div class="comment_loading"><a href="javascript:;" class="comment_loading__txt c_txt1 c_txt2 js_newping_more">查看更多</a>-->
        <!--</div>-->
    </div>
</template>
<script>
    export default {
        props: ['title','arr'],
        data () {
            return {}
        }
    }
</script>

<style>
</style>