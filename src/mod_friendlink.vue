<template>
    <article class="mod_friendlink js_exclusive">
        <header class="mod_tit c_txt1">
            <!--可以自定义标题内容-->
            <h2 class="tit__txt">独家综艺</h2>
            <!--或上传标题图来显示
            <img src="http://y.gtimg.cn/mediastyle/mobile/event/template_variety_show_v2/extra/tit_4.png" class="tit__img" alt="独家综艺">-->
        </header>
        <section class="friendLink__bd">
            <ul class="friendLink_list">
                <li class="friendLink_list__item js_topic_click" data-id="98">
                    <img src="./assets/friendlink1.png"
                         class="friendLink_list__img" alt="歌手总决赛，歌王之战！">
                    <h3 class="friendLink_list__txt c_txt1">歌手总决赛，歌王之战！</h3>
                    <p class="friendLink_list__desc c_txt1"></p>
                </li>
                <li class="friendLink_list__item js_topic_click" data-id="93">
                    <img src="./assets/friendlist2.png"
                         class="friendLink_list__img" alt="萌娃唱歌，天籁童声给你好听！">
                    <h3 class="friendLink_list__txt c_txt1">萌娃唱歌，天籁童声给你好听！</h3>
                    <p class="friendLink_list__desc c_txt1"></p>
                </li>
                <li class="friendLink_list__item js_topic_click" data-id="92" data-href="http://url.cn/499gbow">
                    <img src="./assets/friendlist3.png"
                         class="friendLink_list__img" alt="殿堂级歌手，唱响情怀老歌">
                    <h3 class="friendLink_list__txt c_txt1">殿堂级歌手，唱响情怀老歌</h3>
                    <p class="friendLink_list__desc c_txt1"></p>
                </li>
            </ul>
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
    .mod_friendlink {
        margin: 0 10px 32px
    }
    .c_txt1 {
        color: #2b2322;
    }
    .mod_tit {
        margin-bottom: 14px;
        color: #000;
        text-align: center;
        line-height: 1;
    }
    .tit__txt {
        font-size: 20px;
        font-weight: 400
    }
    .friendLink_list {
        margin: 0 -8px;
        overflow: hidden
    }

    .friendLink_list__item {
        float: left;
        padding: 0 8px;
        width: 33.33%;
        -webkit-box-sizing: border-box
    }
    li {
        list-style: none;
    }


    .friendLink_list__img {
        display: block;
        margin-bottom: 4px;
        width: 100%
    }

    .friendLink_list__txt {
        font-size: 14px;
        color: #000;
        font-weight: 400;
        text-align: center
    }

    .friendLink_list__desc {
        font-size: 12px;
        color: #000;
        text-align: center;
        opacity: .7
    }

</style>