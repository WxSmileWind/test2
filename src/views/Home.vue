<template>
    <div>
        <div class="top">
            <top/>
            <div style="width:100%;  background-color: #ffffff;">
                <menu_N/>
            </div>
        </div>
        <div class="main">
            <imgs />
            <div class="main_right">
                <div style="height:43px;width:100%;border-bottom: solid 1px #DFDFDF;">
                    <div style="float:left;width: 100px;height: 43px; line-height: 43px;">
                        <span class="show_title_l" style="color:black;">支队</span><span class="show_title_r"
                                                                                       style="color:#2a5791;">要闻</span>
                    </div>
                    <div style="float:right;width: 340px;height: 43px; line-height: 43px;">
                        <ul class="main_right_t">
                            <li :class="main_right_m[0]" @mouseover="changemenu(0)" title="最新信息">最新信息</li>
                            <li style="width: 5px;">|</li>
                            <li :class="main_right_m[1]" @mouseover="changemenu(1)" title="一周信息">一周信息</li>
                            <li style="width: 5px;">|</li>
                            <li :class="main_right_m[2]" @mouseover="changemenu(2)" title="本月信息">本月信息</li>
                            <li style="width: 5px;">|</li>
                            <li :class="main_right_m[3]" @mouseover="changemenu(3)" title="更早" style="width: 60px;">更早
                            </li>
                        </ul>
                    </div>
                </div>
                <div class="news_panner"  v-show="main_right_c[0]">
                    <div class="news">
                        <div class="news_icon"><img src="../assets/imgs/point.png"></div>
                        <div class="news_con">
                            <a href="/read/1" target="_blank" title="宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知">宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知 </a>
                        </div>
                        <div class="news_date" >
                            2019-04-08
                        </div>
                    </div>
                    <div class="news">
                        <div class="news_icon"><img src="../assets/imgs/point.png"></div>
                        <div class="news_con">
                            <a href="/read/1" target="_blank" title="宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知">宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知 </a>
                        </div>
                        <div class="news_date" >
                            2019-04-08
                        </div>
                    </div>
                    <div class="news">
                        <div class="news_icon"><img src="../assets/imgs/point.png"></div>
                        <div class="news_con">
                            <a href="/read/1" target="_blank" title="宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知">宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知 </a>
                        </div>
                        <div class="news_date" >
                            2019-04-08
                        </div>
                    </div>
                    <div class="news">
                        <div class="news_icon"><img src="../assets/imgs/point.png"></div>
                        <div class="news_con">
                            <a href="/read/1" target="_blank" title="宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知">宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知 </a>
                        </div>
                        <div class="news_date" >
                            2019-04-08
                        </div>
                    </div>
                    <div class="news">
                        <div class="news_icon"><img src="../assets/imgs/point.png"></div>
                        <div class="news_con">
                            <a href="/read/1" target="_blank" title="宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知">宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知 </a>
                        </div>
                        <div class="news_date" >
                            2019-04-08
                        </div>
                    </div>
                    <div class="news">
                        <div class="news_icon"><img src="../assets/imgs/point.png"></div>
                        <div class="news_con">
                            <a href="/read/1" target="_blank" title="宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知">宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知 </a>
                        </div>
                        <div class="news_date" >
                            2019-04-08
                        </div>
                    </div>
                    <div class="news">
                        <div class="news_icon"><img src="../assets/imgs/point.png"></div>
                        <div class="news_con">
                            <a href="/read/1" target="_blank" title="宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知">宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知 </a>
                        </div>
                        <div class="news_date" >
                            2019-04-08
                        </div>
                    </div>
                    <div class="news">
                        <div class="news_icon"><img src="../assets/imgs/point.png"></div>
                        <div class="news_con">
                            <a href="/read/1" target="_blank" title="宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知">宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知 </a>
                        </div>
                        <div class="news_date" >
                            2019-04-08
                        </div>
                    </div>
                    <div class="news">
                        <div class="news_icon"><img src="../assets/imgs/point.png"></div>
                        <div class="news_con">
                            <a href="/read/1" target="_blank" title="宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知">宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知 </a>
                        </div>
                        <div class="news_date" >
                            2019-04-08
                        </div>
                    </div>
                    <div class="news">
                        <div class="news_icon"><img src="../assets/imgs/point.png"></div>
                        <div class="news_con">
                            <a href="/read/1" target="_blank" title="宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知">宁波市公安局政治部关于报送渉警、涉稳舆情季度分析报告的通知 </a>
                        </div>
                        <div class="news_date" >
                            2019-04-08
                        </div>
                    </div>
                </div>
                <div class="news_panner" v-show="main_right_c[1]">
                    一周信息
                </div>
                <div class="news_panner" v-show="main_right_c[2]">
                    本月信息
                </div>
                <div class="news_panner"  v-show="main_right_c[3]">
                    更早
                </div>
            </div>

            <!-- <a style="margin-left: 20px" v-for="item in 5" :key="item" @click="routerTo(item)" >点击跳转</a>-->
        </div>
        <div style="width: 1230px;height:374px; background-color: #2a5791;clear: both; margin: 0 auto; margin-top: 20px;">
            <div style="float:left;width:600px;height:374px; background-color: #2c3e50">
            </div>
            <div style="float:left;margin-left: 25px;  width:600px;height:374px; background-color: #2c3e50">
            </div>
        </div>
    </div>
</template>
<script>
    // @ is an alias to /src
    import imgs from "@/components/imgs.vue";
    import top from "@/components/top.vue";
    import menu_N from "@/components/menu_N.vue";
    export default {
        name: "home",
        data(){
            return {
                main_right_m:[
                    {menu_on:true},
                    {menu_on:false},
                    {menu_on:false},
                    {menu_on:false},
                ],
                main_right_c:[
                    true,
                    false,
                    false,
                    false,
                ]
            }
        },
        components: {
            imgs, top, menu_N
        },
        methods: {
            routerTo(id) {
                const { href } = this.$router.resolve({
                    name: `list`,
                    params: {
                        id: id,
                        name:'花季风',
                    }
                })

                window.open(href, '_blank');
            },
            changemenu(index) {
                //设置选项卡复位
                this.main_right_m.forEach(item => {
                    item.menu_on = false;
                })
                // this.main_right_c.forEach(item_c => {
                //     item_c = false;
                //     console.log(item_c);
                // })
                //设置选项卡对应内容复位
                for(let i=0;i<=3;i++)
                {
                    this.main_right_c[i]=false;
                }
                this.main_right_m[index].menu_on = true;
                this.main_right_c[index] = true;
            }
        }
    };
</script>
<style scoped>
    .top {
        width: 100%;
    }
    .show_title_l{
        color:black;
        font-size: 18px;
        font-weight: bolder;
    }
    .show_title_r{
        color:#2a5791;
        font-size: 18px;
        font-weight: bolder;
    }
    .main {
        width: 1200px;
        min-height: 410px;
        height: auto;
        margin: 0 auto;
        margin-top: 29px;
        background-color: #ffffff;
        padding: 15px;
        position: relative;
        box-shadow: 0 4px 10px -3px #c8c7c6;
    }
    .main_right{
        float:right;
        width:600px;
        height:407px;
        /*background-color: #f5f7f8;*/
    }
    .main_right_t{
        margin: 0px;
        padding: 0px;
        list-style: none;
    }
    .main_right_t li{
        float:left;
        width: 85px;
        color:#4d4e4f;
        font-size: 16px;
        cursor: pointer;
    }
    .menu_on{
        border-bottom: solid 2px #2a5791;
    }
    .news_panner {
        width: 100%;
        height: 360px;
        margin-top: 4px;
    }
    .news{
        width:600px;
        height:36px;
        overflow:hidden;
    }
    .news_icon {
        float: left;
        width: 20px;
        height: 36px;
    }
    .news_icon img {
        width: 5px;
        height: 5px;
        display: block;
        margin-top: 16px;
        margin-left: 5px;
    }
    .news_con {
        float: left;
        display: inline;
        width: 477px;
        height: 36px;
        line-height: 36px;
        white-space: nowrap;
        text-overflow: ellipsis;
        overflow: hidden;
    }
    .news_con a{
        text-decoration: none;
        color: #333333;
        font-size: 16px;
        display: block;
        float: left;
        height: 33px;
    }
    .news_con a:hover{
        text-decoration: none;
        color:#2a5791;
    }
    .news_date {
        float: left;
        display: inline;
        width: 100px;
        height: 36px;
        line-height: 36px;
        font-family: Arial;
        font-size: 16px;
        text-align: right;
        color:#bcbcbc;
    }
</style>

