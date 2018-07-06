<template>
    <div class="pos">
        <el-row>
            <el-col :span="6" class="order-list fix-height">
                <el-tabs class="order-tabs" >
                    <el-tab-pane label="点餐">
                        <template>
                        <el-table :data="tableData" border style="width: 100%">
                            <el-table-column prop="goodsName" label="商品名称" width="100">
                            </el-table-column>
                            <el-table-column prop="count" label="数量" width="60">
                            </el-table-column>
                            <el-table-column prop="price" label="金额" width="60">
                            </el-table-column>
                            <el-table-column fixed="right" label="操作" width="100">
                                <template slot-scope="scope">
                                    <el-button type="text" size="small">删除</el-button>
                                    <el-button type="text" size="small">增加</el-button>
                                </template>
                            </el-table-column>
                        </el-table>
                        <div class="button-group">
                            <el-button type="warning">挂单</el-button>
                            <el-button type="danger">删除</el-button>
                            <el-button type="success">结账</el-button>
                        </div>
                        </template>
                    </el-tab-pane>
                    <el-tab-pane label="挂单">挂单</el-tab-pane>
                    <el-tab-pane label="外卖">外卖</el-tab-pane>
                </el-tabs>
            </el-col>
            <el-col :span="18" class="goods-list fix-height">
                <div>产品栏</div>
            </el-col>
        </el-row>
    </div>
    
</template>

<script>
    export default {
        name: 'Pos',
        data () {
            return {
                msg: 'Hello Pos Demo',
                tableData: [{
                        goodsName: '可口可乐',
                        price: 8,
                        count:1
                    }, {
                        goodsName: '香辣鸡腿堡',
                        price: 15,
                        count:1
                    }, {
                        goodsName: '爱心薯条',
                        price: 8,
                        count:1
                    }, {
                    goodsName: '甜筒',
                    price: 8,
                    count:1
                }]
            }
        },
        mounted() {
            // height: 100%
            let ch = document.body.clientHeight,
                x = document.getElementsByClassName('fix-height'),
                aX = Array.from(x)
            
            aX.forEach(element => {
                element.style.height =  ch + 'px'      
            })
        }
    }
</script>

<style scoped>
    .pos {
        overflow: hidden;
    }
    .goods-list {
        background: #e5e9f2;
    }
    .button-group {
        margin-top: 20px;
    }
</style>
