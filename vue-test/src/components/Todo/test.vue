<template>
    <div>
        <input type="text" v-model="msg" placeholder="请添加事件">
        <button @click='add'>添加</button>
        
        <Todoitem :list='list'></Todoitem>
        <span v-show='isShow'>还没有添加任何事件哦...</span>
    </div>
</template>
<script>
import Todoitem from './todoitem.vue'

export default{
    data(){
        return{
            msg:'',
            list:['吃饭','睡觉','打豆豆'],
            isShow:false
        }
    },
    components:{
        Todoitem
    },
    methods:{
        add(){
            this.list.unshift(this.msg);
            this.msg='';
        }
    },
    watch:{
        list:function(){
            this.list.length==0?this.isShow=true:this.isShow=false;
        }
    }
}
</script>
<style scoped>

</style>