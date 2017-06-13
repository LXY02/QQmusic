<template>
    <article class="mod_vote c_txt1">
        <header class="mod_tit c_txt1">
            <h2 class="tit__txt">《金曲捞》开场曲由你定！</h2>
            <p class="tit__desc">投票截止时间：5月28日24点</p>
        </header>
        <nav class="vote__nav c_txt1">
            <div class="vote__nav_box js_vote_navbox" :style="styleObject">
                <a href="javascript:;" class="vote__nav_item js_vote_nav c_txt3" :class="{cur: item.cur}" data-endtime="2017-05-28 23:50:00" data-end="1" data-index="0" data-voteset="94" v-for="(item,index) in dataArr" @click="clickA(item,index)">{{item.Fvote_title}}</a>
            </div>
        </nav>
        <section class="vote__bd js_vote_wrap">
            <div class="vote__bd_box js_vote_wrapbox cur" data-index="0" data-voteset="94" style="transform: translateX(0%);">
                <transition-group tag="ul" name="flip-list" class="vote_list js_vote_list" data-voteset="94">
                    <li class="js_vote_item vote_list__item vote_list__count--top c_txt3" data-id="94001" data-voteset="94" v-for="item in currArr" :key="item.randomNum">
                        <a href="javascript:;" class="vote_list__check c_txt1 js_vote_sel " data-id="94001" data-voteset="94" style="display: none;"></a>
                        <span class="vote_list__txt c_txt1">{{item.title}}</span>
                        <a href="javasript:;" class="vote_list__play c_txt1 js_playsong_btn" title="播放" data-id="133020">
                            <svg class="icon_svg c_txt1 icon_play_r">
                                <use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#play"></use>
                            </svg>
                        </a>
                        <span class="vote_list__count vote_list__count--top c_txt3">{{item.randomNum}}票</span>
                    </li>
                </transition-group>
                <transition name="activityStatement">
                    <a href="javascript:;" class="vote__btn c_txt1 disable" data-voteset="94">已结束</a>
                </transition>
            </div>
        </section>
    </article>
</template>

<script>
    import axios from 'axios';
    export default {
        data () {
            return {
                dataArr: [],  //用来存放ajax请求到的数据里的vote数据
                currArr: [],  //用来存放当前点击页面歌曲排行的信息
                styleObject: {}  //用来存放导航条点击会移动相应位置的css样式
            }
        },
        created() {
            var _this = this;
            axios.get('https://www.easy-mock.com/mock/593f5d088ac26d795ff1213e/hit-time9/vote_list')
                .then(function (response) {
                    var dataVote = response.data.vote;
                    for(var i in dataVote){
                        dataVote[i].cur = false;  //用来判断是否是当前页面
                        for(var j in dataVote[i]['Fvote_set']) {
                            dataVote[i]['Fvote_set'][j].randomNum = parseInt(Math.random()*50000);//随机一个投票数量
                        }
                        dataVote[i]['Fvote_set'].sort(function (a,b) {   //做升序排列
                            return b.randomNum - a.randomNum;
                        });
                        _this.dataArr.push(dataVote[i]);
                    }
                    _this.dataArr.reverse();
                    _this.dataArr[0].cur = true; //初始第一项为选中项
                    _this.currArr = _this.dataArr[0]['Fvote_set'].slice(0);
                })
                .catch(function (error) {
                    console.log(error);
                });
        },
        methods: {
            clickA: function (item,index) {
                var _this = this;
                for(var i in _this.dataArr){
                    _this.dataArr[i].cur = false; //将之前的选中样式去掉
                }
                item.cur = true;
                _this.currArr = item['Fvote_set'].slice(0);
                _this.styleObject = {
                    transform: 'translateX('+index*(-5)+'%)'
                }
            }
        }
    }
</script>

<style>
    .c_txt1 {
        color: #2b2322;
    }
    .mod_vote {
        position: relative;
        margin: 0 10px 36px;
    }
    .mod_vote::after, .mod_vote::before {
        content: "";
        position: absolute;
        top: 0;
        width: 41px;
        height: 100%;
        border: solid 8px #000;
        border-color: currentColor;
        -webkit-box-sizing: border-box;
        opacity: .05;
        background-color: transparent;
    }
    .mod_vote::before {
        left: 0;
        border-right: none;
    }
    .mod_vote::after {
        right: 0;
        border-left: none;
    }
    .mod_tit {
        margin-bottom: 14px;
        color: #000;
        text-align: center;
        line-height: 1;
    }
    .tit__txt {
        font-size: 20px;
        font-weight: 400;
    }
    .tit__desc {
        margin-top: 6px;
        font-size: 16px;
    }
    .vote__nav {
        position: relative;
        margin: 0 32px 18px;
        overflow: hidden;
    }
    .vote__nav::after {
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
        opacity: .5;
    }
    .vote__nav_box {
        display: -webkit-box;
        -webkit-box-align: center;
    }
    .vote__nav_item.cur {
        opacity: 1;
    }
    .vote__nav_item {
        position: relative;
        display: block;
        padding: 0 0 3px;
        width: 23%;
        font-size: 14px;
        color: #000;
        text-align: center;
        -webkit-box-sizing: border-box;
        opacity: .8;
    }
    .vote__nav_item.cur::after {
        display: block;
    }
    .vote__nav_item::after {
        content: "";
        position: absolute;
        bottom: 0;
        left: 50%;
        margin-left: -4px;
        width: 0;
        height: 0;
        border-style: solid;
        border-width: 4px;
        border-color: transparent transparent currentColor transparent;
        display: none;
    }
    .vote__bd {
        margin: 0 36px;
        display: -webkit-box;
        overflow: hidden;
    }
    .vote__bd_box {
        display: block;
        width: 100%;
        -webkit-transition: all .3s linear;
    }
    .vote_list {
        overflow: hidden;
    }
    .vote_list__item {
        display: -webkit-box;
        -webkit-box-align: center;
        width: 100%;
    }
    li {
        list-style: none;
    }
    .vote_list__check {
        position: relative;
        display: block;
        width: 24px;
        height: 32px;
        color: #000;
        opacity: .7;
    }
    .vote_list__check::before {
        content: "";
        position: absolute;
        top: 8px;
        width: 14px;
        height: 14px;
        border: solid 1px currentColor;
        border-radius: 2px;
        background-color: transparent;
    }
    a, a:hover {
        text-decoration: none;
    }
    .vote_list__txt {
        display: block;
        -webkit-box-flex: 1;
        font-size: 14px;
        color: #000;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
    }
    .vote_list__play {
        position: relative;
        display: block;
        width: 40px;
        height: 32px;
        color: #000;
    }
    .vote_list__play .icon_svg {
        position: absolute;
        top: 6px;
        right: 0;
        width: 20px;
        height: 20px;
        fill: currentColor;
        opacity: .3;
    }

    .vote_list__count {
        display: block;
        margin-left: 12px;
        width: 60px;
        font-size: 12px;
        color: #000;
    }
    .vote__btn.disable {
        opacity: .4;
    }
    .vote__btn {
        display: table;
        margin: 14px auto 0;
        padding: 0 10px;
        min-width: 114px;
        height: 30px;
        line-height: 28px;
        font-size: 16px;
        color: #000;
        text-align: center;
        border: solid 1px currentColor;
        border-radius: 30px;
        -webkit-box-sizing: border-box;
        background-color: transparent;
    }

    /*过渡效果*/
    .flip-list-enter-active {
        transition: all .8s .4s ease-out;
    }
    .flip-list-leave-active {
        transition: all .5s ease-in;
    }
    .flip-list-enter {
        opacity: 0;
        transform: translateX(20%);
    }
    .flip-list-leave-active {
        opacity: 0;
        transform: translateX(-20%);
    }
</style>
