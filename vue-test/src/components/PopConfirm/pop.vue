<template>
    <div>
        <h3>确定框组件</h3>
        <button @click="pop">分手吧</button>
        <div class="pop" v-show="isShow" :style="{left:x+'px',top:y+'px'}">
            <p>你真要和我分手吗?</p>
            <div class="tool">

            <button @click="pop">取消</button>
            <button>确认</button>
            </div>
            <span class="caret"></span>
        </div>
        <!-- <button @click="pop"><slot>hhhhh</slot></button>
        <div class="pop" v-show="isShow" :style="{left:x+'px',top:y+'px'}">
            <p>{{msg}}</p>
            <div class="tool">

            <button @click="pop">取消</button>
            <button>确认</button>
            </div>
            <span class="caret"></span>
        </div> -->
    </div>
</template>
<script>
export default {
    name:'Pop',
    data(){
        return{
            isShow:false,
            x:0,
            y:0
        }
    },
    props:['msg'],
    methods:{
        pop(mouse){
            this.isShow=!this.isShow;
            this.x=mouse.pageX-30;
            this.y=mouse.pageY-30;
        }
    }
}
</script>
<style lang="css">
.pop{
    background-color: #fff;
    height: 100px;
    width: 200px;
    position:absolute;
    border-radius: 5px;
    /* top:120px; */
    box-shadow: 0 0 10px #ccc;
}
.pop>p{
    padding-top: 10px;
}
.tool{
    float: right;
    padding-right: 10px;
}
.caret{
    display: inline-block;
    border-width:9px;
    border-style: solid;
    border-color:transparent transparent #fff transparent ;
    position: absolute;
    top:-18px;
    left:20px;
}
</style>