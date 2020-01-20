<template>
    <div class="menu_panner" >
        <ul class="menu_p">
            <li  :class="nclass[0]" @mouseover="changemenu(0)"><a href="/">首页</a></li>
            <li  :class="nclass[1]" @mouseover="changemenu(1)">
                <a href="#">支队强军网</a>
            </li>
            <li  :class="nclass[2]" @mouseover="changemenu(2)"><a href="#">主题教育</a>
                <ul v-show="mc_isShow_2" class="menu_child">
                    <li style="background: inherit;height: 20px;"><img style="width: 30px;" src="../assets/imgs/T_arr.png"/></li>
                    <li v-for="(item,idx) in child_list" :key="idx" @mouseover="changeActive($event)" @mouseout="removeActive($event)"><a :href="showchildlink(item.cid,item.classname)">{{item.classname}}</a></li>
<!--                    <li @mouseover="changeActive($event)" @mouseout="removeActive($event)"><a href="/list/1/活动动态">活动动态</a></li>-->
<!--                    <li @mouseover="changeActive($event)" @mouseout="removeActive($event)"><a href="/list/2/学习资料">学习资料</a></li>-->
<!--                    <li @mouseover="changeActive($event)" @mouseout="removeActive($event)"><a href="/list/3/权威解读">权威解读</a></li>-->
<!--                    <li @mouseover="changeActive($event)" @mouseout="removeActive($event)"><a href="/list/4/通知通告">通知通告</a></li>-->
<!--                    <li @mouseover="changeActive($event)" @mouseout="removeActive($event)"><a href="/list/5/交流研究">交流研究</a></li>-->
                </ul>
            </li>
            <li  :class="nclass[3]" @mouseover="changemenu(3)"><a href="#">信息发布</a></li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "menu_N",
        data(){
            return {
                nclass:[
                    {menu_on:true,menu:false},
                    {menu_on:false,menu:true},
                    {menu_on:false,menu:true},
                    {menu_on:false,menu:true},
                ],
                child_list:[
                    {classname:"活动动态",cid:"1"},
                    {classname:"学习资料",cid:"2"},
                    {classname:"权威解读",cid:"3"},
                    {classname:"通知通告",cid:"4"},
                    {classname:"交流研究",cid:"5"},
                ],
                mc_isShow_1:false,
                mc_isShow_2:false
            }
        },
        methods:{
            changemenu(index){
                //console.log("=--=-=-=",index);
                this.nclass.forEach(item => {
                    item.menu_on=false;
                    item.menu=true;
                })
                this.nclass[index].menu_on=true;
                this.nclass[index].menu=false;
                this.mc_isShow_1=false;
                this.mc_isShow_2=false;
                if(index===1)
                {
                    this.mc_isShow_1=true;
                }
                else if(index===2)
                {
                    this.mc_isShow_2=true;
                }
            },
            changeActive($event) {
                $event.currentTarget.className = 'childactive';
            },
            removeActive($event) {
                $event.currentTarget.className = '';
            },
            //拼接设置子菜单链接
            showchildlink(cid,classname){
                return "/list/"+cid+"/"+classname;
            }
        }
    }
</script>
<style scoped>
    a{
        text-decoration: none;
        color:#333333;
    }
    .menu_panner {
        width:1200px;
        height: 74px;
        background-color: #ffffff;
        margin: 0 auto;
    }
    .menu_p {
        list-style: none;
        width: 580px;
        margin: 0px;
        padding: 0px;
        z-index: 9;
    }
    .menu_on
    {
        float:left;
        min-width:114px;
        background-color: #2a5791;
        height:41px;
        color:White;
        line-height:41px;
        text-align:center;
        font-family:微软雅黑;
        font-size:16px;
        position:relative;
        top: 0px;
        left: 0px;
        z-index:9;
        border-radius: 5px;
        margin-left: 20px;
        margin-top: 16px;
    }
    .menu_on a{
        color:white;
    }
    .menu
    {
        float:left;
        min-width:114px;
        height:41px;
        line-height: 41px;
        text-align:center;
        font-family:微软雅黑;
        font-size:16px;
        position:relative;
        top: 0px;
        left: 0px;
        z-index:9;
        border-radius: 5px;
        margin-left: 20px;
        margin-top: 16px;
    }
    .menu a{
        color:black;
    }
    .menu_child {

        border-bottom: solid 1px #e9e9e9;
        float: left;
        margin: 0px;
        padding: 0px;
        list-style: none;
        position: absolute;
        top: 41px;
        left: 0px;
        width: 114px;

        color: white;
        z-index: 999;
        opacity: 85%;
    }
    .menu_child li{
        background-color: #e7e9ec;
    }
    .menu_child_on li{
        background-color: #2a5791;

    }
    .menu_child a{
        color:black;
    }
    .childactive {
        /*background-color: #2a5791;*/
        z-index: 10;
        background: none;
        background-color: black;
    }
    .childactive a {
        font-weight: bolder;
        font-size: 18px;
        color:#2a5791;
    }
</style>