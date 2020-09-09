<template>
    <div class='wrap'>
        <h2>记事本</h2>
        <div class="tools">
            <button class="btn">新建</button>
            <button class="btn" @click="save">保存</button>
            <button class="btn">恢复</button>
            <button class="btn">xxxx</button>
        </div>
       <div class="note">
            <div><input type="text"  v-model="title" class="title form-control" placeholder="请输入标题"></div>
            <div><textarea class="content form-control" v-model="content" placeholder="写点什么吧~"></textarea></div>
        </div>
    </div>
</template>
<script>
export default {
    name:'Note',
    data(){
        return{
            title:'',
            content:''
        }
    },
    methods:{
        save(){
            console.log(this.title,this.content)
        }
    }
}
</script>
<style scoped>
.btn{
    padding:6px 15px;
    background-color: royalblue;
    color: white;
    border-radius: 10px;
    margin-right: 0.5em;
    outline: none;
    border: none;
}
.note{
    margin-top: 10px;
    width: 580px;
    height: 600px;
    border: 1px solid #999;
    border-radius: 10px;
    padding:1em; 
}
.title{
    height: 30px;
    width: 300px;
    border-radius: 5px;
    line-height: 30px;
    float: left;
    border: 1px solid #ccc;
    outline: none;
    margin-bottom: 10px;
    padding-left: .5em;
    font-size: 16px;
}
.content{
    width: 560px;
    height: 540px;
    border: 1px solid #ccc;
    padding: .5em;
    font-size: 16px;
}
</style>