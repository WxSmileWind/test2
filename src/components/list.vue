<template>
    <div style="width: 1200px;height: 800px;margin: 0 auto;">
        <div class="left">
            左侧菜单栏
        </div>
        <div class="right">
            <el-table
                    @row-click="router"
                        :data="data"
                        style="width: 100%">
                    <el-table-column
                            prop="name"
                            label="姓名"
                            width="180">
                    </el-table-column>
                    <el-table-column
                            prop="address"
                            label="地址"
                            width="500">
                    </el-table-column>
                    <el-table-column
                            prop="date"
                            label="发布日期"
                            width="180"
                    >
                    </el-table-column>
                </el-table>
            <el-pagination
                    @current-change="change"
                    background
                    layout="prev, pager, next"
                    :total="total"
                    :page-size="1"
                    >
            </el-pagination>
        </div>
    </div>
</template>
<script>
    import {fetchData} from '@/api/index';
    export default {
        name: "list",
        data(){
            return{
                name:'',
                data:[],
                total:0,
            }
        },
        created() {
            console.log('-------------------------',this.$route);
            this.name = this.$route.params.name;
            this.setData(1);
        },
        methods:{
            setData(page){
                fetchData({"cid":10}).then(res=>{
                    console.log(res);
                    console.log(res.list);
                    console.log("总条数：",res.pageTotal);
                    this.data=res.list;
                    this.total=res.pageTotal;
                    console.log("total：",this.total);
                }).catch(err=>{
                    console.log(err);
                })
            },
            change(page){
                console.log(page)
                this.setData(page);
            },
            router(row, column, event){
                console.log("选中行的id：",row.id)
                const { href } = this.$router.resolve({
                    name: `read`,
                    params: {
                        id: row.id,
                    }
                })
                window.open(href, '_blank');
            }
        }
    }
</script>
<style scoped>
    .left {
        float: left;
        width: 320px;
        height: 800px;
        background-color: azure;
    }
    .right {
        float: right;
        width: 860px;
        height: 800px;
        background-color: aquamarine;
    }
</style>