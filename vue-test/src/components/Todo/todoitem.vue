<template>
    <div>
        <ul>
            <li v-for="(item,i) in list" :key="item">id:{{i+1}}----{{item}}&nbsp;&nbsp;&nbsp;&nbsp;<button @click="del(i)">删除</button></li>
        </ul>
    </div>
</template>
<script>
export default{
    name:'Todoitem',
    data(){
        return{

        }
    },
    props:['list'],
    methods:{
        del(i){
            this.list.splice(i,1);
        }
    }
}
</script>
<style scoped>

</style>