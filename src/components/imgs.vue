<template>
    <div style="float:left;display:inline; width:581px; height:407px; ">
        <div class="yx-rotaion">
            <ul class="rotaion_list">
                <li style="position: absolute; left: 0px; top: 0px; display: none;">
                    <a href="/read/1" target="_blank">
                        <img src="http://115.238.154.42:8083/UploadFiles/2019416141850284.jpg" alt="陶诚出席扫黑除恶宣传文艺小分队基层行活动分割的高大上嘎嘎噶三国杀噶是的噶噶搭嘎" style="width:581px;height:407px;">
                    </a>
                </li>
                <li style="position: absolute; left: 0px; top: 0px; display: none;">
                    <a href="/read/2" target="_blank"><img src="http://115.238.154.42:8083/UploadFiles/201941215232482.jpg" alt="王晴宇同志出席扫黑除恶宣传文艺小分队首场演出" style="width:581px;height:407px;"></a>
                </li>
                <li style="position: absolute; left: 0px; top: 0px; display: none;">
                    <a href="/read/3" target="_blank"><img src="http://115.238.154.42:8083/UploadFiles/20194392023174.jpg" alt="宁波公安警务公开工作入围“中国警务透明度”前十" style="width:581px;height:407px;"></a>
                </li>
                <li style="position: absolute; left: 0px; top: 0px; display: none;">
                    <a href="/read/4" target="_blank"><img src="http://115.238.154.42:8083/UploadFiles/201931110551712.jpg" alt="徐益平同志赴杭州研究宁波公安英烈纪念墙有关工作" style="width:581px;height:407px;"></a>
                </li>
                <li style="position: absolute; left: 0px; top: 0px; display: none;">
                    <a href="/read/5" target="_blank"><img src="http://115.238.154.42:8083/UploadFiles/20193717224480.jpg" alt="市局公共关系处赴余姚市局开展“大巡访、三服务”活动" style="width:581px;height:407px;"></a>
                </li>
            </ul>
        </div>
    </div>
</template>
<script>
    import $ from 'jquery';
    export default {
        name: "imgs",
        mounted() {
            this.$nextTick(()=> {
                $.fn.extend({
                    yx_rotaion: function(options_S) {
                        //默认参数
                        var defaults = {
                            /**轮换间隔时间，单位毫秒*/
                            during:3000,
                            /**是否显示左右按钮*/
                            btn:true,
                            /**是否显示焦点按钮*/
                            focus:true,
                            /**是否显示标题*/
                            title:true,
                            /**是否自动播放*/
                            auto:true
                        }
                        let options_s = $.extend(defaults, options_S);
                        return this.each(function(){
                            var o = options_s;
                            var curr_index = 0;
                            var $this = $(this);
                            var $li = $this.find("li");
                            var li_count = $li.length;
                            $this.css({position:'relative',overflow:'hidden',width:$li.find("img").width(),height:$li.find("img").height()});
                            $this.find("li").css({position:'absolute',left:0,top:0}).hide();
                            $li.first().show();
                            $this.append(`<div class="yx-rotaion-btn"><span class="left_btn"></span><span class="right_btn"></span></div>`);
                            if(!o.btn) $(".yx-rotaion-btn").css({visibility:'hidden'});
                            if(o.title) $this.append(`<div class="yx-rotation-title"></div><a href="" class="yx-rotation-t"></a>`);
                            if(o.focus) $this.append(`<div class="yx-rotation-focus"></div>`);
                            var $btn = $(".yx-rotaion-btn span"),$title = $(".yx-rotation-t"),
                                // $title_bg = $(".yx-rotation-title"),
                                $focus = $(".yx-rotation-focus");
                            //如果自动播放，设置定时器
                            if(o.auto) var t = setInterval(function(){$btn.last().click()},o.during);
                            $title.text($li.first().find("img").attr("alt"));
                            $title.attr("href",$li.first().find("a").attr("href"));

                            // 输出焦点按钮
                            for(let i=1;i<=li_count;i++){
                                $focus.append('<span>'+i+'</span>');
                            }
                            // 兼容IE6透明图片
                            // if($.browser.msie && $.browser.version == "6.0" ){
                            //     $btn.add($focus.children("span")).css({backgroundImage:'url(images/ico.gif)'});
                            // }
                            var $f = $focus.children("span");
                            $f.first().addClass("hover");
                            // 鼠标覆盖左右按钮设置透明度
                            $btn.hover(function(){
                                $(this).addClass("hover");
                            },function(){
                                $(this).removeClass("hover");
                            });
                            //鼠标覆盖元素，清除计时器
                            $btn.add($li).add($f).hover(function(){
                                if(t) clearInterval(t);
                            },function(){
                                if(o.auto) t = setInterval(function(){$btn.last().click()},o.during);
                            });
                            //鼠标覆盖焦点按钮效果
                            $f.bind("mouseover",function(){
                                var i = $(this).index();
                                $(this).addClass("hover");
                                $focus.children("span").not($(this)).removeClass("hover");
                                $li.eq(i).fadeIn(300);
                                $li.not($li.eq(i)).fadeOut(300);
                                $title.text($li.eq(i).find("img").attr("alt"));
                                $title.attr("href",$li.eq(i).find("a").attr("href"));
                                console.log("href:",$li.eq(i).find("a").attr("href"));
                                curr_index = i;
                            });
                            //鼠标点击左右按钮效果
                            $btn.bind("click",function(){
                                $(this).index() == 1?curr_index++:curr_index--;
                                if(curr_index >= li_count) curr_index = 0;
                                if(curr_index < 0) curr_index = li_count-1;
                                $li.eq(curr_index).fadeIn(300);
                                $li.not($li.eq(curr_index)).fadeOut(300);
                                $f.eq(curr_index).addClass("hover");
                                $f.not($f.eq(curr_index)).removeClass("hover");
                                $title.text($li.eq(curr_index).find("img").attr("alt"));
                                $title.attr("href",$li.eq(curr_index).find("a").attr("href"));
                            });

                        });
                    }
                });
                $(".yx-rotaion").yx_rotaion({ auto: true });
            })


        }
    }
</script>
<style scoped>
    /*yx_rotaion*/
    .yx-rotaion {
        margin: 0px;
        padding: 0px;
    }
    .yx-rotaion-btn, .yx-rotaion-title, .yx-rotation-focus, .yx-rotation-t, .yx-rotaion-btn {
        position:absolute;
    }
    .yx-rotation-title {
        position: absolute;
        width: 100%;
        height: 40px;
        line-height: 40px;
        background: #000;
        filter: alpha(opacity=40);
        -moz-opacity: 0.4;
        -khtml-opacity: 0.4;
        opacity: 0.4;
        left: 0;
        bottom: 0;
        /*_bottom: -1px;*/
        z-index: 1
    }
    .yx-rotation-t {
        color: #fff;
        font-size: 16px;
        font-family: microsoft yahei;
        z-index: 2;
        bottom: 0;
        left: 10px;
        line-height: 40px
    }
    .yx-rotation-focus span, .yx-rotaion-btn span {
        display: block;
    }
    .yx-rotation-focus {
        height: 40px;
        line-height: 40px;
        right: 20px;
        bottom: 0;
        z-index: 2
    }
    .yx-rotation-focus span {
        z-index: 999;
        width: 12px;
        height: 12px;
        line-height: 12px;
        float: left;
        margin-left: 5px;
        position: relative;
        top: 14px;
        cursor: pointer;
        background-color: white;
        background-position: -24px -126px;
        text-indent: -9999px
    }
    .yx-rotaion-btn {
        width: 100%;
        height: 41px;
        top: 50%;
        margin-top: -20px;
        display: none;
    }
    .yx-rotaion-btn span {
        width: 41px;
        height: 41px;
        cursor: pointer;
        filter: alpha(opacity=30);
        -moz-opacity: 0.3;
        -khtml-opacity: 0.3;
        opacity: 0.3;
        position: relative
    }
    .yx-rotaion-btn .left_btn {
        background-position: -2px -2px;
        float: left;
        left: 10px
    }
    .yx-rotaion-btn .right_btn {
        background-position: -2px -49px;
        float: right;
        right: 10px
    }
    .yx-rotaion-btn span.hover {
        filter: alpha(opacity=80);
        -moz-opacity: 0.8;
        -khtml-opacity: 0.8;
        opacity: 0.8
    }
    .yx-rotation-focus span.hover {
        background-color: red;
        background-position: -10px -126px;
    }
    .rotaion_list {
        width: 0;
        height: 0;
        overflow: hidden;
    }
    .yx-rotaion a {
        color: white;
        font-size: 14px;
    }
</style>