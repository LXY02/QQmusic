<template>
    <section class="mod_top">
        <h1 class="hide">金曲捞第九期 第9期</h1>
        <span class="top__bg"><img src="./assets/headerbg.jpg" class="top__bg_img js_head_pic" alt="金曲捞第九期 第9期"></span>
        <a href="javascript:;" class="top__btn js_playallsong" title="播放全部" @click="onPlayAll">
            <img src="./assets/bofangbtn.png" class="top__btn_img" alt="播放全部">
        </a>
    </section>
</template>

<script>
    import { bus } from './bus.js'
    export default {
        data () {
            return {}
        },
        methods: {
            onPlayAll: function () {
                bus.$emit('playAll');
            }
        }
    }
</script>

<style>
    .mod_top {
        position: relative;
        margin-bottom: 34px;
        padding-top: 80%
    }

    .top__bg {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        padding-top: 80%;
        overflow: hidden
    }

    .top__bg_img {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%
    }

    .top__btn {
        position: absolute;
        bottom: 0;
        left: 50%;
        -webkit-transform: translate3d(-50%,50%,0) scale(.5)
    }

    .top__btn_img {
        display: block;
    }

</style>
