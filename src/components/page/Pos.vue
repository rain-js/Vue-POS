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
                <div class="often-goods">
                    <div class="often-goods-title">常用商品</div>
                    <ol class="clearfix" >
                        <li v-for="goods in oftenGoods">
                            <span class="often-goods-name">{{goods.goodsName}}</span>
                            <span class="often-goods-price">￥{{goods.price}}</span>
                        </li>
                    </ol>
                </div>
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
                }],
                oftenGoods:[
                    {
                        goodsId:1,
                        goodsName:'香辣鸡腿堡',
                        price:18
                    }, {
                        goodsId:2,
                        goodsName:'田园鸡腿堡',
                        price:15
                    }, {
                        goodsId:3,
                        goodsName:'和风汉堡',
                        price:15
                    }, {
                        goodsId:4,
                        goodsName:'快乐全家桶',
                        price:80
                    }, {
                        goodsId:5,
                        goodsName:'脆皮炸鸡腿',
                        price:10
                    }, {
                        goodsId:6,
                        goodsName:'魔法鸡块',
                        price:20
                    }, {
                        goodsId:7,
                        goodsName:'可乐大杯',
                        price:10
                    }, {
                        goodsId:8,
                        goodsName:'雪顶咖啡',
                        price:18
                    }, {
                        goodsId:9,
                        goodsName:'大块鸡米花',
                        price:15
                    }, {
                        goodsId:20,
                        goodsName:'香脆鸡柳',
                        price:17
                    }
                ]
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
    .often-goods-title {
        height: 20px;
        border-bottom:1px solid #D3DCE6;
        background-color: #F9FAFC;
        padding:10px;
    }
    .often-goods li {
        float:left;
        border:1px solid #E5E9F2;
        padding:10px;
        margin:5px;
        background-color:#fff;
    }
    .often-goods-price {
        color:#58B7FF;
    }
</style>
