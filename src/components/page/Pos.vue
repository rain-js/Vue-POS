<template>
    <div class="pos">
        <el-row>
            <el-col :span="6" class="order-list fix-height">
                <div>订单栏</div>
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
                msg: 'Hello Pos Demo'
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
    .order-list {
        border-right: 1px solid blue;
        background: #d3dce6;
    }
    .goods-list {
        background: #e5e9f2;
    }
</style>
