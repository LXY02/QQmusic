<template>
    <article class="mod_rank">
        <header class="mod_tit c_txt1">
            <!--可以自定义标题内容-->
            <h2 class="tit__txt">人气金曲榜</h2>
            <!--或上传标题图来显示
            <img src="http://y.gtimg.cn/mediastyle/mobile/event/template_variety_show_v2/extra/tit_2.png" class="tit__img" alt="节目总榜">-->
        </header>
        <section class="rank__bd">
            <ul class="rank_list" id="id_total_ranklist_cont">
                <li class="rank_list__item js_toprank" data-idx="1">
                    <div class="rank_list__box">
                        <span class="rank_list__bg c_bg2"></span>
                        <span class="rank_list__index c_txt1">1</span>
                        <span class="rank_list__avatar"><img src="./assets/rank.jpg" class="rank_list__avatar_img js_singerimg"></span>
                        <div class="rank_list__bd">
                            <p class="rank_list__txt c_txt1 js_songname">动物世界</p>
                            <p class="rank_list__desc c_txt1 js_singername">薛之谦</p>
                            <p class="rank_list__desc c_txt1 js_votenum">123.0万票</p>
                        </div>
                    </div>
                </li>
                <li class="rank_list__item js_toprank" data-idx="2">
                    <div class="rank_list__box">
                        <span class="rank_list__bg c_bg2"></span>
                        <span class="rank_list__index c_txt1">2</span>
                        <span class="rank_list__avatar"><img src="./assets/rank2.jpg" class="rank_list__avatar_img js_singerimg"></span>
                        <div class="rank_list__bd">
                            <p class="rank_list__txt c_txt1 js_songname">王子公主</p>
                            <p class="rank_list__desc c_txt1 js_singername">薛之谦</p>
                            <p class="rank_list__desc c_txt1 js_votenum">117.8万票</p>
                        </div>
                    </div>
                </li>
                <li class="rank_list__item js_toprank" data-idx="3">
                    <div class="rank_list__box">
                        <span class="rank_list__bg c_bg2"></span>
                        <span class="rank_list__index c_txt1">3</span>
                        <span class="rank_list__avatar"><img src="./assets/rank3.jpg" class="rank_list__avatar_img js_singerimg"></span>
                        <div class="rank_list__bd">
                            <p class="rank_list__txt c_txt1 js_songname">友情卡片</p>
                            <p class="rank_list__desc c_txt1 js_singername">沙宝亮</p>
                            <p class="rank_list__desc c_txt1 js_votenum">110.8万票</p>
                        </div>
                    </div>
                </li>
            </ul>
            <a href="javascript:;" class="rank__more c_txt1 js_show_toplist">完整榜单 &gt;</a>
        </section>
    </article>
</template>

<script>
    export default {
        data () {
            return {}
        }

    }
</script>

<style>
    .mod_rank {
        margin: 0 10px 32px
    }

    .rank_list {
        margin: 0 -4px;
        overflow: hidden;
        display: -webkit-box;
        -webkit-box-align: end
    }

    .rank_list__item {
        position: relative;
        float: left;
        width: 32%;
        overflow: hidden
    }

    .rank_list__box {
        position: relative;
        display: -webkit-box;
        -webkit-box-orient: vertical;
        -webkit-box-align: center;
        -webkit-box-pack: end;
        margin: 0 4px;
        padding: 12px 0 14px;
        border-top: solid 4px #dca84f;
        -webkit-box-sizing: border-box
    }

    .rank_list__bg {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0,0,0,.1);
        opacity: .5
    }

    .rank_list__index {
        position: absolute;
        top: 44px;
        left: 12px;
        z-index: 2;
        font-size: 30px;
        color: #000;
        line-height: 1;
        opacity: .8
    }

    .rank_list__avatar {
        position: relative;
        left: 4px;
        z-index: 1;
        display: block;
        margin-bottom: 12px;
        width: 60px;
        height: 60px
    }

    .rank_list__avatar_img {
        display: block;
        width: 100%;
        height: 100%;
        border-radius: 99px
    }

    .rank_list__bd {
        position: relative;
        z-index: 1;
        width: 70%
    }

    .rank_list__txt {
        font-size: 14px;
        color: #000;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis
    }

    .rank_list__desc {
        font-size: 12px;
        color: #000;
        opacity: .8;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis
    }

    .rank_list__item:first-child {
        left: 32%;
        width: 36%
    }

    .rank_list__item:nth-child(2) {
        left: -36%
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

    .rank__more {
        display: table;
        margin: 10px auto 0;
        font-size: 12px;
        color: #000;
        opacity: .8
    }

</style>